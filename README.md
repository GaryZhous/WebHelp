# Bash scripts for web app security checks (For Unix/Linux Environment)

## Serveo.sh
Serveo is an SSH server just for remote port forwarding, which doesn't require an account or client software. Servo.sh is a wrapper that allows users to expose their application to the public easily through servo.net
```
  #usage
  ./Serveo.sh <local_port> [remote_port]
  #or
  ./Serveo.sh <local_port>
  #if you wish to change the subdomain, do
  ./Serveo.sh <local_port> [remote_port] change
```
## webapp_security_check.sh
### Prerequisites
The script requires the following tools to be installed on your system:

1. **nmap** - For network and port scanning.
2. **nikto** - For web server vulnerability scanning.
3. **curl** - For checking HTTP security headers.
4. **openssl** - For SSL certificate checks.

### Installing the Required Tools

#### Installing nmap
Nmap ("Network Mapper") is a free and open-source utility for network discovery and security auditing.

```bash
sudo apt install nmap
```
#### Installing Nikto
Nikto is an open-source web server scanner that checks for vulnerabilities such as misconfigurations and outdated software.

```bash
sudo apt install nikto
```
#### Installing curl
Curl is a tool for transferring data using various network protocols and is useful for testing HTTP headers.

```Bash
sudo apt install curl
```
#### Installing openssl
OpenSSL is a robust toolkit for SSL and TLS protocols, allowing you to check SSL certificates.

```bash
sudo apt install openssl
```
The script performs the following security checks on your web application:
- Port Scanning: Using nmap, it checks for open ports and services running on the target server.
- Vulnerability Scanning: Using nikto, it scans for known vulnerabilities on the web server.
- Security Headers: Using curl, it checks if HTTP security headers (such as HSTS and CSP) are properly configured.
- SSL Check: Using openssl, it checks the validity of the SSL certificate.

#### Usage
```Bash
./webapp_security_check.sh <target_url> <target_ip>
```

## mysql_injection_test.sh

This shell script performs SQL injection checks on a web application. It leverages the powerful `sqlmap` tool to detect SQL injection vulnerabilities in web applications that interact with MySQL databases.

### Prerequisites

Before running the script, ensure the following tool is installed on your system:

1. **sqlmap** - Automated SQL injection detection and exploitation tool.

#### Installing sqlmap

`sqlmap` is a powerful tool for automating the detection and exploitation of SQL injection flaws.

You can install `sqlmap` using **pip** (the Python package manager):

For Python 2 or Python 3:
```bash
pip install sqlmap
```

#### Usage
```bash
./mysql_injection_test.sh <target_url> <parameter>
```
