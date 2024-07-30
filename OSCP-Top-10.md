**1. Buffer Overflow**

- Definition: Writing more data to a buffer than it can hold, causing the extra data to spill over into adjacent areas of memory.
- Exploitation:
    - Find a vulnerable buffer overflow vulnerability in a program.
    - Craft a payload that overflows the buffer, overwriting the return address with the address of your shellcode.
    - Use a tool like Metasploit or Immunity Debugger to create and test your exploit.
- Example: `msf > use exploit/windows/fileformat/ buffer_overflow_ example`

**2. SQL Injection**

- Definition: Injecting malicious SQL code into a web application's database to extract or modify sensitive data.
- Exploitation:
    - Identify a vulnerable web application that uses user input to construct SQL queries.
    - Use a tool like Burp Suite or SQLMap to inject malicious SQL code and extract data.
    - Use techniques like UNION injection, error-based injection, or blind injection to bypass security measures.
- Example: `sqlmap -u "http://example.com/vulnerable.php?id=1" --dump`

**3. Cross-Site Scripting (XSS)**

- Definition: Injecting malicious JavaScript code into a web application to steal user data or take control of the user's session.
- Exploitation:
    - Identify a vulnerable web application that reflects user input without proper sanitization.
    - Use a tool like Burp Suite or BeEF to inject malicious JavaScript code and steal user data.
    - Use techniques like stored XSS, reflected XSS, or DOM-based XSS to bypass security measures.
- Example: `beef > use xss / reflect / basic`

**4. Command Injection**

- Definition: Injecting malicious system commands into a web application to execute arbitrary code on the server.
- Exploitation:
    - Identify a vulnerable web application that uses user input to construct system commands.
    - Use a tool like Burp Suite or Metasploit to inject malicious system commands and execute arbitrary code.
    - Use techniques like shellshock or command injection to bypass security measures.
- Example: `msf > use exploit/multi/http/command_injection`

**5. File Inclusion**

- Definition: Including malicious files or code into a web application to execute arbitrary code or steal sensitive data.
- Exploitation:
    - Identify a vulnerable web application that includes user-input files or code.
    - Use a tool like Burp Suite or Metasploit to include malicious files or code and execute arbitrary code.
    - Use techniques like local file inclusion (LFI) or remote file inclusion (RFI) to bypass security measures.
- Example: `msf > use exploit/multi/http/file_inclusion`

**6. Authentication Bypass**

- Definition: Bypassing authentication mechanisms to gain unauthorized access to a system or application.
- Exploitation:
    - Identify a vulnerable authentication mechanism that can be bypassed using techniques like SQL injection or password cracking.
    - Use a tool like Burp Suite or Metasploit to bypass authentication and gain unauthorized access.
    - Use techniques like authentication bypass using SQL injection or authentication bypass using password cracking.
- Example: `msf > use exploit/multi/http/auth_bypass`

**7. Directory Traversal**

- Definition: Accessing files or directories outside of the intended directory structure of a web application.
- Exploitation:
    - Identify a vulnerable web application that allows directory traversal using techniques like dot-dot-slash (../) or URL encoding.
    - Use a tool like Burp Suite or Metasploit to traverse directories and access sensitive files or data.
    - Use techniques like directory traversal using dot-dot-slash (../) or directory traversal using URL encoding.
- Example: `msf > use exploit/multi/http/dir_traversal`

**8. Cross-Site Request Forgery (CSRF)**

- Definition: Forging requests to a web application to perform unauthorized actions on behalf of a user.
- Exploitation:
    - Identify a vulnerable web application that does not implement proper CSRF protection.
    - Use a tool like Burp Suite or BeEF to forge requests and perform unauthorized actions.
    - Use techniques like CSRF using GET requests or CSRF using POST requests.
- Example: `beef > use csrf / forge / basic`

**9. Remote File Execution (RFE)**

- Definition: Executing arbitrary code on a remote server by exploiting vulnerabilities in web applications.
- Exploitation:
    - Identify a vulnerable web application that allows remote file execution using techniques like file inclusion or command injection.
    - Use a tool like Burp Suite or Metasploit to execute arbitrary code on the remote server.
    - Use techniques like RFE using file inclusion or RFE using command injection.
- Example: `msf > use exploit/multi/http/rfe`

**10. Local Privilege Escalation**

- Definition:* Definition: Escalating privileges from a low-privileged user account to a high-privileged user account, such as root or administrator.
- Exploitation:
    - Identify a vulnerable system or application that allows local privilege escalation using techniques like buffer overflow or misconfigured permissions.
    - Use a tool like Metasploit or Immunity Debugger to exploit the vulnerability and escalate privileges.
    - Use techniques like local privilege escalation using buffer overflow or local privilege escalation using misconfigured permissions.
- Example: `msf > use exploit/windows/local/priv_esc`