# 📜 Bash Scripting — Important Points to Remember

## 📌 1️⃣ Shebang is Mandatory

Always start Bash scripts with:

```bash
#!/bin/bash
```

This tells Linux to execute the script using the Bash shell.

---

## 📌 2️⃣ Make Script Executable

```bash
chmod +x script.sh
```

Run:

```bash
./script.sh
```

---

## 📌 3️⃣ Variables Have No Spaces

✅ Correct:

```bash
name="Atul"
```

❌ Wrong:

```bash
name = "Atul"
```

---

## 📌 4️⃣ Access Variables with `$`

```bash
echo $name
```

or

```bash
echo "${name}"
```

---

## 📌 5️⃣ Use Quotes Carefully

### Double Quotes `" "`

Variables expand:

```bash
name="Atul"
echo "Hello $name"
```

### Single Quotes `' '`

Variables do NOT expand:

```bash
echo 'Hello $name'
```

---

## 📌 6️⃣ Comments Improve Readability

```bash
# This is a comment
```

---

## 📌 7️⃣ Read User Input

```bash
read username
echo $username
```

With prompt:

```bash
read -p "Enter Name: " username
```

---

## 📌 8️⃣ Use `if` Properly

```bash
if [ condition ]
then
    commands
fi
```

Example:

```bash
if [ $num -gt 10 ]
then
   echo "Greater"
fi
```

---

## 📌 9️⃣ Important Comparison Operators

### Numeric Operators

| Operator | Meaning          |
| -------- | ---------------- |
| `-eq`    | Equal            |
| `-ne`    | Not equal        |
| `-gt`    | Greater than     |
| `-lt`    | Less than        |
| `-ge`    | Greater or equal |
| `-le`    | Less or equal    |

Example:

```bash
[ $a -gt $b ]
```

---

## 📌 🔟 String Comparison

```bash
[ "$a" = "$b" ]
```

Check empty string:

```bash
[ -z "$var" ]
```

---

## 📌 1️⃣1️⃣ File Test Operators

| Operator | Meaning            |
| -------- | ------------------ |
| `-f`     | File exists        |
| `-d`     | Directory exists   |
| `-r`     | Read permission    |
| `-w`     | Write permission   |
| `-x`     | Execute permission |

Example:

```bash
if [ -f test.txt ]
then
   echo "File exists"
fi
```

---

## 📌 1️⃣2️⃣ Loops are Very Important

### For Loop

```bash
for i in 1 2 3
do
   echo $i
done
```

### While Loop

```bash
while [ $num -le 5 ]
do
   echo $num
   ((num++))
done
```

---

## 📌 1️⃣3️⃣ Functions Improve Reusability

```bash
greet() {
   echo "Welcome"
}

greet
```

---

## 📌 1️⃣4️⃣ Command Line Arguments

| Variable | Meaning         |
| -------- | --------------- |
| `$0`     | Script name     |
| `$1`     | First argument  |
| `$2`     | Second argument |
| `$#`     | Total arguments |
| `$@`     | All arguments   |

Example:

```bash
echo $1
```

Run:

```bash
./script.sh Atul
```

---

## 📌 1️⃣5️⃣ Exit Status is Important

| Value    | Meaning |
| -------- | ------- |
| `0`      | Success |
| Non-zero | Failure |

Check previous command:

```bash
echo $?
```

---

## 📌 1️⃣6️⃣ Use Logical Operators

| Operator | Meaning |   |    |
| -------- | ------- | - | -- |
| `&&`     | AND     |   |    |
| `        |         | ` | OR |
| `!`      | NOT     |   |    |

Example:

```bash
mkdir demo && cd demo
```

---

## 📌 1️⃣7️⃣ Redirect Output

### Overwrite

```bash
echo "Hello" > file.txt
```

### Append

```bash
echo "World" >> file.txt
```

---

## 📌 1️⃣8️⃣ Pipes are Powerful

```bash
cat file.txt | grep error
```

Output of one command becomes input for another.

---

## 📌 1️⃣9️⃣ Use `grep` Frequently

```bash
grep "root" /etc/passwd
```

Case insensitive:

```bash
grep -i root file.txt
```

---

## 📌 2️⃣0️⃣ Arrays in Bash

```bash
fruits=("apple" "banana" "mango")

echo ${fruits[0]}
```

---

## 📌 2️⃣1️⃣ Arithmetic Operations

```bash
a=10
b=5

echo $((a+b))
```

---

## 📌 2️⃣2️⃣ Debugging Script

### Debug Entire Script

```bash
bash -x script.sh
```

### Debug Specific Section

```bash
set -x
commands
set +x
```

---

## 📌 2️⃣3️⃣ Important Special Variables

| Variable | Meaning             |
| -------- | ------------------- |
| `$$`     | Current Process ID  |
| `$?`     | Last command status |
| `$USER`  | Current user        |
| `$HOME`  | Home directory      |
| `$PWD`   | Current directory   |

---

## 📌 2️⃣4️⃣ Best Practices

* Use meaningful variable names
* Add comments
* Validate user input
* Handle errors properly
* Use functions for repeated tasks
* Test scripts before production
* Keep scripts modular

---

# 🚀 Most Common Real-Time Bash Script Use Cases

* User creation automation
* Backup scripts
* Log cleanup
* Disk monitoring
* Service monitoring
* Deployment automation
* Cron job automation
* Health check scripts
* AWS/Azure automation scripts
* CI/CD helper scripts

---

# 📌 Frequently Used Bash Commands

```bash
echo
read
if
for
while
case
grep
awk
sed
cut
find
chmod
chown
tar
zip
scp
ssh
curl
wget
```

---

# 📌 Points to Remember for Interviews

* Difference between `sh` and `bash`
* Meaning of shebang
* Difference between `>` and `>>`
* Difference between `$*` and `$@`
* File permissions in scripts
* Exit codes
* Cron jobs
* Signal handling
* Debugging methods
* Environment variables
* Process automation

---

# 📌 Quick Bash Script Template

```bash
#!/bin/bash

# Variables
name="Atul"

# Function
greet() {
   echo "Welcome $name"
}

# Main Logic
greet

# Condition
if [ -f test.txt ]
then
   echo "File exists"
else
   echo "File not found"
fi
```
