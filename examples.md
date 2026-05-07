# 📜 Bash Scripting Examples — Basic to Advanced

## 📌 1️⃣ What is Bash Scripting?

Bash scripting is the process of writing commands in a file and executing them automatically using the **Bash Shell**.

### 📌 Advantages

* Automation of repetitive tasks
* Server administration
* CI/CD automation
* Monitoring & backups
* Cloud and DevOps operations

---

# 📌 2️⃣ Create and Run Your First Script

## Step 1: Create Script File

```bash
nano hello.sh
```

## Step 2: Add Script

```bash
#!/bin/bash

echo "Hello World"
```

## Step 3: Give Execute Permission

```bash
chmod +x hello.sh
```

## Step 4: Run Script

```bash
./hello.sh
```

---

# 📌 3️⃣ Variables in Bash

```bash
#!/bin/bash

name="Atul"
company="Cloudnautic"

echo "Welcome $name"
echo "Company: $company"
```

---

# 📌 4️⃣ User Input

```bash
#!/bin/bash

echo "Enter your name:"
read username

echo "Welcome $username"
```

---

# 📌 5️⃣ Command Line Arguments

```bash
#!/bin/bash

echo "First Argument: $1"
echo "Second Argument: $2"
echo "All Arguments: $@"
echo "Total Arguments: $#"
```

## Run

```bash
./script.sh Linux AWS Azure
```

---

# 📌 6️⃣ Arithmetic Operations

```bash
#!/bin/bash

a=10
b=5

sum=$((a+b))
sub=$((a-b))
mul=$((a*b))
div=$((a/b))

echo "Addition: $sum"
echo "Subtraction: $sub"
echo "Multiplication: $mul"
echo "Division: $div"
```

---

# 📌 7️⃣ If Condition

```bash
#!/bin/bash

num=10

if [ $num -gt 5 ]
then
    echo "Number is greater than 5"
fi
```

---

# 📌 8️⃣ If Else Example

```bash
#!/bin/bash

echo "Enter Password:"
read pass

if [ "$pass" == "admin123" ]
then
    echo "Login Successful"
else
    echo "Invalid Password"
fi
```

---

# 📌 9️⃣ Nested If Example

```bash
#!/bin/bash

age=25
citizen="yes"

if [ $age -ge 18 ]
then
    if [ "$citizen" == "yes" ]
    then
        echo "Eligible to vote"
    fi
fi
```

---

# 📌 🔟 Case Statement

```bash
#!/bin/bash

echo "Enter option:"
read option

case $option in
    start)
        echo "Starting Service"
        ;;
    stop)
        echo "Stopping Service"
        ;;
    restart)
        echo "Restarting Service"
        ;;
    *)
        echo "Invalid Option"
        ;;
esac
```

---

# 📌 1️⃣1️⃣ For Loop

```bash
#!/bin/bash

for i in 1 2 3 4 5
do
    echo "Number: $i"
done
```

---

# 📌 1️⃣2️⃣ While Loop

```bash
#!/bin/bash

count=1

while [ $count -le 5 ]
do
    echo "Count: $count"
    ((count++))
done
```

---

# 📌 1️⃣3️⃣ Until Loop

```bash
#!/bin/bash

num=1

until [ $num -gt 5 ]
do
    echo $num
    ((num++))
done
```

---

# 📌 1️⃣4️⃣ Arrays in Bash

```bash
#!/bin/bash

clouds=("AWS" "Azure" "GCP")

echo ${clouds[0]}
echo ${clouds[1]}

echo "All Elements: ${clouds[@]}"
```

---

# 📌 1️⃣5️⃣ Functions in Bash

```bash
#!/bin/bash

greet() {
    echo "Welcome $1"
}

greet Atul
```

---

# 📌 1️⃣6️⃣ Return Values from Functions

```bash
#!/bin/bash

addition() {
    sum=$(( $1 + $2 ))
    echo $sum
}

result=$(addition 10 20)

echo "Result: $result"
```

---

# 📌 1️⃣7️⃣ File Existence Check

```bash
#!/bin/bash

file="test.txt"

if [ -f $file ]
then
    echo "File Exists"
else
    echo "File Not Found"
fi
```

---

# 📌 1️⃣8️⃣ Directory Check

```bash
#!/bin/bash

dir="/home"

if [ -d $dir ]
then
    echo "Directory Exists"
fi
```

---

# 📌 1️⃣9️⃣ Read File Line by Line

```bash
#!/bin/bash

while read line
do
    echo $line
done < test.txt
```

---

# 📌 2️⃣0️⃣ Backup Script

```bash
#!/bin/bash

src="/home/ec2-user/data"
dest="/backup"

tar -czvf backup.tar.gz $src

mv backup.tar.gz $dest

echo "Backup Completed"
```

---

# 📌 2️⃣1️⃣ Disk Usage Monitoring

```bash
#!/bin/bash

usage=$(df -h / | awk 'NR==2 {print $5}' | sed 's/%//')

if [ $usage -gt 80 ]
then
    echo "Disk Usage Critical"
else
    echo "Disk Usage Normal"
fi
```

---

# 📌 2️⃣2️⃣ Service Monitoring Script

```bash
#!/bin/bash

service=httpd

if systemctl is-active --quiet $service
then
    echo "$service is running"
else
    echo "$service is stopped"
fi
```

---

