
| Port  | Service | Observations                                                                                |
| ----- | ------- | ------------------------------------------------------------------------------------------- |
| 21    | FTP     | Pure-FTPd: Check for weak credentials, anonymous access, or outdated versions.              |
| 22    | SSH     | OpenSSH 7.4: Look for outdated version vulnerabilities or brute-force SSH credentials.      |
| 25/26 | SMTP    | Exim smtpd: Possible vulnerabilities in Exim; test for open relay and CVEs.                 |
| 53    | DNS     | ISC BIND 9.11: Test for DNS zone transfer vulnerabilities or outdated version issues.       |
| 80    | HTTP    | Apache httpd: Check for outdated Apache version, misconfigurations, or exposed directories. |
| 443   | HTTPS   | Apache httpd: Test for SSL/TLS misconfigurations or weak ciphers.                           |
| 110   | POP3    | Dovecot: Test for outdated versions or brute-force credentials.                             |
| 143   | IMAP    | Dovecot: Similar to POP3, test for credentials or version-based exploits.                   |
| 3306  | MySQL   | Check for weak database credentials or access to sensitive data.                            |
### ports to focus on:
- **21 (FTP)**: Can give file system access.
- **22 (SSH)**: Root access risk.
- **80/443 (HTTP/HTTPS)**: Sensitive data exposure.
- **3306 (MySQL)**: Direct access to the database.
### exploitation:
1. **Port 21 (FTP)**:    
    - Check for anonymous login:
        `ftp 111.118.215.174`
        Username: `anonymous`, Password: `<blank>` or `test@test.com`.
    - If successful, search for sensitive files.
2. **Port 22 (SSH)**:
    - Test for weak credentials using a tool like `hydra`:
        hydra -l root -P passwords.txt ssh://111.118.215.174
    - Check for outdated OpenSSH exploits in Metasploit or ExploitDB.
3. **Port 53 (DNS)**:
    - Test for zone transfers (AXFR):
        `dig axfr @111.118.215.174 domain.com`
4. **Ports 80/443 (HTTP/HTTPS)**:
    - Run a vulnerability scanner like Nikto:
        `nikto -h http://111.118.215.174`
    - Test for XSS or SQL injection manually or with Burp Suite.
5. **Port 3306 (MySQL)**:
    - Check for default credentials:
        `mysql -u root -p -h 111.118.215.174`
    - If access is granted, extract databases:
        `SHOW DATABASES;`