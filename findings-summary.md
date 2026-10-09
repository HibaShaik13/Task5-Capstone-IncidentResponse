# Consolidated Findings — DVWA / Metasploitable2 Pentest

| Severity | Finding | Source Task | Evidence |
|---|---|---|---|
| Critical | vsFTPd 2.3.4 backdoor (CVE-2011-2523) — remote root via Metasploit | Task 2 / Task 4 | Meterpreter session opened, getuid = root |
| Critical | SQL Injection in DVWA — full user table + MD5 hashes extracted | Task 3 | UNION SELECT payload, screenshot captured |
| High | Stored & Reflected XSS — guestbook and name fields | Task 3 | `<script>alert()</script>` executed, screenshot captured |
| High | Weak default SSH credential (msfadmin:msfadmin) | Task 4 | Direct SSH login succeeded |
| Medium | CSRF — password change via crafted URL, no token | Task 3 | Vulnerable URL screenshot |
| Medium | Local File Inclusion — /etc/passwd readable via DVWA | Task 3 | `?page=../../../../../../etc/passwd` |
| Low | Missing security headers (X-Frame-Options, CSP, X-Content-Type-Options) | Task 3 | curl -I header inspection |

## Recon / Scanning Re-Verification (Capstone)
ping -c 4 192.168.56.102
nmap -sV -O 192.168.56.102
→ Confirmed target state unchanged from Task 2 baseline; vsFTPd 2.3.4, Samba,
  UnrealIRCd, outdated Linux 2.6.x kernel all still present.

## Mitigations
- Parameterize all DB queries (prevent SQLi)
- Encode/escape all user output (prevent XSS)
- Add anti-CSRF tokens to state-changing requests
- Validate/allow-list file-inclusion parameters
- Patch or remove vsFTPd 2.3.4
- Enforce strong credentials, disable default accounts
- Add standard security headers
- Deploy rate-limiting / IDS for SYN flood detection
