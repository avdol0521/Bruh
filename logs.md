## 2 types : 
1. host centric log sources 
2. network centric log sources 
--- 
### Host-Centric Log sources:
### filenames (windows): Windows Event Logs, Sysmon, Osquery etc 
#### stuff it logs: 
- A user accessing a file
- A user attempting to authenticate.
- A process Execution Activity
- A process adding/editing/deleting a registry key or value.
- Powershell execution
### Network-Centric Log sources:
### gets generated when hosts communicate or access the internet to visit a site 
#### stuff it logs:
- SSH connection
- A file being accessed via FTP
- Web traffic
- A user accessing company's resources through VPN.
- Network file sharing Activity
---
## Types based on system type:
### linux log locations:
- /var/log/httpd : Contains HTTP Request  / Response and error logs.
- /var/log/cron   : Events related to cron jobs are stored in this location.
- /var/log/auth.log and /var/log/secure : Stores authentication related logs.  
- /var/log/kern : This file stores kernel related events.