# 📌 2️⃣3️⃣ Automated User Creation

```bash
#!/bin/bash

echo "Enter username:"
read username

sudo useradd $username

echo "User Created Successfully"
```

---

# 📌 2️⃣4️⃣ Log Cleanup Script

```bash
#!/bin/bash

find /var/log -name "*.log" -mtime +7 -delete

echo "Old Logs Deleted"
```

---

# 📌 2️⃣5️⃣ Ping Multiple Servers

```bash
#!/bin/bash

servers=("google.com" "amazon.com" "microsoft.com")

for server in "${servers[@]}"
do
    ping -c 1 $server > /dev/null

    if [ $? -eq 0 ]
    then
        echo "$server is reachable"
    else
        echo "$server is unreachable"
    fi
done
```

---

# 📌 2️⃣6️⃣ AWS EC2 Status Script

```bash
#!/bin/bash

aws ec2 describe-instances \
--query "Reservations[*].Instances[*].[InstanceId,State.Name]" \
--output table
```

---

# 📌 2️⃣7️⃣ Kubernetes Pod Monitoring

```bash
#!/bin/bash

kubectl get pods -A
```

---

# 📌 2️⃣8️⃣ Menu Driven Script

```bash
#!/bin/bash

echo "1. Date"
echo "2. Uptime"
echo "3. Users"

read choice

case $choice in
    1) date ;;
    2) uptime ;;
    3) who ;;
    *) echo "Invalid Choice"
esac
```

---

# 📌 2️⃣9️⃣ Error Handling

```bash
#!/bin/bash

mkdir demo

if [ $? -eq 0 ]
then
    echo "Directory Created"
else
    echo "Failed"
fi
```

---

# 📌 3️⃣0️⃣ Debugging Bash Scripts

## Run in Debug Mode

```bash
bash -x script.sh
```

## Enable Debugging Inside Script

```bash
#!/bin/bash
set -x
```

---

# 📌 3️⃣1️⃣ Scheduling with Cron

## Open Cron

```bash
crontab -e
```

## Run Script Every Day at 5 AM

```bash
0 5 * * * /home/ec2-user/backup.sh
```

---

# 📌 3️⃣2️⃣ Advanced Script — System Health Check

```bash
#!/bin/bash

echo "===== SYSTEM HEALTH ====="

echo "Hostname:"
hostname

echo "Kernel Version:"
uname -r

echo "Disk Usage:"
df -h

echo "Memory Usage:"
free -m

echo "CPU Load:"
uptime

echo "Logged In Users:"
who
```

---

# 📌 3️⃣3️⃣ Advanced Script — Automatic Apache Installation

## Ubuntu/Debian

```bash
#!/bin/bash

sudo apt update -y
sudo apt install apache2 -y
sudo systemctl start apache2
sudo systemctl enable apache2

echo "Apache Installed"
```

## Amazon Linux / RHEL

```bash
#!/bin/bash

sudo yum install httpd -y
sudo systemctl start httpd
sudo systemctl enable httpd

echo "Apache Installed"
```

---

# 📌 3️⃣4️⃣ Advanced Script — Jenkins Installation

```bash
#!/bin/bash

sudo yum update -y

sudo yum install java-21-amazon-corretto -y

sudo wget -O /etc/yum.repos.d/jenkins.repo \
https://pkg.jenkins.io/redhat-stable/jenkins.repo

sudo rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io-2023.key

sudo yum install jenkins -y

sudo systemctl start jenkins
sudo systemctl enable jenkins
```

---

# 📌 3️⃣5️⃣ Important Bash Special Variables

| Variable | Meaning              |
| -------- | -------------------- |
| `$0`     | Script Name          |
| `$1-$9`  | Positional Arguments |
| `$#`     | Total Arguments      |
| `$@`     | All Arguments        |
| `$?`     | Last Command Status  |
| `$$`     | Current Process ID   |
| `$USER`  | Current User         |
| `$HOME`  | Home Directory       |

---

# 📌 3️⃣6️⃣ Common Comparison Operators

| Operator | Meaning          |
| -------- | ---------------- |
| `-eq`    | Equal            |
| `-ne`    | Not Equal        |
| `-gt`    | Greater Than     |
| `-lt`    | Less Than        |
| `-ge`    | Greater or Equal |
| `-le`    | Less or Equal    |

---

# 📌 3️⃣7️⃣ File Test Operators

| Operator | Meaning            |
| -------- | ------------------ |
| `-f`     | Regular File       |
| `-d`     | Directory          |
| `-r`     | Read Permission    |
| `-w`     | Write Permission   |
| `-x`     | Execute Permission |

---

# 📌 3️⃣8️⃣ Best Practices

* Always use `#!/bin/bash`
* Use meaningful variable names
* Add comments
* Validate user input
* Use functions for reusable code
* Handle errors properly
* Use quotes around variables

Example:

```bash
"$filename"
```

---

# 📌 3️⃣9️⃣ Useful Commands for Script Developers

```bash
chmod +x script.sh
bash -n script.sh
bash -x script.sh
shellcheck script.sh
```

---

# 📌 4️⃣0️⃣ Real-Time DevOps Use Cases

* Server provisioning
* AWS automation
* Azure resource deployment
* Docker automation
* Kubernetes deployment
* Jenkins CI/CD pipelines
* Log monitoring
* Backup automation
* Security compliance checks
* Cron job automation
