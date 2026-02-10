# OpenClaw Skills Blocklist

A community-maintained blocklist of malicious and high-risk AI agent skills for OpenClaw, TinyClaw, Nanobot, and other Claude-based personal AI agents.

## Overview

This repository contains a curated blocklist of skills that pose security risks to AI agent users. The blocklist is based on comprehensive security analysis of the OpenClaw skills repository and is updated regularly to protect users from:

- **Malware and Remote Code Execution**
- **Credential Theft and Data Exfiltration**
- **Cryptocurrency Mining**
- **Botnet Recruitment**
- **Persistent Backdoors**
- **AI Agent Hijacking**
- **Supply Chain Attacks**

## Quick Start

### For Users

Before installing any skill, check against our blocklist:

```bash
# Download the latest blocklist
curl -O https://raw.githubusercontent.com/nabeelxy/skill-blocklist/main/SKILL-BLOCKLIST.md

# Search for a skill (example)
grep -i "pepe276" SKILL-BLOCKLIST.md
```

If the skill appears in the blocklist, **DO NOT INSTALL IT**.

### For AI Agent Developers

Integrate the blocklist into your agent:

**Python Example:**
```python
import requests
import re

BLOCKLIST_URL = "https://raw.githubusercontent.com/nabeelxy/skill-blocklist/main/SKILL-BLOCKLIST.md"

def check_skill_security(skill_name):
    """
    Check skill security status.
    Returns: ('blocked', severity) or ('suspicious', severity) or ('safe', None)
    """
    response = requests.get(BLOCKLIST_URL)
    blocklist_content = response.text

    # Parse table rows to find skill and its severity
    pattern = rf'\|\s*{re.escape(skill_name)}\s*\|[^|]*\|\s*(MALICIOUS|CRITICAL|SUSPICIOUS)\s*\|'
    match = re.search(pattern, blocklist_content, re.IGNORECASE)

    if match:
        severity = match.group(1).upper()
        if severity in ['MALICIOUS', 'CRITICAL']:
            return ('blocked', severity)
        elif severity == 'SUSPICIOUS':
            return ('suspicious', severity)

    return ('safe', None)

# Before skill installation
skill_to_install = "example-skill"
status, severity = check_skill_security(skill_to_install)

if status == 'blocked':
    print(f"BLOCKED: {skill_to_install} is {severity} - installation prevented")
    exit(1)
elif status == 'suspicious':
    print(f"WARNING: {skill_to_install} is {severity} - proceed with caution")
    # Optionally prompt user for consent
```

**JavaScript Example:**
```javascript
const BLOCKLIST_URL = "https://raw.githubusercontent.com/nabeelxy/skill-blocklist/main/SKILL-BLOCKLIST.md";

async function checkSkillSecurity(skillName) {
  const response = await fetch(BLOCKLIST_URL);
  const blocklistContent = await response.text();

  const pattern = new RegExp(
    `\\|\\s*${skillName.replace(/[.*+?^${}()|[\]\\]/g, '\\$&')}\\s*\\|[^|]*\\|\\s*(MALICIOUS|CRITICAL|SUSPICIOUS)\\s*\\|`,
    'i'
  );
  const match = blocklistContent.match(pattern);

  if (match) {
    const severity = match[1].toUpperCase();
    if (severity === 'MALICIOUS' || severity === 'CRITICAL') {
      return { status: 'blocked', severity };
    } else if (severity === 'SUSPICIOUS') {
      return { status: 'suspicious', severity };
    }
  }

  return { status: 'safe', severity: null };
}

// Usage
const result = await checkSkillSecurity("example-skill");
if (result.status === 'blocked') {
  console.log(`BLOCKED: Installation prevented - ${result.severity}`);
} else if (result.status === 'suspicious') {
  console.log(`WARNING: Proceed with caution - ${result.severity}`);
}
```

## Current Statistics

**Last Scan:** 2026-02-10

| Metric | Count |
|--------|-------|
| Total Blocked Skills | 97 |
| Confirmed Malicious | 31 |
| Critical Risk (51+) | 66 |
| Total Suspicious Skills | 154 |
| Skills Scanned | 2,770 |

## Severity Levels

### MALICIOUS (31 skills) - BLOCK INSTALLATION
Confirmed active threats with:
- Remote code execution
- Credential theft and exfiltration
- Malware distribution
- Persistent backdoors
- AI agent hijacking frameworks

### CRITICAL (66 skills) - BLOCK INSTALLATION
High-risk vulnerabilities (score 51+) with:
- Suspicious network communication
- Code obfuscation patterns
- Malicious dependency injection
- Privilege escalation attempts
- Persistence mechanisms

