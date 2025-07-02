practical guide for **Linux Bash scripting** with working code examples and brief tutorials for each. I’ll cover:

* Basics of bash scripting
* Variables
* Conditionals
* Loops
* Functions
* Command line arguments
* Arrays
* File handling
* User input
* Practical mini-projects

---

## 📜 Bash Scripting Essentials

### 📌 How to Create and Run a Bash Script

**Create a file:**

```bash
nano script.sh
```

**Add this at the top:**

```bash
#!/bin/bash
```

**Make it executable:**

```bash
chmod +x script.sh
```

**Run it:**

```bash
./script.sh
```

---

## ✅ Basic Hello World Script

```bash
#!/bin/bash
echo "Hello, World!"
```

---

## 📦 Variables

```bash
#!/bin/bash
name="Atul"
echo "Welcome, $name!"
```

**Variable Types:**

* Local: `var=value`
* Read-only: `readonly var=value`
* Delete var: `unset var`

---

## 📑 User Input

```bash
#!/bin/bash
echo "Enter your name:"
read name
echo "Hello, $name"
```

---

## 🔄 If-Else Condition

```bash
#!/bin/bash
echo "Enter a number:"
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
#!/bin/bash
for i in 1 2 3 4 5
do
  echo "Iteration $i"
done
```

---

## 🔄 While Loop

```bash
#!/bin/bash
count=1
while [ $count -le 5 ]
do
  echo "Count is $count"
  ((count++))
done
```

---

## ⚙️ Functions

```bash
#!/bin/bash
greet() {
  echo "Hello, $1"
}
greet "Atul"
```

---

## 📚 Command Line Arguments

```bash
#!/bin/bash
echo "Script name: $0"
echo "First arg: $1"
echo "Second arg: $2"
```

**Run it:**

```bash
./script.sh hello world
```

---

## 📦 Arrays

```bash
#!/bin/bash
fruits=("Apple" "Banana" "Cherry")
echo "First fruit: ${fruits[0]}"
echo "All fruits: ${fruits[@]}"
```

---

## 📂 File Handling — Read a file line by line

```bash
#!/bin/bash
file="sample.txt"
while read line; do
  echo "Line: $line"
done < "$file"
```

---

## 📝 Case Statement

```bash
#!/bin/bash
echo "Enter a number between 1-3:"
read num
case $num in
  1) echo "You picked One" ;;
  2) echo "You picked Two" ;;
  3) echo "You picked Three" ;;
  *) echo "Invalid" ;;
esac
```

---

## 📌 Practical Mini Projects

### 1️⃣ Disk Usage Monitor

```bash
#!/bin/bash
THRESHOLD=80
usage=$(df -h / | grep / | awk '{ print $5}' | sed 's/%//')
if [ $usage -gt $THRESHOLD ]; then
  echo "Disk usage is above $THRESHOLD%"
fi
```

---

### 2️⃣ Backup Script

```bash
#!/bin/bash
src="/etc"
dest="/tmp/backup_$(date +%F_%T).tar.gz"
tar -czf $dest $src
echo "Backup created at $dest"
```

---

### 3️⃣ Simple Calculator

```bash
#!/bin/bash
echo "Enter first number:"
read a
echo "Enter second number:"
read b
echo "Enter operation (+ - * /):"
read op

case $op in
  +) res=$((a + b)) ;;
  -) res=$((a - b)) ;;
  \*) res=$((a * b)) ;;
  /) res=$((a / b)) ;;
  *) echo "Invalid operation"; exit 1 ;;
esac

echo "Result: $res"
```

---

## 📖 Learning Resources

| Resource                   | Link                                                                                                     |
| :------------------------- | :------------------------------------------------------------------------------------------------------- |
| Bash Official Manual       | [https://www.gnu.org/software/bash/manual/bash.html](https://www.gnu.org/software/bash/manual/bash.html) |
| ShellCheck (script linter) | [https://www.shellcheck.net](https://www.shellcheck.net)                                                 |
| Bash Scripting Cheatsheet  | [https://devhints.io/bash](https://devhints.io/bash)                                                     |

---

## 📦 Suggested GitHub Repo Structure

```
bash-scripting/
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
├── projects/
│   ├── disk-monitor.sh
│   ├── backup-script.sh
│   └── calculator.sh
└── README.md
```
