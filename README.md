# FILE-INCLUSION

File Inclusion vulnerability enables an attacker to gain unauthorized access to sensitive files on a web server or execute malicious files through the utilization of the ‘include’ functionality.

## Types of File Inclusion

### 1. Local File Inclusion

It is a type of File Inclusion that allows an attacker to include files from the server's filesystem in the web application's response. This can lead to a range of malicious activities, including information disclosure, code execution, and privilege escalation.

**Example:**

```php
/**
* Get the filename from a GET input
* Example - http://example-website.com/?file=filename.php
*/
$file = $_GET['file'];
```
### 2. Remote File Execution

It allows an attacker to include arbitrary code files from a remote location in a web application. This can be used to execute malicious code on the victim’s server, steal sensitive data, or take control of the website.

Example:
```jsp
<c:import url="<=request.getParameter('conf')%>">
```

GIT Link : [https://rb.gy/a3bhvy](https://rb.gy/a3bhvy)

## Preventive Measures

### 1. Input Validation and Sanitization
Always validate and sanitize user inputs, especially those used to construct file paths. Use functions like `realpath()` and ensure they point to expected locations.
### 2. Use Whitelists
Maintain a whitelist of allowed files and directories that can be included or accessed by the application. Validate user inputs against this whitelist to prevent unauthorized file access.
### 3. Disable Dynamic Includes
Avoid using user-supplied input directly in functions that include files (include, require, etc.). 

If dynamic file inclusion is necessary, validate the input and restrict it to a predefined set of safe paths.
### 4. File Access Permissions
Ensure that sensitive files and directories are properly protected with appropriate file system permissions. 

Limit the web server's access rights to only necessary directories and files.
### 5. Secure Configuration
Configure the web server and application framework to restrict access to sensitive directories and files. Use configuration settings that prevent directory traversal attacks (e.g., ../../).

## Usage
Clone the repository:
```bash
git clone https://rb.gy/a3bhvy
cd a3bhvy
```


