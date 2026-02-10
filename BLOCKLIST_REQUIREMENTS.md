# Skills Blocklist - Requirements & Maintenance Guide

**Document Version:** 1.2
**Last Updated:** 2026-02-10
**Purpose:** Define structure, criteria, and update procedures for the skills blocklist

---

## Table of Contents

1. [Overview](#overview)
2. [Severity Classification](#severity-classification)
3. [File Structure](#file-structure)
4. [Update Procedures](#update-procedures)
5. [Quality Assurance](#quality-assurance)
6. [Integration Guidelines](#integration-guidelines)

---

## Overview

The Skills Blocklist provides **two-tier protection** for AI agent users:

1. **BLOCKED** - Skills that MUST NOT be installed (MALICIOUS or CRITICAL severity)
2. **SUSPICIOUS** - Skills that require USER WARNING before installation (SUSPICIOUS severity)

### Core Principles

- **Severity-Based Action**: Protection level determined by BOTH skill name AND severity level
- **Transparency**: All entries include scan dates and primary threat descriptions
- **Maintainability**: Clear structure for manual and automated updates
- **Accessibility**: Human-readable markdown format parseable by code

---

## Severity Classification

### Risk Score Ranges

| Risk Score | Severity | Action | Description |
|------------|----------|--------|-------------|
| **51-67** | CRITICAL | **BLOCK** | Severe security vulnerabilities |
| **N/A** | MALICIOUS | **BLOCK** | Confirmed malware/malicious intent |
| **40-50** | SUSPICIOUS | **WARN** | Concerning security patterns |
| **26-39** | Medium | MONITOR | Not in blocklist, track for escalation |
| **11-25** | Low | LOG | Informational only |
| **0-10** | Safe | ALLOW | Generally benign |

### Risk Score Calculation

Risk scores are calculated using the following methodology (from aggregate_results.py):

```python
def calculate_risk_score(report):
    score = 0

    # High risk indicators (10 points each)
    if remote_code_execution: score += 10
    if malware_download: score += 10
    if data_exfiltration: score += 10

    # Medium risk indicators (5 points each)
    if privilege_escalation: score += 5
    if process_injection: score += 5
    if persistence_mechanism: score += 5
    if code_obfuscation: score += 5

    # Low risk indicators (2 points each)
    if excessive_permissions: score += 2

    # Suspicious patterns (1 point each, max 10)
    score += min(len(suspicious_patterns), 10)

    # Vulnerabilities (2 points each, max 10)
    score += min(len(vulnerabilities) * 2, 10)

    return score
```

**Maximum Theoretical Score:** 72
**Maximum Observed Score:** 67

### Severity Assignment Rules

1. **MALICIOUS** (31 skills):
   - Verdict = "malicious" in security analysis report
   - Confirmed active threats: RCE, credential theft, data exfiltration, malware
   - **Action:** BLOCK installation, no exceptions

2. **CRITICAL** (66 skills):
   - Risk score >= 51
   - Severe vulnerabilities or suspicious patterns
   - **Action:** BLOCK installation, no exceptions

3. **SUSPICIOUS** (154 skills):
   - Risk score 40-50
   - Concerning but not confirmed malicious
   - **Action:** WARN user, allow installation with consent

---

## File Structure

### SKILL-BLOCKLIST.md Structure

```markdown
# Agent Skills Blocklist

**Last Updated:** YYYY-MM-DD
**Scan Dates:** YYYY-MM-DD, YYYY-MM-DD
**Total Blocked Skills:** <count>
**Total Suspicious Skills:** <count>
**Malicious Skills:** <count>
**Critical Risk Skills:** <count>
**Total Skills Scanned:** <count>
**Source:** OpenClaw Skills Repository Security Analysis

## How to Use This Blocklist
[Instructions for two-tier checking]

## Blocked Skills
[Table with MALICIOUS and CRITICAL skills]

## Suspicious Skills
[Table with SUSPICIOUS skills]

## Malicious Skills Summary
[List of confirmed malicious skills]

## Usage Examples
[Python and JavaScript integration examples]

## Severity Levels
[Detailed severity descriptions]
```

### Table Format Requirements

**Blocked Skills Table:**
| Column | Type | Required | Description |
|--------|------|----------|-------------|
| Skill Name | string | YES | Exact folder name from repository |
| Version | string | YES | Semantic version from _meta.json (e.g., 1.0.0) or "N/A" |
| Risk Score | integer | YES | 51-67 or N/A for confirmed malicious |
| Severity | enum | YES | MALICIOUS or CRITICAL |
| Primary Threat | string | YES | Max 80 chars, from security analysis |
| Scan Date | date | YES | YYYY-MM-DD format |

**Suspicious Skills Table:**
| Column | Type | Required | Description |
|--------|------|----------|-------------|
| Skill Name | string | YES | Exact folder name from repository |
| Version | string | YES | Semantic version from _meta.json (e.g., 1.0.0) or "N/A" |
| Risk Score | integer | YES | 40-50 |
| Severity | enum | YES | SUSPICIOUS (fixed value) |
| Primary Threat | string | YES | Max 80 chars, from security analysis |
| Scan Date | date | YES | YYYY-MM-DD format |

**Sorting Rules:**
1. Within each table, sort by Risk Score (descending)
2. Within same score, sort alphabetically by Skill Name
3. Maintain consistent column widths for readability

---

## Update Procedures

### Adding New Skills

#### Step 1: Run Security Analysis

```bash
# Ensure security analysis is complete
cd ~/Documents/work/skills/security_analysis
python3 aggregate_results.py
```

#### Step 2: Identify New High-Risk Skills

```python
# Extract skills with scores >= 40
import json

with open('statistics.json', 'r') as f:
    stats = json.load(f)

# Blocked: scores 51+
blocked = [x for x in stats['high_risk_folders'] if x['score'] >= 51]

# Suspicious: scores 40-50
suspicious = [x for x in stats['high_risk_folders'] if 40 <= x['score'] <= 50]
```

#### Step 3: Generate Table Entries

For each skill:
1. Read corresponding `reports/{skill_name}_analysis.json`
2. Extract primary threat from `reasons[0]` (truncate to 80 chars)
3. Extract version from skill metadata:
   - **Directory Structure:** `../skills/{author_name}/{skill_subdirectory}/_meta.json`
   - **Author Name:** Same as `skill_name` (e.g., for skill "aymenafia" → `/skills/aymenafia/`)
   - **Skill Subdirectory:** First subdirectory under author directory
   - **Version Path:** `_meta.json` → `latest.version` field
   - **Example:** For "aymenafia": `/skills/aymenafia/jeanclaw-arena/_meta.json` → `latest.version`
   - **Default:** Use "N/A" if _meta.json is missing or version field is absent
   - **Multi-Skill Authors:** If author has multiple skills, use first skill's version
4. Determine scan date (date of analysis run)
5. Assign severity based on risk score and verdict

#### Step 4: Update SKILL-BLOCKLIST.md

1. Update header statistics:
   ```markdown
   **Last Updated:** YYYY-MM-DD
   **Total Blocked Skills:** <new count>
   **Total Suspicious Skills:** <new count>
   ```

2. Add entries to appropriate table (Blocked or Suspicious)
3. Maintain sorting order (score DESC, name ASC)
4. Update "Malicious Skills Summary" if new malicious skills added

#### Step 5: Update README.md

1. Update "Current Statistics" section with new counts
2. Calculate total skills scanned by counting author directories:
   ```bash
   ls -d /path/to/skills/skills/*/ | wc -l
   ```
   **Important:** The total skills scanned count is the number of author directories in the skills repository, NOT the total_skills value from statistics.json (which may include subdirectories or other counts).
3. Add entry to "Recent Updates" section
4. Update "Last Updated" date in footer

#### Step 6: Update UPDATE_SUMMARY.md

Create/update summary documenting:
- Scan date
- Skills analyzed
- New entries added
- Removed entries (if any)
- Statistics changes

---

## Quality Assurance

### Pre-Commit Checks

Before committing updates:

```bash
# 1. Verify table formatting
grep "^|" SKILL-BLOCKLIST.md | head -30

# 2. Count entries
grep "| [a-z]" SKILL-BLOCKLIST.md | wc -l

# 3. Verify no duplicate entries
grep "^|" SKILL-BLOCKLIST.md | sort | uniq -d

# 4. Check date format (YYYY-MM-DD)
grep -E "\| [0-9]{4}-[0-9]{2}-[0-9]{2} \|" SKILL-BLOCKLIST.md

# 5. Verify severity values
grep -E "\| (MALICIOUS|CRITICAL|SUSPICIOUS) \|" SKILL-BLOCKLIST.md
```

### Validation Rules

1. **No Duplicates**: Each skill name appears exactly once across both tables
2. **Correct Severity**: MALICIOUS/CRITICAL in Blocked, SUSPICIOUS in Suspicious
3. **Score Consistency**:
   - Blocked table: scores 51-67 or empty for MALICIOUS
   - Suspicious table: scores 40-50
4. **Date Format**: All scan dates in YYYY-MM-DD format
5. **Primary Threat**: Non-empty, meaningful description (not generic)

### Version Extraction Details

**Directory Structure:**
```
skills/
├── {author_name}/           # Author directory (same as skill name in blocklist)
│   ├── {skill_1}/           # Individual skill subdirectory
│   │   ├── _meta.json       # Contains version information
│   │   └── SKILL.md
│   ├── {skill_2}/           # Authors may have multiple skills
│   │   ├── _meta.json
│   │   └── SKILL.md
```

**Version Extraction Code:**
```python
import os
import json

def extract_skill_version(skill_name, skills_base_path):
    """
    Extract version from skill metadata.

    Args:
        skill_name: Author/skill name (e.g., "aymenafia")
        skills_base_path: Base path to skills directory

    Returns:
        Version string (e.g., "1.0.0") or "N/A"
    """
    author_path = os.path.join(skills_base_path, skill_name)

    if not os.path.exists(author_path) or not os.path.isdir(author_path):
        return "N/A"

    # List all skill subdirectories
    skill_dirs = [d for d in os.listdir(author_path)
                  if os.path.isdir(os.path.join(author_path, d))
                  and not d.startswith('.')]

    if len(skill_dirs) == 0:
        return "N/A"

    # Use first skill's version (for multi-skill authors)
    first_skill = skill_dirs[0]
    meta_path = os.path.join(author_path, first_skill, '_meta.json')

    if not os.path.exists(meta_path):
        return "N/A"

    try:
        with open(meta_path, 'r') as f:
            meta = json.load(f)
            return meta.get('latest', {}).get('version', 'N/A')
    except:
        return "N/A"

# Example usage
version = extract_skill_version("aymenafia", "/path/to/skills/skills")
# Returns: "1.0.0"
```

**Multi-Skill Authors:**
- **Count:** 103 authors have multiple skills
- **Strategy:** Use first skill's version alphabetically
- **Alternative:** Could track all versions or use latest version
- **Current Approach:** Simplicity - one version per author entry in blocklist

**Version Format Validation:**
- All versions should follow semantic versioning: `MAJOR.MINOR.PATCH`
- Examples: `1.0.0`, `2.1.1`, `0.1.0`
- Invalid formats default to "N/A"

### Common Issues

**Issue: Risk score changes after recalculation**
- **Cause:** Boolean field format inconsistency (nested objects vs simple booleans)
- **Fix:** Use `get_bool_value()` helper in aggregate_results.py
- **Prevention:** Ensure security analysis agents use simple booleans

**Issue: Skill in wrong table**
- **Cause:** Manual entry error or score threshold confusion
- **Fix:** Move to correct table based on score/severity
- **Prevention:** Automated script generation for table entries

**Issue: Outdated statistics in header**
- **Cause:** Forgot to update after adding entries
- **Fix:** Recalculate counts from tables
- **Prevention:** Include header update in checklist

**Issue: Version shows "N/A"**
- **Cause:** _meta.json file missing or malformed
- **Fix:** Verify file exists at correct path: `skills/{author}/{skill}/_meta.json`
- **Prevention:** Ensure skill repository maintains _meta.json for all skills

**Issue: Wrong version for multi-skill authors**
- **Cause:** Author has multiple skills with different versions
- **Context:** Current approach uses first skill's version alphabetically
- **Fix:** If accuracy critical, manually verify correct skill/version mapping
- **Alternative:** Modify extraction to track all skills and their versions

---

## Integration Guidelines

### For AI Agent Developers

#### Required Functionality

1. **Fetch Blocklist**
   ```python
   BLOCKLIST_URL = "https://raw.githubusercontent.com/nabeelxy/skill-blocklist/main/SKILL-BLOCKLIST.md"
   ```

2. **Parse Severity**
   - Extract skill name AND severity from table row
   - Use regex pattern: `\|\s*{skill_name}\s*\|[^|]*\|\s*(MALICIOUS|CRITICAL|SUSPICIOUS)\s*\|`

3. **Implement Two-Tier Protection**
   ```
   if severity in ['MALICIOUS', 'CRITICAL']:
       BLOCK installation (no user override)
   elif severity == 'SUSPICIOUS':
       WARN user, require explicit consent
   else:
       ALLOW installation
   ```

#### Caching Recommendations

- Cache blocklist locally for 24 hours
- Use ETags or Last-Modified headers
- Refresh on user-initiated update check
- Fallback to cached version if fetch fails

#### Error Handling

```python
try:
    status, severity = check_skill_security(skill_name)
except NetworkError:
    # Fall back to cached blocklist
    status, severity = check_cached_blocklist(skill_name)
except ParsingError:
    # Log error, default to safe
    log_error("Blocklist parsing failed")
    status, severity = ('safe', None)
```

#### User Messages

**Blocked Skill:**
```
⚠️  SECURITY WARNING ⚠️

The skill "{skill_name}" is BLOCKED due to {severity} threats.

This skill has been identified as malicious or critically vulnerable
and CANNOT be installed for your protection.

For more information:
https://github.com/nabeelxy/skill-blocklist
```

**Suspicious Skill:**
```
⚠️  SECURITY WARNING ⚠️

The skill "{skill_name}" contains SUSPICIOUS security patterns.

Risk Level: SUSPICIOUS (score: {score})
Primary Concern: {primary_threat}

This skill may pose security risks. Review the source code before proceeding.

Continue installation? (yes/no):
```

---

## Maintenance Schedule

### Daily
- Monitor for new skills in repository
- Check for community-reported threats

### Weekly
- Run security analysis on new skills
- Update blocklist with any findings
- Review suspicious skills for escalation

### Monthly
- Audit existing entries for false positives
- Review and update risk scoring methodology
- Generate monthly security report

### Quarterly
- Comprehensive re-analysis of all skills
- Update documentation and requirements
- Community feedback review

---

## Version History

| Version | Date | Changes |
|---------|------|---------|
| 1.2 | 2026-02-10 | Clarified version extraction from nested directory structure, added code examples |
| 1.1 | 2026-02-10 | Added Version column to table requirements |
| 1.0 | 2026-02-10 | Initial requirements document, two-tier system |

---

## Contact & Support

- **Issues**: https://github.com/nabeelxy/skill-blocklist/issues
- **Security Reports**: Private security advisories
- **Updates**: Follow repository for notifications

---

**Document Maintained By:** Security Analysis Team
**Review Frequency:** Quarterly or as needed for major changes