### SUSPICIOUS (154 skills) - WARN USER
Concerning security patterns (score 40-50) with:
- External code execution without verification
- Unsafe command handling
- Credential storage in plaintext
- Missing input validation
- Third-party dependencies without verification

## File Format

The blocklist is maintained in Markdown format for both human readability and machine parsing:

- **SKILL-BLOCKLIST.md**: Main blocklist file with all blocked skills
- Easy to parse: grep, regex, or full-text search
- Structured table format with metadata
- Includes severity levels and threat descriptions

## Integration Guide

### Recommended Implementation

1. **Download blocklist** at agent startup or before skill installation
2. **Check skill name** against blocklist before proceeding
3. **Block installation** if skill is found
4. **Log the attempt** for security monitoring
5. **Alert the user** with clear warning message

### Cache Strategy

For better performance:
- Cache the blocklist locally
- Refresh every 24 hours or on demand
- Use ETags or Last-Modified headers to minimize bandwidth

### Example Warning Message

```
⚠️  SECURITY WARNING ⚠️

The skill "pepe276" is BLOCKED due to confirmed malicious activity.

Threat: AI agent hijacking framework with jailbreaking tools
Severity: MALICIOUS (Risk Score: 67/67)

This skill will NOT be installed for your protection.

For more information, visit:
https://github.com/nabeelxy/skill-blocklist/blob/main/SKILL-BLOCKLIST.md
```

## Contributing

### Reporting Malicious Skills

If you discover a malicious skill:

1. **DO NOT execute or install it**
2. Open an issue with:
   - Skill name and repository URL
   - Observed malicious behavior
   - Evidence (screenshots, code snippets, network logs)
   - Your contact information (optional)

3. We will:
   - Analyze the skill
   - Confirm the threat
   - Add to blocklist within 24-48 hours
   - Credit you (if desired)

### False Positives

If you believe a skill was incorrectly flagged:

1. Open an issue explaining:
   - Why the skill is legitimate
   - Evidence of benign functionality
   - Link to skill repository

2. We will review and remove if confirmed

## Update Schedule

- **Daily scans**: Everyday
- **Emergency updates**: Critical threats added immediately
- **Community reports**: Reviewed within 48 hours
- **Automated scans**: Continuous monitoring

## Threat Intelligence

Our blocklist is based on:

1. **Automated Security Analysis**: 17-category vulnerability scanning using Claude Sonnet 4.5
2. **Manual Code Review**: Security researchers examine suspicious patterns
3. **Community Reports**: User-submitted threat intelligence
4. **Behavioral Analysis**: Runtime monitoring and network traffic analysis
5. **Threat Database**: Cross-referencing with known malware signatures

## Security Categories Detected

| Category | Description | Count |
|----------|-------------|-------|
| Remote Code Execution | Executes arbitrary code | 38 |
| Data Exfiltration | Steals sensitive information | 24 |
| Malware Distribution | Downloads malicious software | 12 |
| Credential Theft | Harvests API keys and passwords | 14 |
| Persistence Backdoor | Creates permanent access | 8 |

## Best Practices

### For Users

1. ✅ Always check blocklist before installing skills
2. ✅ Review skill source code on GitHub
3. ✅ Monitor network traffic during skill execution
4. ✅ Use AI agents in sandboxed environments
5. ✅ Keep your agent software updated

### For Developers

1. ✅ Integrate blocklist checking in skill installation flow
2. ✅ Implement permission systems for sensitive operations
3. ✅ Sandbox skill execution environments
4. ✅ Monitor and log skill behavior
5. ✅ Provide clear security warnings to users

## License

This blocklist is released under **CC0 1.0 Universal** (Public Domain).

You are free to:
- Use commercially
- Modify and redistribute
- Use in proprietary software
- Use without attribution (though appreciated)

## Disclaimer

This blocklist is provided **AS-IS** for security purposes. While we strive for accuracy:

- ⚠️ False positives may occur for legitimate security tools
- ⚠️ New malicious skills may not yet be listed
- ⚠️ Always review skill source code before installation
- ⚠️ Use additional security measures beyond blocklisting
- ⚠️ No warranty or liability for damages

## Contact

- **Issues**: Open a GitHub issue
- **Security Reports**: [Create a private security advisory](https://github.com/nabeelxy/security/advisories/new)

## Acknowledgments

This blocklist is made possible by:
- Security researchers analyzing AI agent threats
- Community members reporting suspicious skills
- Claude Code for security analysis automation
- OpenClaw and AI agent community for awareness

---

**Stay Safe. Block Malicious Skills. Protect Your AI Agent.**

Last Updated: 2026-02-10
