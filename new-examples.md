Here are some **Linux Bash scripting examples**, starting from beginner level and progressing to intermediate.

---

# 1. Hello World

```bash
#!/bin/bash

echo "Hello, World!"
```

Run:

```bash
chmod +x hello.sh
./hello.sh
```

---

# 2. Print Variables

```bash
#!/bin/bash

name="Atul"
course="Linux"

echo "Name: $name"
echo "Course: $course"
```

Output

```
Name: Atul
Course: Linux
```

---

# 3. Take User Input

```bash
#!/bin/bash

echo "Enter your name:"
read name

echo "Welcome $name"
```

---

# 4. Addition of Two Numbers

```bash
#!/bin/bash

echo "Enter first number:"
read a

echo "Enter second number:"
read b

sum=$((a+b))

echo "Sum = $sum"
```

---

# 5. If Else Example

```bash
#!/bin/bash

echo "Enter a number:"
read num

if [ $num -gt 0 ]
then
    echo "Positive Number"
else
    echo "Zero or Negative Number"
fi
```

---

# 6. Even or Odd

```bash
#!/bin/bash

echo "Enter a number:"
read num

if [ $((num%2)) -eq 0 ]
then
    echo "Even"
else
    echo "Odd"
fi
```

---

# 7. Compare Two Numbers

```bash
#!/bin/bash

echo "Enter first number:"
read a

echo "Enter second number:"
read b

if [ $a -gt $b ]
then
    echo "$a is greater"
elif [ $a -lt $b ]
then
    echo "$b is greater"
else
    echo "Both are equal"
fi
```

---

# 8. For Loop

```bash
#!/bin/bash

for i in {1..5}
do
    echo "Number: $i"
done
```

---

# 9. While Loop

```bash
#!/bin/bash

count=1

while [ $count -le 5 ]
do
    echo $count
    ((count++))
done
```

---

# 10. Until Loop

```bash
#!/bin/bash

count=1

until [ $count -gt 5 ]
do
    echo $count
    ((count++))
done
```

---

# 11. List Files

```bash
#!/bin/bash

for file in *
do
    echo "$file"
done
```

---

# 12. Check File Exists

```bash
#!/bin/bash

echo "Enter filename:"
read file

if [ -f "$file" ]
then
    echo "File exists"
else
    echo "File not found"
fi
```

---

# 13. Check Directory Exists

```bash
#!/bin/bash

echo "Enter directory:"
read dir

if [ -d "$dir" ]
then
    echo "Directory exists"
else
    echo "Directory not found"
fi
```

---

# 14. Create Backup

```bash
#!/bin/bash

cp data.txt data.txt.bak

echo "Backup created."
```

---

# 15. Rename All `.txt` Files

```bash
#!/bin/bash

for file in *.txt
do
    mv "$file" "${file%.txt}.bak"
done
```

---

# 16. Count Files

```bash
#!/bin/bash

count=$(ls | wc -l)

echo "Total files: $count"
```

---

# 17. Display Current Date and Time

```bash
#!/bin/bash

echo "Date: $(date)"
```

---

# 18. Disk Usage Check

```bash
#!/bin/bash

df -h
```

---

# 19. Memory Usage

```bash
#!/bin/bash

free -h
```

---

# 20. System Information

```bash
#!/bin/bash

echo "Hostname: $(hostname)"
echo "Kernel: $(uname -r)"
echo "User: $(whoami)"
echo "Date: $(date)"
echo "Uptime:"
uptime
```

---

# 21. Simple Calculator

```bash
#!/bin/bash

echo "1. Add"
echo "2. Subtract"
echo "3. Multiply"
echo "4. Divide"

read choice

echo "Enter first number:"
read a

echo "Enter second number:"
read b

case $choice in
1)
    echo "Result = $((a+b))"
    ;;
2)
    echo "Result = $((a-b))"
    ;;
3)
    echo "Result = $((a*b))"
    ;;
4)
    echo "Result = $((a/b))"
    ;;
*)
    echo "Invalid Choice"
    ;;
esac
```

---

# 22. Password Check

```bash
#!/bin/bash

password="cloudnautic"

echo "Enter password:"
read input

if [ "$input" = "$password" ]
then
    echo "Access Granted"
else
    echo "Access Denied"
fi
```

---

# 23. Create Multiple Files

```bash
#!/bin/bash

for i in {1..10}
do
    touch file$i.txt
done

echo "10 files created."
```

---

# 24. Find Largest Number

```bash
#!/bin/bash

echo "Enter three numbers:"
read a b c

largest=$a

if [ $b -gt $largest ]
then
    largest=$b
fi

if [ $c -gt $largest ]
then
    largest=$c
fi

echo "Largest = $largest"
```

---

# 25. Check Service Status

```bash
#!/bin/bash

service=ssh

systemctl is-active $service

if [ $? -eq 0 ]
then
    echo "$service is running."
else
    echo "$service is stopped."
fi
```

---

# Common Bash Commands Used

| Command      | Description                  |
| ------------ | ---------------------------- |
| `echo`       | Print output                 |
| `read`       | Read user input              |
| `if`         | Conditional statement        |
| `case`       | Multiple conditions          |
| `for`        | For loop                     |
| `while`      | While loop                   |
| `until`      | Until loop                   |
| `break`      | Exit loop                    |
| `continue`   | Skip current iteration       |
| `exit`       | Exit script                  |
| `$?`         | Previous command exit status |
| `$0`         | Script name                  |
| `$1`         | First argument               |
| `$#`         | Number of arguments          |
| `$@`         | All arguments                |
| `$(command)` | Command substitution         |

---

## Common Bash Scripting Projects

1. User Management Automation
2. Automated File Backup
3. Disk Space Monitoring
4. Log File Rotation
5. Service Health Check
6. System Monitoring Dashboard
7. AWS EC2 Startup Script
8. Docker Container Monitoring
9. Kubernetes Node Health Check
10. Cron-based Database Backup

These examples cover the core Bash concepts commonly taught in Linux administration, DevOps, and cloud automation courses.
