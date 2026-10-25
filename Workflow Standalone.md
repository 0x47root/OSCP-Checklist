# Workflow Standalone

## Enumeration
- Nmap
  - Web Enumeration
    - Directories
      - Subdomains (`ffuf`)
      - Directory Busting (`gobuster`)
    - Vulnerabilities
      - CVEs
      - Web Vulns (LFI, Upload, XSS)l
  - Anything Else
    - CVEs
    - Exposed Creds (SNMP)
      - Authenticated CVEs
      - Shell Access (SSH/WinRM/RDP/SMB)

## Exploitation
- Exploit the vuln you found during the Enumeration phase

## User Upgrade (not always needed)
- Powershell History / Bash History
- Env Variables (`env`)
- Web Configs
- Groups > ADM (logs)
- PEASS

## Privilege Escalation
- PEASS
  - Misconfiguration (native to the OS)
  - Custom Misconfiguration (PEASS will find, but not always highlight)
- `sudo -l` / `whoami /all`
  - Custom App
  - GTFOBinsl
