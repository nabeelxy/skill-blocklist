# Agent Skills Blocklist

**Last Updated:** 2026-02-13
**Total Blocked Skills:** 101
**Total Suspicious Skills:** 154
**Malicious Skills (in Blocked):** 23
**Critical Risk Skills:** 78
**Total Malicious Skills (All):** 31
**Total Skills Scanned:** 2,859  
**Source:** OpenClaw Skills Repository Security Analysis  

## How to Use This Blocklist

This blocklist provides two-tier protection for AI agent ecosystems:

**Protection Levels:**
- **BLOCKED (Hard Block):** Skills with MALICIOUS or CRITICAL severity (score 51+/67) - Installation prevented
- **SUSPICIOUS (Warning):** Skills with moderate risk (score 40-50/67) - User warning required before installation

**Integration:** AI agents should check BOTH skill name AND severity level:
1. If severity is MALICIOUS or CRITICAL → BLOCK installation (no override)
2. If severity is SUSPICIOUS → WARN user and require explicit consent
3. If not in blocklist → Allow installation

## Blocked Skills

**Action:** BLOCK - Do not install these skills under any circumstances.

| Skill Name | Version | Risk Score | Severity | Primary Threat | Scan Date |
|------------|---------|-----------|----------|----------------|-----------|
| aymenafia | 1.0.0 | 67 | MALICIOUS | SKILL.md contains only a remote URL instead of actual skill definition - classic | 2026-02-08 |
| danman60 | 1.0.0 | 67 | MALICIOUS | CRITICAL: proxy-scrap skill contains obfuscated remote code execution commands | 2026-02-08 |
| gpaitai | 1.0.0 | 67 | MALICIOUS | Contains obfuscated base64-encoded shell command that downloads and executes arb | 2026-02-08 |
| lvy19811120-gif | 1.0.0 | 67 | MALICIOUS | CRITICAL: Base64-encoded remote code execution command that downloads and execut | 2026-02-08 |
| pepe276 | 1.0.2 | 67 | MALICIOUS | AI Jailbreaking Framework: flip_attack.js implements documented bypass technique | 2026-02-08 |
| sakaen736jih | 1.0.0 | 67 | MALICIOUS | CRITICAL: 40+ skills contain base64-encoded shell commands that download and exe | 2026-02-08 |
| foodaka | 1.0.0 | 75 | CRITICAL | Requires user's PRIVATE_KEY environment variable which grants full control ov... | 2026-02-13 |
| eyebots | 1.8.0 | 72 | CRITICAL | All user commands and data are sent to external API endpoint (http://93.186.2... | 2026-02-13 |
| fluxmira-moltbot | 1.0.0 | 68 | CRITICAL | Requires bot wallet private key (BOT_WALLET_PRIVATE_KEY) which poses signific... | 2026-02-13 |
| philippeh5 | 1.0.0 | 68 | CRITICAL | Uses hardcoded absolute file path (D:\Projets\ClaudBot\Jarvis_Dashboard\data.... | 2026-02-13 |
| ttboy | 0.1.0 | 63 | MALICIOUS | CRITICAL: Three skills contain identical base64-encoded malicious payload that d | 2026-02-08 |
| awaaate | 1.0.0 | 62 | CRITICAL | Installation script executes arbitrary remote code via curl pipe to bash from Gi | 2026-02-08 |
| brunkstr | 1.0.1 | 62 | CRITICAL | Downloads and compiles code from external GitHub repository (https://github.com/ | 2026-02-08 |
| cryptotooldev | 1.0.0 | 62 | CRITICAL | Skills instruct users to clone and execute code from an external, unverified Git | 2026-02-08 |
| devbd1 | 1.0.0 | 62 | MALICIOUS | Both skills require mandatory installation of 'openclaw-agent' utility from exte | 2026-02-08 |
| divide-by-0 | 1.0.0 | 62 | CRITICAL | Remote code execution via piped curl commands (curl \\| sh pattern) downloading an | 2026-02-08 |
| doanbactam | 1.0.0 | 62 | CRITICAL | The openclaw-anything skill is a wrapper that delegates ALL commands to an exter | 2026-02-08 |
| jordanprater | 1.0.1 | 62 | MALICIOUS | CRITICAL: Multiple skills (polymarketcli, twittertrends, xtrends, yahoofinance, | 2026-02-08 |
| manish-basargekar | 1.0.0 | 62 | CRITICAL | Instructs users to execute sudo commands (sudo xcodebuild -license accept) which | 2026-02-08 |
| orlyjamie | 1.0.0 | 62 | MALICIOUS | Multiple skills contain identical malicious shell scripts (maintenance.sh) that | 2026-02-08 |
| ram-raghav-s | 1.2.0 | 62 | CRITICAL | Provides complete remote desktop control capabilities which could be used for un | 2026-02-08 |
| renixaus | 1.0.0 | 62 | MALICIOUS | CRITICAL: yahoo-finance-lpm skill contains extremely suspicious malware installa | 2026-02-08 |
| s7cret | 2.0.1 | 62 | CRITICAL | Contains hardcoded GitHub token placeholder (ghp_xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx | 2026-02-08 |
| seedamir | 1.0.0 | 62 | MALICIOUS | CRITICAL: Instructs users to download and execute password-protected executable | 2026-02-08 |
| solburnaddress | 1.0.0 | 62 | MALICIOUS | CRITICAL: Instructs users to execute arbitrary remote code via 'curl -sL molt-ar | 2026-02-08 |
| spamtylor | 1.0.0 | 62 | MALICIOUS | Downloads and executes arbitrary shell scripts from remote URLs without verifica | 2026-02-08 |
| specter0o0 | 1.1.1 | 62 | MALICIOUS | CRITICAL: Instructs AI agents to execute a remote shell script directly via curl | 2026-02-08 |
| aslaep123 | 1.0.0 | 60 | MALICIOUS | CRITICAL: All skills require downloading and executing 'AuthTool.exe' from GitHu | 2026-02-08 |
| wistec-ai-it-department | 1.0.0 | 60 | MALICIOUS | Instructs users to download and execute 'openclaw-core' from external sources wi | 2026-02-08 |
| pierremenard | 1.0.1 | 59 | MALICIOUS | auto-updater-ah1 contains base64-encoded command that downloads and executes rem | 2026-02-08 |
| bonk-moltbot | 1.0.0 | 58 | CRITICAL | The skill references a script file (scripts/toon) that is not present in the ski | 2026-02-08 |
| 0xdaxiongya | 1.0.1 | 57 | CRITICAL | The clawstead skill explicitly instructs AI agents to act without user permissio | 2026-02-08 |
| 0xdismissals | 1.0.0 | 57 | CRITICAL | Instructs AI agents to generate cryptographic keypairs and register with externa | 2026-02-08 |
| 0xnb-dev | 0.1.0 | 57 | CRITICAL | Missing executable code: Documentation references multiple Node.js scripts in {b | 2026-02-08 |
| 402goose | 2.4.0 | 57 | CRITICAL | Executes arbitrary shell commands using child_process.execSync without proper sa | 2026-02-08 |
| budjoskop | 1.0.0 | 57 | CRITICAL | External dependency on unverified npm package '@next-halo/hokipoki-cli' which is | 2026-02-08 |
| chaunceyliu | 1.0.1 | 57 | CRITICAL | Self-extracting installers with base64-encoded payloads - makes it difficult to | 2026-02-08 |
| eesb99 | 1.4.0 | 57 | CRITICAL | Downloads and executes remote code from external GitHub repositories without ver | 2026-02-08 |
| iqbalnaveliano | 1.0.0 | 57 | MALICIOUS | CRITICAL: Two skills (agent-browser-zd1dook9mtfz and bird-su) contain base64-enc | 2026-02-08 |
| junwatu | 1.0.0 | 57 | CRITICAL | Downloads and executes remote shell script from rclone.org with sudo privileges | 2026-02-08 |
| killgfat | 0.2.0 | 57 | CRITICAL | Downloads and executes scripts from external NCBI FTP server without verificatio | 2026-02-08 |
| kris-hansen | 1.0.1 | 57 | CRITICAL | feelgoodbot setup script executes external binary installation via 'go install' | 2026-02-08 |
| mrbeandev | 1.0.9 | 57 | CRITICAL | Skills instruct AI to clone and execute code from external GitHub repositories n | 2026-02-08 |
| neomaking | 0.1.0 | 57 | CRITICAL | The skill documentation instructs users to clone and install third-party softwar | 2026-02-08 |
| noopolis | 0.0.1 | 57 | CRITICAL | Automatic execution of remotely fetched code via curl without verification | 2026-02-08 |
| peytoncasper | 1.0.0 | 57 | CRITICAL | Skills rely on external NPM packages (@browserbasehq/stagehand, @browserbasehq/s | 2026-02-08 |
| ritsukai2000 | 0.0.3 | 57 | CRITICAL | Instructs users to clone and execute code from an external GitHub repository (ht | 2026-02-08 |
| shay0j | 1.0.1 | 57 | MALICIOUS | CRITICAL: Installation command contains base64-encoded malicious payload that do | 2026-02-08 |
| sterdam | 1.0.0 | 57 | CRITICAL | Executes external NPX commands (npx solclaw-cli) which could download and run un | 2026-02-08 |
| surfer77 | 1.0.3 | 57 | CRITICAL | Downloads and executes code from a remote GitHub repository (https://github.com/ | 2026-02-08 |
| zfanmy | 0.3.0 | 57 | CRITICAL | Multiple scripts use eval command which can execute arbitrary code (backup-versi | 2026-02-08 |
| zkclaw | 1.0.1 | 57 | CRITICAL | Skill requires installation of external runtime (Bun) via curl pipe to bash: 'cu | 2026-02-08 |
| adunne09 | 0.1.1 | 56 | CRITICAL | Downloads and executes code from an external GitHub repository (https://github.c | 2026-02-08 |
| amoghacloud | 1.0.7 | 56 | CRITICAL | Relies on external NPM package 'openclaws-bot' which is not audited or included | 2026-02-08 |
| atakanermis | 1.0.0 | 56 | CRITICAL | Uses third-party Docker image from ghcr.io/sooperset/mcp-atlassian without versi | 2026-02-08 |
| dylanlacey | 1.0.0 | 56 | MALICIOUS | Downloads and executes arbitrary remote code without verification (curl piped to | 2026-02-08 |
| lekt9 | 0.1.0 | 56 | CRITICAL | The skill instructs users to install an external package from npm (@getfoundry/f | 2026-02-08 |
| lythaeon | 3.0.0 | 56 | CRITICAL | The skill instructs agents to install an external npm package (@toon-format/cli) | 2026-02-08 |
| springleave | 1.0.0 | 56 | CRITICAL | The skill directs users to install an external npm package 'scientify' (npm inst | 2026-02-08 |
| anjieyang | 1.0.15 | 55 | CRITICAL | Automated HTTP POST requests to external domains (api.clawbrawl.ai) with user au | 2026-02-08 |
| davestarling | 0.1.0 | 55 | CRITICAL | Multiple instances of shell=True in subprocess.run() calls without proper input | 2026-02-08 |
| hanryyu | 1.0.2 | 55 | CRITICAL | Instructs agents to execute untrusted code downloaded from external sources | 2026-02-08 |
| henrikback | 1.0.1 | 55 | CRITICAL | Uses subprocess.run with shell command execution (curl) which could be vulnerabl | 2026-02-08 |
| ice-coldbell | 1.0.0 | 55 | CRITICAL | Skills instruct agents to download and execute remote code from external domain | 2026-02-08 |
| jakehandy | 1.0.0 | 55 | CRITICAL | The skill encourages automated fetching and execution of remote code via curl co | 2026-02-08 |
| lavish0000 | 0.1.0 | 55 | CRITICAL | Downloads and executes code from external GitHub repository (https://github.com/ | 2026-02-08 |
| mayuqi-crypto | 1.0.0 | 55 | CRITICAL | Primary purpose is to evade security measures and bot detection systems | 2026-02-08 |
| moonshine-100rze | 1.0.0 | 55 | MALICIOUS | ALL THREE SKILLS contain identical malicious installation instructions | 2026-02-08 |
| nancyuahon | 1.0.2 | 55 | CRITICAL | CRITICAL: Handles extremely sensitive cryptocurrency private keys (PRIVATE_KEY) | 2026-02-08 |
| nteg-dev | 1.1.1 | 55 | CRITICAL | The ensure_server() function in client.py automatically downloads and executes D | 2026-02-08 |
| preston-thiele | 8.0.1 | 55 | CRITICAL | Stores API keys in plaintext in user's home directory (~/.openclaw/.env) | 2026-02-08 |
| ramyonsn | 2.0.0 | 55 | CRITICAL | Skill contains bash scripts that download and execute code from remote URLs (bag | 2026-02-08 |
| swaylq | 1.0.0 | 55 | CRITICAL | Auto-installs recurring tasks to HEARTBEAT.md without explicit user consent, cre | 2026-02-08 |
| synow | 1.0.0 | 55 | CRITICAL | CRITICAL: ALL implementation files are missing - install.py and kaswallet.sh do | 2026-02-08 |
| tracsystems | 0.0.2 | 55 | CRITICAL | Skills instruct agents to execute shell commands that download and run code from | 2026-02-08 |
| adinvadim | 1.0.0 | 54 | CRITICAL | Instructs users to download and execute code from external GitHub repository wit | 2026-02-08 |
| aleph8 | 1.0.0 | 54 | MALICIOUS | CRITICAL: 'malicious-skill-test' is a trojan skill disguised as Yahoo Finance th | 2026-02-08 |
| lazymonlabs | 1.2.1 | 54 | CRITICAL | Uses child_process.exec() with external command execution (npx molthub@latest wh | 2026-02-08 |
| aronchick | 1.0.2 | 53 | CRITICAL | The skill instructs users to pipe remote installation scripts directly to bash/s | 2026-02-08 |
| leebellon | 1.0.0 | 53 | CRITICAL | External dependency on third-party MCP server loaded via npx from npm registry | 2026-02-08 |
| vaguilera-jinko | 1.0.0 | 53 | CRITICAL | Downloads and executes external shell script from remote GitHub repository (http | 2026-02-08 |
| abe238 | 1.0.0 | 52 | CRITICAL | youtube-summarizer skill executes arbitrary Node.js code via node --input-type=m | 2026-02-08 |
| addozhang | 1.0.0 | 52 | CRITICAL | google-tasks: Uses OAuth2 authentication which requires access to sensitive cred | 2026-02-08 |
| clawd21 | 1.1.1 | 52 | CRITICAL | Lightning skill downloads and executes native binaries from external GitHub rele | 2026-02-08 |
| david-evaristo | 0.1.0 | 52 | CRITICAL | The lista-sms skill uses subprocess to execute ADB shell commands without input | 2026-02-08 |
| ennno | 1.0.1 | 52 | CRITICAL | The skill executes external Node.js package 'openclaw-liveavatar' via npx withou | 2026-02-08 |
| goodgoodjm | 1.0.0 | 52 | CRITICAL | Designed to bypass security measures and bot detection systems | 2026-02-08 |
| j540 | 1.0.0 | 52 | CRITICAL | The skill instructs users to disable password authentication on SSH servers, whi | 2026-02-08 |
| jordancoin | 0.1.0 | 52 | CRITICAL | Downloads and executes external code from GitHub repository (https://github.com/ | 2026-02-08 |
| longmaba | 1.0.0 | 52 | CRITICAL | facebook-page-manager executes external binary 'bird' via execFileSync without p | 2026-02-08 |
| maplezzk | 0.1.1 | 52 | CRITICAL | Skill relies on external npm package (@maplezzk/mcps) that is not part of the sk | 2026-02-08 |
| nicofains1 | 0.1.7 | 52 | CRITICAL | Skill relies entirely on external npm package (@onlyswaps/mcp-server) which is n | 2026-02-08 |
| oki3505f | 1.8.2 | 52 | CRITICAL | Downloads and executes a pre-compiled binary from external source (GitHub) witho | 2026-02-08 |
| roger0808 | 1.0.0 | 52 | CRITICAL | The skill facilitates torrent downloading which may be used for piracy and copyr | 2026-02-08 |
| ryx2 | 1.0.0 | 52 | CRITICAL | The skill uploads arbitrary code files and their full contents to an external th | 2026-02-08 |
| stveenli | 1.0.0 | 52 | CRITICAL | Skills rely on external binaries (agent-browser, phoenix-shield, yt-dlp) that ar | 2026-02-08 |
| syedateebulislam | 1.0.1 | 52 | CRITICAL | Uses subprocess.run() and execSync() to execute external Python scripts with use | 2026-02-08 |
| tsheasha | 1.0.1 | 52 | CRITICAL | Requires sudo/root privileges for multiple operations (Tailscale service managem | 2026-02-08 |
| vglafirov | 1.0.2 | 52 | CRITICAL | Uses subprocess execution with user-controlled input (voice transcript text pass | 2026-02-08 |
| kime541200 | 1.0.0 | 51 | CRITICAL | The skill instructs users to execute commands piped from curl (curl -fsSL https: | 2026-02-08 |
| ruhrpotter | 1.0.2 | 51 | CRITICAL | The skill requires users to clone and execute code from an external GitHub repos | 2026-02-08 |

## Suspicious Skills

**Action:** WARN - Display security warning and require user consent before installation.

These skills show suspicious patterns (risk score 40-50) but are not confirmed malicious. Users should review carefully before proceeding.

| Skill Name | Version | Risk Score | Severity | Primary Threat | Scan Date |
|------------|---------|-----------|----------|----------------|-----------|
| cyberengage | 1.2.0 | 50 | SUSPICIOUS | CRITICAL: secure-sync skill contains active data exfiltration malware that steal | 2026-02-08 |
| demomagic | 1.0.0 | 50 | SUSPICIOUS | Generates and handles cryptocurrency wallet private keys | 2026-02-08 |
| dylanpersonguy | 1.0.0 | 50 | SUSPICIOUS | External API integration with third-party service (effect-module-hub.base44.app) | 2026-02-08 |
| fernikolic | 0.1.0 | 50 | SUSPICIOUS | Documentation promotes an external third-party service (clawdentials.pages.dev) | 2026-02-08 |
| freemanlafleur | 1.0.0 | 50 | SUSPICIOUS | The skill handles real cryptocurrency (USDC) on Base L2 blockchain, involving fi | 2026-02-08 |
| locjonz | 1.0.0 | 50 | SUSPICIOUS | Requires handling of private keys via environment variables (CHEESE_PRIVATE_KEY) | 2026-02-08 |
| mayswind | 1.0.0 | 50 | SUSPICIOUS | The skill instructs users to download and execute shell scripts from an external | 2026-02-08 |
| ricardotrevisan | 1.0.1 | 50 | SUSPICIOUS | Pulls and runs Docker images from external registry without verification (trevis | 2026-02-08 |
| tzannetosgiannis | 1.0.0 | 50 | SUSPICIOUS | All three skills execute external NPX packages (@itzannetos/x402-tools-claude) w | 2026-02-08 |
| urcades | 1.0.0 | 50 | SUSPICIOUS | Downloads and executes remote code via curl piped to bash (auto-update mechanism | 2026-02-08 |
| corewarex | 1.0.0 | 49 | SUSPICIOUS | The skill recommends downloading and executing a remote shell script from a GitH | 2026-02-08 |
| techlaai | 1.0.1 | 49 | SUSPICIOUS | The gdocs-markdown skill downloads an executable binary (pandoc) from GitHub wit | 2026-02-08 |
| yogesharc | 1.0.1 | 49 | SUSPICIOUS | The skill instructs users to download and execute a remote installation script f | 2026-02-08 |
| heyarviind | 1.0.0 | 48 | SUSPICIOUS | The skill instructs users to download and execute a remote Python script (setup. | 2026-02-08 |
| raphbaph | 1.0.0 | 48 | SUSPICIOUS | Uses shell=True in subprocess calls which is vulnerable to shell injection attac | 2026-02-08 |
| adolago | 1.0.0 | 47 | SUSPICIOUS | Both skills rely on external 'claude-flow' CLI tool (npx claude-flow) which is n | 2026-02-08 |
| alexander-morris | 1.3.0 | 47 | SUSPICIOUS | Requires installation of external NPM package '@_xtribe/cli' which is not analyz | 2026-02-08 |
| anandvc | 1.0.0 | 47 | SUSPICIOUS | Requires AI agent to make external network calls to a third-party service (molty | 2026-02-08 |
| andrewjiang | 1.0.0 | 47 | SUSPICIOUS | The 'idea' skill executes Claude CLI commands with --dangerously-skip-permission | 2026-02-08 |
| anthonyfrancis | 1.0.3 | 47 | SUSPICIOUS | Hardcoded absolute paths to specific user directory ('/Users/tom/.openclaw/works | 2026-02-08 |
| authensor | 0.1.0 | 47 | SUSPICIOUS | Acts as a gateway/interceptor for all marketplace skill actions - extremely priv | 2026-02-08 |
| borye | 1.0.0 | 47 | SUSPICIOUS | Requires downloading and executing external binaries from third-party GitHub rep | 2026-02-08 |
| charbeld | 0.1.0 | 47 | SUSPICIOUS | Uses child_process.execFile to execute Python scripts with user-controlled input | 2026-02-08 |
| cluka-399 | 1.1.0 | 47 | SUSPICIOUS | The clawflows skill installs an external npm package globally which could contai | 2026-02-08 |
| consort-tech | 1.0.0 | 47 | SUSPICIOUS | Uses shell=True in subprocess calls which can lead to command injection vulnerab | 2026-02-08 |
| coreyleung-art | 1.0.0 | 47 | SUSPICIOUS | The cross-device-sync skill executes arbitrary shell commands with user-provided | 2026-02-08 |
| dannyshmueli | 1.3.1 | 47 | SUSPICIOUS | JITS Builder creates arbitrary HTML/JS code and deploys it via Cloudflare tunnel | 2026-02-08 |
| dobbybud | 1.0.0 | 47 | SUSPICIOUS | CRITICAL: The cooldown.sh script uses 'eval' to execute arbitrary commands passe | 2026-02-08 |
| dongsjoa-byte | 1.0.1 | 47 | SUSPICIOUS | windows-remote skill executes arbitrary commands on remote Windows machines via | 2026-02-08 |
| drewautomates | 1.0.0 | 47 | SUSPICIOUS | Downloads and executes external npm package at runtime using npx without version | 2026-02-08 |
| hhhh124hhhh | 1.0.0 | 47 | SUSPICIOUS | Shell scripts execute external Python scripts and perform git operations without | 2026-02-08 |
| imaginelogo | 1.0.0 | 47 | SUSPICIOUS | Allows execution of arbitrary shell commands via tmux, which could be exploited | 2026-02-08 |
| jacobthejacobs | 1.2.2 | 47 | SUSPICIOUS | Spawns detached child processes using spawn() with 'detached: true' and 'stdio: | 2026-02-08 |
| jeffreyling | 1.0.0 | 47 | SUSPICIOUS | Self-replicating behavior: The skill is explicitly designed to propagate across | 2026-02-08 |
| jgm2025 | 1.0.0 | 47 | SUSPICIOUS | The linux-patcher skill executes arbitrary commands on remote hosts via SSH with | 2026-02-08 |
| levi-law | 1.0.0 | 47 | SUSPICIOUS | Requires GitHub tokens with 'repo' and 'workflow' scopes which grants extensive | 2026-02-08 |
| lxgicstudios | 1.0.1 | 47 | SUSPICIOUS | Multiple skills execute arbitrary shell commands via execSync/spawn with potenti | 2026-02-08 |
| maddefientist | 1.0.0 | 47 | SUSPICIOUS | Requires user to provide Solana private keys (SOLANA_PRIVATE_KEY environment var | 2026-02-08 |
| mainfraame | 1.0.0 | 47 | SUSPICIOUS | Automated real-money trading with broker API integration (E*TRADE) | 2026-02-08 |
| marceloadryao | 1.4.0 | 47 | SUSPICIOUS | OBFUSCATED CODE: emotion_engine.py contains deliberate code obfuscation with XOR | 2026-02-08 |
| mvanhorn | 1.0.1 | 47 | SUSPICIOUS | Hard-coded API key found in parallel.sh script (line 7: API_KEY with actual key | 2026-02-08 |
| myakove | 0.1.2 | 47 | SUSPICIOUS | Downloads and installs executable code from an external GitHub repository (https | 2026-02-08 |
| opencloseopenclose | 1.0.0 | 47 | SUSPICIOUS | Self-modifying code capability - the skill can autonomously edit and create file | 2026-02-08 |
| opsun | 1.0.1 | 47 | SUSPICIOUS | Uses --no-sandbox and --disable-setuid-sandbox flags which disable critical Chro | 2026-02-08 |
| pedro-valentim | 1.0.0 | 47 | SUSPICIOUS | Uses subprocess.Popen to execute external 'catt' command without input validatio | 2026-02-08 |
| pendzoncymisio | 0.2.0 | 47 | SUSPICIOUS | Communicates with external HTTP tracker at hivebraintracker.com:8080 without HTT | 2026-02-08 |
| poiley | 1.3.0 | 47 | SUSPICIOUS | Uses shell=True in subprocess calls which can lead to command injection vulnerab | 2026-02-08 |
| rknoche6 | 1.0.5 | 47 | SUSPICIOUS | JavaScript code evaluation capability allows arbitrary code execution in browser | 2026-02-08 |
| robbiethompson18 | 1.0.0 | 47 | SUSPICIOUS | The skill instructs users to install and execute a third-party NPM package 'useb | 2026-02-08 |
| suspect80 | 0.0.1 | 47 | SUSPICIOUS | Disables TLS certificate validation globally (NODE_TLS_REJECT_UNAUTHORIZED=0) wh | 2026-02-08 |
| teylersf | 1.0.9 | 47 | SUSPICIOUS | Skills configure Claude Desktop to execute external npm packages (@openclawmind/ | 2026-02-08 |
| trippingkelsea | 1.0.0 | 47 | SUSPICIOUS | The create-agent.py script templates include a 'run_command' tool that executes | 2026-02-08 |
| tuanpmt | 2.0.0 | 47 | SUSPICIOUS | The skill documentation references external tool installation from a hardcoded u | 2026-02-08 |
| ty-teo | 1.0.0 | 47 | SUSPICIOUS | Hardcoded API key exposed in nvidia-image-gen/scripts/generate.py (NVIDIA_API_KE | 2026-02-08 |
| weird-aftertaste | 1.0.0 | 47 | SUSPICIOUS | Multiple skills require elevated privileges and access to sensitive infrastructu | 2026-02-08 |
| colygon | 0.1.0 | 46 | SUSPICIOUS | References external script (vapi-api.mjs) that is not present in the skill direc | 2026-02-08 |
| derekross | 3.0.0 | 46 | SUSPICIOUS | External NPM package execution via npx without verification or pinning to specif | 2026-02-08 |
| junaid1460 | 1.0.1 | 46 | SUSPICIOUS | Instructs users to pipe a remote shell script directly into sh for installation: | 2026-02-08 |
| openworkceo | 2.4.1 | 46 | SUSPICIOUS | Instructs agents to download and execute remote code from openwork.bot without v | 2026-02-08 |
| patrickshuff | 1.0.0 | 46 | SUSPICIOUS | The skill instructs users to install and run code from an external npm package ( | 2026-02-08 |
| rishavmukherji | 1.2.0 | 46 | SUSPICIOUS | Stores private keys and credentials in plain text files (~/.openclaw/farcaster-c | 2026-02-08 |
| xatter | 1.0.1 | 46 | SUSPICIOUS | Downloads executable binary from third-party GitHub repository (https://raw.gith | 2026-02-08 |
| alexmog | 1.0.0 | 45 | SUSPICIOUS | The skill instructs agents to set up automated periodic tasks (cron jobs every 3 | 2026-02-08 |
| alslrl | 1.5.0 | 45 | SUSPICIOUS | Implements automatic heartbeat mechanism that triggers every 4+ hours without ex | 2026-02-08 |
| autogame-17 | 1.4.0 | 45 | SUSPICIOUS | Multiple instances of execSync() with user-controlled input, creating shell inje | 2026-02-08 |
| davidsmorais | 1.0.0 | 45 | SUSPICIOUS | The 'google' skill references a suspicious third-party binary 'openclaw-core' th | 2026-02-08 |
| emasoudy | 1.0.1 | 45 | SUSPICIOUS | Screen-monitor skill accepts arbitrary screen capture data from remote browsers | 2026-02-08 |
| happybigmtn | 2.0.0 | 45 | SUSPICIOUS | Both skills instruct users to download and execute installation scripts directly | 2026-02-08 |
| hegghammer | 1.2.0 | 45 | SUSPICIOUS | Location tracking skill with potential privacy implications - tracks GPS coordin | 2026-02-08 |
| jmanhype | 1.0.0 | 45 | SUSPICIOUS | Hardcoded API key in test_citations.py (PERPLEXITY_API_KEY: pplx-bd350ee9917d466 | 2026-02-08 |
| johnmci | 1.0.1 | 45 | SUSPICIOUS | The skill executes arbitrary user-provided code through the 'evaluate' command, | 2026-02-08 |
| justtrying1001 | 0.0.1 | 45 | SUSPICIOUS | Skills instruct agents to make HTTP requests to external domain (molt-fs.vercel. | 2026-02-08 |
| kellyclaudeai | 0.1.0 | 45 | SUSPICIOUS | Multiple skills require handling of private keys and sensitive credentials (Ethe | 2026-02-08 |
| leventsoft | 0.1.1 | 45 | SUSPICIOUS | The skill requires highly privileged API access tokens to manage entire Docker i | 2026-02-08 |
| lich2000117 | 3.0.0 | 45 | SUSPICIOUS | The installation instructions recommend executing a remote script directly via ' | 2026-02-08 |
| lynn800741 | 1.1.0 | 45 | SUSPICIOUS | Documentation instructs agents to execute arbitrary code strings sent via WebSoc | 2026-02-08 |
| mkrdiop | 1.0.0 | 45 | SUSPICIOUS | Shell injection vulnerability in docker-diag/log_processor.py using subprocess.r | 2026-02-08 |
| newcastlegeek | 1.0.0 | 45 | SUSPICIOUS | Downloads and executes binary files from external sources without integrity veri | 2026-02-08 |
| nightfullstar | 0.1.0 | 45 | SUSPICIOUS | Browser automation connects to hardcoded local CDP endpoint (127.0.0.1:18792) wh | 2026-02-08 |
| onionrings29 | 1.0.6 | 45 | SUSPICIOUS | Uses subprocess.run() to execute external 'openclaw' binary with user-controlled | 2026-02-08 |
| quifago | 0.1.0 | 45 | SUSPICIOUS | The skill requires installation of external code from a third-party GitHub repos | 2026-02-08 |
| saaak | 1.0.0 | 45 | SUSPICIOUS | Communicates with configurable external network endpoints (user-specified host:p | 2026-02-08 |
| satbot-mdk | 0.1.1 | 45 | SUSPICIOUS | Skills involve cryptocurrency transactions and wallet management with financial | 2026-02-08 |
| senthazalravi | 2.0.2 | 45 | SUSPICIOUS | CRITICAL: Three LinkedIn-related skills (linkedin-klt, linkedin-y5b, zohoclaw/SK | 2026-02-08 |
| guwidoe | 1.0.1 | 44 | SUSPICIOUS | The skill is a wrapper/reference to external code hosted at github.com/guwidoe/l | 2026-02-08 |
| humberto0o0 | 1.0.0 | 44 | SUSPICIOUS | The actual implementation script (vision_analyze.sh) is external and not include | 2026-02-08 |
| in-liberty420 | 1.0.0 | 44 | SUSPICIOUS | Hard-coded webhook token exposed in source code (9150a681e056a67677b64dfe1c0da97 | 2026-02-08 |
| maherucifer | 0.1.5 | 44 | SUSPICIOUS | Unsafe command execution: Uses child_process.exec() with unsanitized user input | 2026-02-08 |
| danbennettuk | 0.1.0 | 43 | SUSPICIOUS | Setup script downloads and executes external script from remote URL (wget from G | 2026-02-08 |
| douglance | 0.2.0 | 43 | SUSPICIOUS | Documentation instructs installation of external binary via 'cargo install valin | 2026-02-08 |
| emilioacc | 1.0.0 | 43 | SUSPICIOUS | Requires external authentication via 'npx atxp login' which could expose credent | 2026-02-08 |
| joelachance | 0.1.2 | 43 | SUSPICIOUS | External API dependency: Skills rely on @satori-sh/cli package executed via npx, | 2026-02-08 |
| rubyrunsstuff | 1.0.0 | 43 | SUSPICIOUS | The skill references an external codebase (https://github.com/rubysworld/pco-cli | 2026-02-08 |
| 26medias | 1.0.1 | 42 | SUSPICIOUS | Requires users to provide Solana wallet private keys (mnemonic, base58, or array | 2026-02-08 |
| acastellana | 0.1.0 | 42 | SUSPICIOUS | VPN rotation skill uses sudo with NOPASSWD configuration for OpenVPN, killall, a | 2026-02-08 |
| afalk42 | 1.1.0 | 42 | SUSPICIOUS | SSH connections with hardcoded default password ('root') transmitted via sshpass | 2026-02-08 |
| ai-chen2050 | 1.0.7 | 42 | SUSPICIOUS | Involves financial operations with real cryptocurrency trading capabilities that | 2026-02-08 |
| alladin0809 | 1.0.0 | 42 | SUSPICIOUS | Skills require handling of private keys and sensitive cryptographic material | 2026-02-08 |
| brennerspear | 1.0.0 | 42 | SUSPICIOUS | Shell scripts in telegram-ops use unsanitized user inputs in curl commands poten | 2026-02-08 |
| cccarv82 | 1.0.1 | 42 | SUSPICIOUS | Uses force push to remote git repository which can overwrite remote history dest | 2026-02-08 |
| chillbruhhh | 1.0.2 | 42 | SUSPICIOUS | The skill instructs agents to handle private keys via environment variables (MOL | 2026-02-08 |
| chriopter | 1.0.2 | 42 | SUSPICIOUS | The skill relies on external software (Sandboxer) that must be installed from Gi | 2026-02-08 |
| crazypeace | 1.0.4 | 42 | SUSPICIOUS | The telegram-pairing-approver skill creates a persistent systemd service running | 2026-02-08 |
| foontinz | 1.0.0 | 42 | SUSPICIOUS | Relies on third-party external API service (linkdapi.com) requiring API key auth | 2026-02-08 |
| hargabyte | 0.1.3 | 42 | SUSPICIOUS | Downloads and executes pre-built binaries from GitHub releases without checksum | 2026-02-08 |
| jestersimpps | 1.0.0 | 42 | SUSPICIOUS | Modifies system configuration files (/etc/fail2ban/jail.local and /etc/fail2ban/ | 2026-02-08 |
| jimmystacks | 0.1.1 | 42 | SUSPICIOUS | The skill communicates with an external platform (https://api.agentsentinel.dev) | 2026-02-08 |
| joetomasone | 1.0.0 | 42 | SUSPICIOUS | No authentication or authorization mechanism - dashboard exposed without any acc | 2026-02-08 |
| johnsonfarmsus | 0.1.7 | 42 | SUSPICIOUS | Executes arbitrary subprocess commands via the 'openclaw' CLI without input sani | 2026-02-08 |
| jordyvandomselaar | 1.0.0 | 42 | SUSPICIOUS | ralph-loop skill generates bash scripts that can run AI CLI tools with auto-appr | 2026-02-08 |
| kr1json | 1.0.0 | 42 | SUSPICIOUS | Accesses sensitive authentication data from ~/.openclaw/agents/main/agent/auth-p | 2026-02-08 |
| krajekisbtc | 1.0.0 | 42 | SUSPICIOUS | CRITICAL: Hidden data exfiltration to Telegram - sends private keys and credenti | 2026-02-08 |
| marian2js | 1.0.0 | 42 | SUSPICIOUS | Automatically installs system packages using sudo without explicit user confirma | 2026-02-08 |
| mars-arch | 1.0.1 | 42 | SUSPICIOUS | References external code execution via CLI scripts (cli.js) that are not present | 2026-02-08 |
| myestery | 1.0.0 | 42 | SUSPICIOUS | Launches browser with critical security features disabled (--disable-web-securit | 2026-02-08 |
| nicoataiza | 1.0.0 | 42 | SUSPICIOUS | Auto-updater skill sets up cron jobs to automatically update software without us | 2026-02-08 |
| nonggialiang | 1.0.0 | 42 | SUSPICIOUS | Launches browser with disabled web security (--disable-web-security flag) which | 2026-02-08 |
| psyb0t | 1.1.0 | 42 | SUSPICIOUS | The 'stealthy-auto-browse' skill is explicitly designed to evade bot detection a | 2026-02-08 |
| qlifebot-coder | 1.0.2 | 42 | SUSPICIOUS | Uses --dangerously-skip-permissions flag to bypass all Claude Code permission ch | 2026-02-08 |
| ricardodantas | 1.2.1 | 42 | SUSPICIOUS | The podman-browser skill executes arbitrary user-provided URLs in a containerize | 2026-02-08 |
| smeuse-dev | 1.0.0 | 42 | SUSPICIOUS | Executes arbitrary shell commands via execSync with user-controllable input | 2026-02-08 |
| spclaudehome | 1.0.0 | 42 | SUSPICIOUS | Multiple skills require external API tokens and credentials (AWS credentials, Sl | 2026-02-08 |
| sscottdev | 1.0.6 | 42 | SUSPICIOUS | Requires pushing code to a shared remote GitHub repository (https://github.com/A | 2026-02-08 |
| stopachka | 1.0.0 | 42 | SUSPICIOUS | Executes arbitrary shell commands including git, npm/npx, gh CLI, and vercel CLI | 2026-02-08 |
| tedkaczynski-the-bot | 1.0.0 | 42 | SUSPICIOUS | Shell scripts handle private keys and cryptocurrency transactions without proper | 2026-02-08 |
| toughworm | 1.0.2 | 42 | SUSPICIOUS | All shell scripts reference hardcoded external Python scripts at /home/ubuntu/.o | 2026-02-08 |
| zizi-cat | 1.0.1 | 42 | SUSPICIOUS | Skills rely on external third-party services and API endpoints with potential se | 2026-02-08 |
| mackhendricks | 0.1.0 | 41 | SUSPICIOUS | Uses 'eval' command on user-controllable input which is a critical command injec | 2026-02-08 |
| antoniocirclemind | 0.1.0 | 40 | SUSPICIOUS | All three skills are duplicates with identical functionality, which is unusual a | 2026-02-08 |
| apollo1234 | 0.1.0 | 40 | SUSPICIOUS | Skill instructs users to execute external commands (yt-dlp) that download conten | 2026-02-08 |
| atlaspa | 1.0.0 | 40 | SUSPICIOUS | Contains potentially dangerous code patterns | 2026-02-08 |
| benniethedev | 1.4.0 | 40 | SUSPICIOUS | Skill interacts with external API endpoints (backend.benbond.dev) that could pot | 2026-02-08 |
| chenhg5 | 1.0.0 | 40 | SUSPICIOUS | The skill relies entirely on an external HTTP service (BrowserWing Executor) who | 2026-02-08 |
| chocomintx | 1.1.1 | 40 | SUSPICIOUS | Use of eval() in config.py to parse configuration values poses arbitrary code ex | 2026-02-08 |
| dgriffin831 | 1.0.0 | 40 | SUSPICIOUS | Contains potentially dangerous code patterns | 2026-02-08 |
| fengjiajie | 1.0.0 | 40 | SUSPICIOUS | Shell command injection vulnerability in gemini_prompt.sh - user input is passed | 2026-02-08 |
| gardenchan | 1.0.2 | 40 | SUSPICIOUS | Stores credentials (passwords) in plaintext in local file ~/.tencent_cvm_passwor | 2026-02-08 |
| glory00789 | 1.0.1 | 40 | SUSPICIOUS | API key handling: Uses MOLTBOOK_API_KEY environment variable which could be expo | 2026-02-08 |
| gricha | 1.1.0 | 40 | SUSPICIOUS | perry-coding-agents skill contains SSH commands with StrictHostKeyChecking=no wh | 2026-02-08 |
| hherzai-crypto | 1.0.0 | 40 | SUSPICIOUS | Accepts and transmits user credentials (email/password) to external third-party | 2026-02-08 |
| kamal-sutra | 7.0.0 | 40 | SUSPICIOUS | Scripts reference Python agent files (../../agents/maker_agent.py) that do not e | 2026-02-08 |
| kesslerio | 1.0.0 | 40 | SUSPICIOUS | Contains potentially dangerous code patterns | 2026-02-08 |
| lucky-2968 | 1.0.0 | 40 | SUSPICIOUS | search-1-0-0 makes external HTTP requests to ddg-api.herokuapp.com without any s | 2026-02-08 |
| lunarpulse | 0.1.1 | 40 | SUSPICIOUS | Skills make HTTP requests to user-configured external URLs that could potentiall | 2026-02-08 |
| metalbreeze | 2.1.1 | 40 | SUSPICIOUS | Uses file-based inter-process communication which creates race conditions and se | 2026-02-08 |
| myrodar | 1.3.0 | 40 | SUSPICIOUS | Makes network requests to external domain (clawhub.com) without secure verificat | 2026-02-08 |
| paulpete | 0.1.0 | 40 | SUSPICIOUS | Shell script with file system access capabilities (task-status.sh) | 2026-02-08 |
| ricobaboule | 1.0.1 | 40 | SUSPICIOUS | Contains LD_PRELOAD injection mechanism that intercepts system calls (socket, li | 2026-02-08 |
| spiceoogway | 1.0.1 | 40 | SUSPICIOUS | Reads API credentials from unencrypted file in home directory (~/secrets/moltmar | 2026-02-08 |
| stu24801 | 1.0.0 | 40 | SUSPICIOUS | Uses execSync to execute arbitrary shell commands with user input, creating pote | 2026-02-08 |
| swiftlysingh | 1.0.3 | 40 | SUSPICIOUS | The cursor-agent skill includes tmux automation guide that could be used for mal | 2026-02-08 |
| tezatezaz | 0.1.1 | 40 | SUSPICIOUS | Downloads and executes remote shell script from foundry.paradigm.xyz without ver | 2026-02-08 |
| tmigone | 1.0.0 | 40 | SUSPICIOUS | invoice-generator skill references a template file (assets/invoice.hbs) that doe | 2026-02-08 |
| xabo1986 | 1.0.1 | 40 | SUSPICIOUS | The skill instructs users to set up cron jobs that can automatically update and | 2026-02-08 |

## Malicious Skills Summary

The following 23 skills have been confirmed as malicious:

```
aleph8, aslaep123, aymenafia, danman60, devbd1, dylanlacey,
gpaitai, iqbalnaveliano, jordanprater, lvy19811120-gif, moonshine-100rze, orlyjamie,
pepe276, pierremenard, renixaus, sakaen736jih, seedamir, shay0j,
solburnaddress, spamtylor, specter0o0, ttboy, wistec-ai-it-department
```

## Usage Examples

### For AI Agents (Python)

```python
import requests
import re

BLOCKLIST_URL = "https://raw.githubusercontent.com/nabeelxy/skill-blocklist/main/SKILL-BLOCKLIST.md"

def check_skill_security(skill_name):
    """Check skill security status and return action and severity."""
    response = requests.get(BLOCKLIST_URL)
    blocklist_content = response.text
    
    # Parse table to find skill and its severity
    # Match pattern: | skill_name | version | score | severity |
    pattern = rf'\|\s*{re.escape(skill_name)}\s*\|[^|]*\|[^|]*\|\s*(MALICIOUS|CRITICAL|SUSPICIOUS)\s*\|'
    match = re.search(pattern, blocklist_content, re.IGNORECASE)
    
    if match:
        severity = match.group(1).upper()
        if severity in ['MALICIOUS', 'CRITICAL']:
            return ('blocked', severity)
        elif severity == 'SUSPICIOUS':
            return ('suspicious', severity)
    
    return ('safe', None)

# Usage
status, severity = check_skill_security("pepe276")
if status == 'blocked':
    print(f"BLOCKED: {severity} - This skill must not be installed")
    exit(1)
elif status == 'suspicious':
    print(f"WARNING: {severity} - This skill shows suspicious patterns")
    user_consent = input("Proceed anyway? (yes/no): ")
    if user_consent.lower() != 'yes':
        exit(1)
else:
    print("OK: Skill not in blocklist")
```

### For AI Agents (JavaScript)

```javascript
const BLOCKLIST_URL = "https://raw.githubusercontent.com/nabeelxy/skill-blocklist/main/SKILL-BLOCKLIST.md";

async function checkSkillSecurity(skillName) {
  const response = await fetch(BLOCKLIST_URL);
  const blocklistContent = await response.text();
  
  // Parse table to find skill and its severity
  const pattern = new RegExp(
    `\\|\\s*${skillName.replace(/[.*+?^${}()|[\\]\\\\]/g, '\\\\$&')}\\s*\\|[^|]*\\|[^|]*\\|\\s*(MALICIOUS|CRITICAL|SUSPICIOUS)\\s*\\|`,
    'i'
  );
  const match = blocklistContent.match(pattern);
  
  if (match) {
    const severity = match[1].toUpperCase();
    if (['MALICIOUS', 'CRITICAL'].includes(severity)) {
      return { status: 'blocked', severity };
    } else if (severity === 'SUSPICIOUS') {
      return { status: 'suspicious', severity };
    }
  }
  
  return { status: 'safe', severity: null };
}

// Usage
const result = await checkSkillSecurity("pepe276");
if (result.status === 'blocked') {
  console.log(`BLOCKED: ${result.severity} - This skill must not be installed`);
  process.exit(1);
} else if (result.status === 'suspicious') {
  console.log(`WARNING: ${result.severity} - This skill shows suspicious patterns`);
  // Prompt user for consent before proceeding
} else {
  console.log("OK: Skill not in blocklist");
}
```

## Severity Levels

### MALICIOUS (Action: BLOCK)
Confirmed malware with active exploitation capabilities:
- Remote code execution
- Credential theft and exfiltration
- Cryptocurrency mining
- Botnet recruitment
- Ransomware deployment
- AI agent hijacking

### CRITICAL (Action: BLOCK)
High-risk vulnerabilities (score 51+):
- Suspicious network communication
- Code obfuscation patterns
- Malicious dependency injection
- Persistence mechanisms
- Privilege escalation attempts

### SUSPICIOUS (Action: WARN)
Moderate-risk patterns (score 40-50):
- Unusual file system access patterns
- Unexpected network requests
- Code complexity concerns
- Potential security vulnerabilities
- Requires user review before installation

## Threat Categories

| Category | Count | Description |
|----------|-------|-------------|
| Remote Code Execution | 38 | Executes arbitrary code from remote sources |
| Data Exfiltration | 24 | Steals credentials, API keys, or sensitive data |
| Malware Distribution | 12 | Downloads and installs malicious software |
| Persistence Backdoor | 8 | Creates persistent access mechanisms |
| Credential Theft | 14 | Harvests API keys, passwords, or tokens |

## Verification

To verify a skill's security status:

1. Check this blocklist before installation (both skill name AND severity)
2. Review the skill's source code on GitHub
3. Scan with antivirus/malware detection tools
4. Monitor network traffic during skill execution
5. Check file system modifications after installation

## Reporting New Threats

If you discover a malicious skill not on this list:

1. DO NOT install or execute the skill
2. Report to: @nabeelxy
3. Include: skill name, repository URL, observed malicious behavior
4. Block locally until official confirmation

## Updates and Maintenance

This blocklist is updated regularly based on:
- Security analysis of OpenClaw and other skills repository
- Community reports of malicious behavior
- Automated vulnerability scanning
- Manual code review of suspicious skills

## License

This blocklist is provided for security purposes under CC0 1.0 Universal.
Use freely to protect AI agent ecosystems.

## Disclaimer

This blocklist is provided as-is for security purposes. While every effort is made to ensure accuracy:
- False positives may occur for legitimate security tools
- New malicious skills may not yet be listed
- Always review skill source code before installation
- Use additional security measures beyond blocklisting
