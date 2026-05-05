# 🐧 Linux Bash Scripting – Complete Practical Guide

---

## 📌 Introduction to Shell and Bash Environment

* **Shell** = Interface between user and Linux kernel
* **Bash (Bourne Again Shell)** = Most widely used shell in Linux
* Acts as:

  * Command interpreter
  * Scripting language
  * Automation tool

👉 Check current shell:

```bash
echo $SHELL
```

👉 List available shells:

```bash
cat /etc/shells
```

---

## 🧩 Types of Shells and Execution Context

### 🔹 Types of Shells

* **bash** – Default Linux shell
* **sh** – Original shell
* **zsh** – Advanced interactive shell
* **ksh** – Korn shell

### 🔹 Execution Context

* **Interactive shell**

  * User enters commands manually
* **Non-interactive shell**

  * Executes scripts

👉 Check process:

```bash
ps -p $$
```

---

## 📜 Writing and Executing Basic Shell Scripts

### Create Script

```bash
nano script.sh
```

### Add Shebang

```bash
#!/bin/bash
```

### Give Permission

```bash
chmod +x script.sh
```

### Execute

```bash
./script.sh
```

---

## ⚙️ Script Structure and Shebang

```bash
#!/bin/bash

# Author: Atul
# Description: Sample script

echo "Script Started"
```

📌 **Shebang (`#!/bin/bash`)**

* Defines interpreter
* Must be first line
* Without it → system may use wrong shell

---

## 📦 Variables and Environment Variables

### 🔹 Local Variables

```bash
name="Atul"
echo $name
```

### 🔹 Read-only Variable

```bash
readonly PI=3.14
```

### 🔹 Delete Variable

```bash
unset name
```

### 🔹 Environment Variables

```bash
echo $HOME
echo $PATH
```

📌 Export variable:

```bash
export VAR=value
```

---

## ⌨️ User Input Handling

```bash
#!/bin/bash
read -p "Enter your name: " name
echo "Hello $name"
```

📌 Hidden input (password):

```bash
read -s password
```

---

## ➕ Basic Operators

### 🔹 Arithmetic

```bash
a=10
b=5
echo $((a + b))
```

### 🔹 Relational

```bash
if [ $a -gt $b ]; then
  echo "a is greater"
fi
```

### 🔹 Logical

```bash
if [ $a -gt 5 ] && [ $b -lt 10 ]; then
  echo "Condition True"
fi
```

---

# 🚀 Bash Scripting Essentials (Practical)

---

## ✅ Hello World

```bash
#!/bin/bash
echo "Hello, World!"
```

---

## 📦 Variables Example

```bash
name="Atul"
echo "Welcome, $name!"
```

---

## 📑 User Input

```bash
read -p "Enter name: " name
echo "Hello $name"
```

---

## 🔄 If-Else Condition

```bash
read num
if [ $num -gt 10 ]; then
  echo "Greater than 10"
else
  echo "10 or less"
fi
```

---

## 🔁 For Loop

```bash
for i in {1..5}
do
  echo "Iteration $i"
done
```

---

## 🔄 While Loop

```bash
count=1
while [ $count -le 5 ]
do
  echo "Count: $count"
  ((count++))
done
```

---

## ⚙️ Functions

```bash
greet() {
  echo "Hello, $1"
}
greet "Atul"
```

---

## 📚 Command Line Arguments

```bash
echo "Script: $0"
echo "Arg1: $1"
echo "Arg2: $2"
```

Run:

```bash
./script.sh hello world
```

---

## 📦 Arrays

```bash
fruits=("Apple" "Banana" "Cherry")
echo ${fruits[0]}
echo ${fruits[@]}
```

---

## 📂 File Handling

```bash
while read line; do
  echo "$line"
done < file.txt
```

---

## 📝 Case Statement

```bash
read num
case $num in
  1) echo "One" ;;
  2) echo "Two" ;;
  *) echo "Invalid" ;;
esac
```

---

# 🧪 Practical Mini Projects

---

## 💾 Disk Usage Monitor

```bash
THRESHOLD=80
usage=$(df -h / | awk 'NR==2 {print $5}' | sed 's/%//')

if [ $usage -gt $THRESHOLD ]; then
  echo "Disk usage is high: $usage%"
fi
```

---

## 📦 Backup Script

```bash
src="/etc"
dest="/tmp/backup_$(date +%F_%T).tar.gz"

tar -czf $dest $src
echo "Backup created: $dest"
```

---

## 🧮 Simple Calculator

```bash
read -p "Enter a: " a
read -p "Enter b: " b
read -p "Operator (+ - * /): " op

case $op in
  +) echo $((a+b)) ;;
  -) echo $((a-b)) ;;
  \*) echo $((a*b)) ;;
  /) echo $((a/b)) ;;
  *) echo "Invalid" ;;
esac
```

---

# 📂 Suggested GitHub Repo Structure

```
linux-bash-scripting/
├── 01-hello-world.sh
├── 02-variables.sh
├── 03-user-input.sh
├── 04-conditionals.sh
├── 05-loops.sh
├── 06-functions.sh
├── 07-arguments.sh
├── 08-arrays.sh
├── 09-file-handling.sh
├── 10-case-statement.sh
├── 11-operators.sh
├── 12-environment-vars.sh
├── projects/
│   ├── disk-monitor.sh
│   ├── backup-script.sh
│   └── calculator.sh
└── README.md
```

---

# ⚡ Points to Remember (Interview + Practical)

* `#!/bin/bash` → mandatory for script interpreter
* Always use **chmod +x** before execution
* Prefer `$(command)` over backticks
* Use **double quotes** to avoid word splitting issues
* Use `-eq, -ne, -gt, -lt` for numeric comparison
* Use `=` for string comparison
* Use `[[ ]]` (modern) instead of `[ ]` when possible
* Always validate user input
* Debug script:

```bash
bash -x script.sh
```

* Check syntax:

```bash
bash -n script.sh
```

---
