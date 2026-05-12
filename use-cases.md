# 📖 Linux Shell Script Use Cases with Practical Code Examples

---

# 1️⃣ User Creation Automation

## 📌 Use Case

Automate Linux user creation for admins or DevOps teams.

## ✅ Script

```bash
#!/bin/bash

USERNAME="devuser"

useradd $USERNAME
passwd $USERNAME

echo "User $USERNAME created successfully"
```

---

# 2️⃣ Apache Web Server Installation

## 📌 Use Case

Automatically install and configure Apache/Nginx servers.

## ✅ Script

```bash
#!/bin/bash

yum install httpd -y

systemctl start httpd
systemctl enable httpd

echo "Apache Installed Successfully"
```

---

# 3️⃣ Disk Space Monitoring

## 📌 Use Case

Monitor server disk usage.

## ✅ Script

```bash
#!/bin/bash

echo "Disk Usage Report"

df -h
```

---

# 4️⃣ Memory Usage Monitoring

## 📌 Use Case

Monitor RAM usage in Linux servers.

## ✅ Script

```bash
#!/bin/bash

echo "Memory Usage"

free -m
```

---

# 5️⃣ CPU Monitoring

## 📌 Use Case

Check CPU load on servers.

## ✅ Script

```bash
#!/bin/bash

echo "CPU Load"

uptime
```

---

# 6️⃣ Backup Automation

## 📌 Use Case

Take automatic backup of important files.

## ✅ Script

```bash
#!/bin/bash

tar -czvf backup.tar.gz /home/ec2-user

echo "Backup Completed"
```

---

# 7️⃣ Delete Old Files

## 📌 Use Case

Automatically clean old log/temp files.

## ✅ Script

```bash
#!/bin/bash

find /tmp -type f -mtime +7 -delete

echo "Old Files Deleted"
```

---

# 8️⃣ Website Deployment Script

## 📌 Use Case

Deploy latest application code automatically.

## ✅ Script

```bash
#!/bin/bash

cd /var/www/html

git pull

systemctl restart httpd

echo "Deployment Completed"
```

---

# 9️⃣ Docker Automation

## 📌 Use Case

Build and run Docker containers automatically.

## ✅ Script

```bash
#!/bin/bash

docker build -t myapp .

docker run -d -p 80:80 myapp
```

---

# 🔟 Kubernetes Deployment

## 📌 Use Case

Deploy Kubernetes YAML files automatically.

## ✅ Script

```bash
#!/bin/bash

kubectl apply -f deployment.yaml

kubectl get pods
```

---

# 1️⃣1️⃣ AWS EC2 Automation

## 📌 Use Case

Manage AWS infrastructure using shell scripts.

## ✅ Script

```bash
#!/bin/bash

aws ec2 describe-instances
```

---

# 1️⃣2️⃣ Azure VM Automation

## 📌 Use Case

Create Azure VMs using Azure CLI.

## ✅ Script

```bash
#!/bin/bash

az vm list -o table
```

---

# 1️⃣3️⃣ Ping Server Monitoring

## 📌 Use Case

Check if server/network is reachable.

## ✅ Script

```bash
#!/bin/bash

ping -c 4 google.com
```

---

# 1️⃣4️⃣ Service Status Monitoring

## 📌 Use Case

Check service health automatically.

## ✅ Script

```bash
#!/bin/bash

systemctl status sshd
```

---

# 1️⃣5️⃣ Restart Failed Service

## 📌 Use Case

Auto-restart failed services.

## ✅ Script

```bash
#!/bin/bash

systemctl restart nginx

echo "Nginx Restarted"
```

---

# 1️⃣6️⃣ Log File Analysis

## 📌 Use Case

Search errors in logs.

## ✅ Script

```bash
#!/bin/bash

grep "ERROR" /var/log/messages
```

---

# 1️⃣7️⃣ Database Backup

## 📌 Use Case

Backup MySQL database automatically.

## ✅ Script

```bash
#!/bin/bash

mysqldump -u root -p mydb > backup.sql
```

---

# 1️⃣8️⃣ File Rename Automation

## 📌 Use Case

Rename multiple files automatically.

## ✅ Script

```bash
#!/bin/bash

for file in *.txt
do
mv "$file" "new_$file"
done
```

---

# 1️⃣9️⃣ Cron Job Automation

## 📌 Use Case

Schedule scripts automatically.

## ✅ Example

```bash
crontab -e
```

## Run Script Daily at 1 AM

```bash
0 1 * * * /home/ec2-user/backup.sh
```

---

# 2️⃣0️⃣ System Health Check Script

## 📌 Use Case

Perform complete server health check.

## ✅ Script

```bash
#!/bin/bash

echo "Hostname:"
hostname

echo "Disk Usage:"
df -h

echo "Memory Usage:"
free -m

echo "CPU Load:"
uptime
```

---

# 2️⃣1️⃣ Variable Example

## 📌 Use Case

Store reusable values.

## ✅ Script

```bash
#!/bin/bash

NAME="Atul"

echo "Welcome $NAME"
```

---

# 2️⃣2️⃣ User Input Script

## 📌 Use Case

Take dynamic input from users.

## ✅ Script

```bash
#!/bin/bash

echo "Enter Your Name"

read NAME

echo "Welcome $NAME"
```

---

# 2️⃣3️⃣ If Condition Example

## 📌 Use Case

Perform decision making.

## ✅ Script

```bash
#!/bin/bash

NUMBER=10

if [ $NUMBER -gt 5 ]
then
echo "Number is Greater"
fi
```

---

# 2️⃣4️⃣ Loop Example

## 📌 Use Case

Repeat tasks automatically.

## ✅ Script

```bash
#!/bin/bash

for i in 1 2 3 4 5
do
echo $i
done
```

---

# 2️⃣5️⃣ Function Example

## 📌 Use Case

Reuse code blocks.

## ✅ Script

```bash
#!/bin/bash

hello() {
echo "Hello World"
}

hello
```

---

# 📌 Real-Time DevOps Use Cases

| Use Case         | Example              |
| ---------------- | -------------------- |
| CI/CD Pipeline   | Jenkins Automation   |
| Cloud Automation | AWS CLI / Azure CLI  |
| Containerization | Docker Scripts       |
| Kubernetes       | kubectl Automation   |
| Monitoring       | CPU/Disk Alerts      |
| Security         | SSH Monitoring       |
| Backups          | Scheduled Backups    |
| Deployments      | Auto Deployment      |
| Cleanup          | Log Rotation         |
| Infrastructure   | Terraform Automation |

---

# 📌 Important Commands

| Purpose                | Command            |
| ---------------------- | ------------------ |
| Make Script Executable | chmod +x script.sh |
| Run Script             | ./script.sh        |
| Check Exit Status      | echo $?            |
| View Running Processes | ps -ef             |
| Monitor System         | top                |
| Check Ports            | netstat -tulnp     |

---

# 📌 Points to Remember

* Always start scripts with:

```bash
#!/bin/bash
```

* Add execution permission:

```bash
chmod +x script.sh
```

* Use comments:

```bash
# This is comment
```

* Debug script:

```bash
bash -x script.sh
```

* Best practice:

  * Use variables
  * Handle errors
  * Use functions
  * Keep scripts modular

---

# 📌 Interview Question

## Q: Why are shell scripts important in DevOps?

### Answer:

Shell scripts automate repetitive tasks like deployments, monitoring, backups, server management, Docker/Kubernetes operations, and cloud provisioning, making infrastructure management faster and more efficient.
