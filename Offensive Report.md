# Red Team: Summary of Operations

## Table of Contents
- Exposed Services
- Critical Vulnerabilities
- Exploitation

### Exposed Services

Nmap scan results for each machine reveal the below services and OS details:

```bash
 $ nmap -sV 192.168.1.110
  ```
 ![nmap1](/Screenshots/Capture1.JPG)
 
```bash
 $ nmap --script vuln 192.168.1.110
  ```
  ![nmap1](/Screenshots/Vulnerabilities.JPG)

This scan identifies the services below as potential points of entry:
- Target 1
  - 22/tcp ssh Potential remote shell, brute force/dictionary attacks
  - 80/tcp http Potential command injection, brute force/dictionary attack
  - 111/tcp rpcbind Potential recon and file upload/download

The following vulnerabilities were identified on each target:
- Target 1
  - Weak passwords
  - MySQL Db vulnerability
  - Privilege escalation using Python

### Exploitation

The Red Team was able to penetrate `Target 1` and retrieve the following confidential data:
- Target 1
  - `flag1.txt`:  _{b9bbcb33e11b80be759c4e844862482d}_
    - **Exploit Used**
         - Use “wpscan --url http://192.168.1.110:80/wordpress -e u”
           To discover users Steven and Michael
         - Used “ssh michael@192.168.1.110” and guessed password “michael” to gain access to michaels account
           Navigated to /var/www/html and used “grep -R flag1” to find flag 1
  - `flag2.txt`: _{fc3fd58dcdad9ab23faca6e9a36e581c}_
    - **Exploit Used**
      - flag 2 coud be found in directory shown below:
        ![nmap1](/Screenshots/flag2.JPG)
  - `flag3.txt`: _{afc01ab56b50591e7dccf93122770cd2}_
    - **Exploit Used**
      - _TODO: Identify the exploit used_
      - _TODO: Include the command run_
  - `flag4.txt`: _{715dea6c055b9fe3337544932f2941ce}_
    - **Exploit Used**
      - _TODO: Identify the exploit used_
      - _TODO: Include the command run_


