# Workflow AD

## Nothing Enumeration
- No Creds
  - Null/Guest Authentication
    - File shares (`nxc`)
    - `ldapdomaindump`
    - Responder
- Handle like Standalone machine

## Initial Foothold
- Vulnerability
  - CVEs
  - Web Vulns (Upload, XSS, LFI, RFI)
- Creds (Assumed Breach)

## Internal Enumeration
- Dual-homed > setup a pivot (`chisel`/`ligolo-ng`)
  - 192.168.x.x > External
  - 10.10.x.x > Internal (AD-network)
 
## Lateral Movement
- User 'john' finds creds on dual-homed machine
- Sprays them against all services using `nxc` > RDP access
- Local Admin in dual-homed machine?
  - `secretsdump` / `mimikatz`
  - Hash found? > spray services using `nxc` (smb|ldap|winrm|rdp|mssql|ssh)
- Access to other machine? > Repeat Enumeration

## Vertical Movement / Post Exploitation
- Example: DA hash found? > Login to DC
- Now Post-Exploitation begins
  - Dump secrets (`secretsdump`, secrets of all the domain, NTDS.dit)
  - Try to crack hashes with `hashcat`
  - Golden Ticket / Cleanup (not needed for exam)
