HEAD
# dvwa-sqlmap-lab
Beginner-friendly guide for DVWA
=======
# DVWA + sqlmap Beginner Lab 

A beginner-friendly guide to setting up DVWA (Damn Vulnerable Web App) and using `sqlmap` to perform basic SQL injection testing.

## Setup 
- Docker-based setup for DVWA
- Login & configuration
- Fixing common issues (permissions, config.inc.php, etc)

## What You’ll Learn
- How to find SQLi vulnerabilities
- Using sqlmap for GET and POST injections
- Bypassing protection with tamper scripts
- Handling cookies and sessions

#Quick Start
1. `git clone ...`
2. `docker-compose up -d`
3. Access DVWA at [http://localhost:8080](http://localhost:8080)

##  Example Injection
sqlmap -u "http://localhost/DVWA/vulnerabilities/sqli/?id=1&Submit=Submit" \
--cookie="PHPSESSID=..." --batch --risk=3 --level=5 --dbs
