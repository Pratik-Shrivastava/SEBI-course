# Shell Scripting Notes

---

## 1. Shell Scripting Basics

### **What is a Shell?**
- A shell is a command-line interpreter that executes commands for the operating system.
- Popular shells: **sh, bash, zsh, ksh, csh**.
- A **shell script** is a file containing a set of UNIX/Linux commands.

### **Shebang (#!)**
```bash
#!/bin/bash
```
Indicates which shell should execute the script.

### **Running a Script**
**Method 1: Make executable**
```bash
chmod +x script.sh
./script.sh
```
**Method 2: Pass script to shell**
```bash
bash script.sh
```

---

## 2. Shell Variables

### **Types of Variables**
1. User-defined variables
2. Environment variables (`PATH`, `HOME`)
3. Special variables (`$#`, `$?`, `$$`, etc.)

### **Defining Variables**
```bash
name="Pratik"
age=25
```
> No spaces around `=`.

### **Accessing Variables**
```bash
echo "$name"
echo "$age"
```

### **Environment Variables**
```bash
printenv
export JAVA_HOME=/usr/lib/jvm/java-17-openjdk
```

### **Constants**
```bash
readonly PI=3.14
```

---

## 3. Shell Script Arguments

### **Special Variables**
| Variable | Meaning |
|---------|---------|
| `$0` | Script name |
| `$1, $2...` | Positional arguments |
| `$#` | Number of arguments |
| `$@` | All args (individually) |
| `$*` | All args (as one string) |
| `$$` | PID of current script |
| `$!` | PID of last background process |
| `$?` | Exit status of last command |

### **Example**
```bash
#!/bin/bash
echo "Script name: $0"
echo "First arg: $1"
echo "Total args: $#"
echo "All args: $@"
echo "PID: $$"
```

---

## 4. If Statement

### **Basic If**
```bash
if [ condition ]; then
    commands
fi
```

### **If-Else**
```bash
if [ condition ]; then
    commands
else
    commands
fi
```

### **If-Elif-Else**
```bash
if [ cond1 ]; then
    c1
elif [ cond2 ]; then
    c2
else
    c3
fi
```

### **String Comparisons**
| Operator | Meaning |
|----------|---------|
| `=` | equal |
| `!=` | not equal |
| `-z` | empty string |
| `-n` | non-empty string |

### **Number Comparisons**
| Operator | Meaning |
|----------|---------|
| `-eq` | equal |
| `-ne` | not equal |
| `-gt` | greater than |
| `-lt` | less than |
| `-ge` | >= |
| `-le` | <= |

---

## 5. Loops

### **For Loop**
```bash
for var in list
do
    commands
done
```

Example:
```bash
for num in 1 2 3 4 5
do
    echo "Number: $num"
done
```

### **C-style For Loop**
```bash
for ((i=1; i<=5; i++))
do
    echo "$i"
done
```

---

### **While Loop**
```bash
while [ condition ]
do
    commands
done
```

Example:
```bash
count=1
while [ $count -le 5 ]
do
    echo "$count"
    count=$((count+1))
done
```

---

### **Until Loop**
Runs until condition becomes **true**.
```bash
until [ $x -gt 5 ]
do
    echo "$x"
    x=$((x+1))
done
```

---

## 6. Return & Exit Status

### **return (inside functions)**
```bash
myFunc() {
    return 10
}
myFunc
echo $?   # 10
```

### **exit**
```bash
exit 1
```

### **$?**
Shows exit status of last command.
```bash
ls
echo $?   # 0 = success
```

---

## 7. Basic UNIX Commands

## 🗂 Filesystem Commands

| Command | Description | Example |
|----------|--------------|----------|
| `ls` | Lists files and directories. | `ls` |
| `ls -l` | Lists files in long format (permissions, size, owner). | `ls -l` |
| `pwd` | Prints current working directory. | `pwd` → `/home/pratik/projects` |
| `cd dir` | Changes directory to `dir`. | `cd Documents` |
| `mkdir dir` | Creates a new directory. | `mkdir my_folder` |
| `rmdir dir` | Removes an empty directory. | `rmdir my_folder` |
| `touch file` | Creates an empty file or updates timestamp. | `touch notes.txt` |
| `cp src dst` | Copies file or directory. | `cp file1.txt backup.txt` |
| `mv src dst` | Moves or renames file/directory. | `mv old.txt new.txt` |
| `rm file` | Deletes a file. | `rm notes.txt` |
| `rm -r dir` | Recursively deletes directory and contents. | `rm -r my_folder` |

💡 *Be careful with `rm -r` — it permanently deletes data!*

---

## 📄 Viewing Files

| Command | Description | Example |
|----------|--------------|----------|
| `cat file` | Displays file content. | `cat readme.txt` |
| `head -n 5 file` | Shows first 5 lines. | `head -n 5 log.txt` |
| `tail -n 5 file` | Shows last 5 lines. | `tail -n 5 log.txt` |
| `less file` | Opens file in scrollable view (`q` to quit). | `less bigfile.txt` |
| `more file` | Displays file content one screen at a time. | `more bigfile.txt` |

🧭 *Use `less` for large files — you can scroll up/down easily.*

---

## 🔍 Search & Filter

| Command | Description | Example |
|----------|--------------|----------|
| `grep "text" file` | Searches for text in a file. | `grep "error" logfile.txt` |
| `grep -i "text" file` | Case-insensitive search. | `grep -i "warning" logfile.txt` |
| `grep -r "text" /path` | Recursive search in directory. | `grep -r "TODO" /project` |
| `sort file` | Sorts lines alphabetically. | `sort names.txt` |
| `uniq file` | Removes duplicate lines (after sorting). | `sort names.txt | uniq` |
| `wc file` | Counts lines, words, and characters. | `wc essay.txt` → `40 200 1200 essay.txt` |

---

## 🔐 Permissions

| Command | Description | Example |
|----------|--------------|----------|
| `chmod 755 file` | Changes file permissions. | `chmod 755 script.sh` |
| `chmod u+x script.sh` | Adds execute permission for user. | `chmod u+x run.sh` |
| `chown user:group file` | Changes file ownership. | `chown pratik:devs app.py` |

### 🧩 chmod Breakdown

Each file has 3 permission groups:
- **u** → user (owner)
- **g** → group
- **o** → others

Permissions values:
| Permission | Meaning | Value |
|-------------|----------|--------|
| `r--` | read only | 4 |
| `rw-` | read & write | 6 |
| `rwx` | read, write, execute | 7 |
| `r-x` | read & execute | 5 |
| `--x` | execute only | 1 |
| `---` | no permission | 0 |

Example → `chmod 755 file`

| User | Group | Others |
|-------|--------|--------|
| 7 = rwx | 5 = r-x | 5 = r-x |

🧠 *Owner can do everything, others can read/execute only.*

---

## ⚙️ Processes

| Command | Description | Example |
|----------|--------------|----------|
| `ps` | Shows running processes. | `ps` |
| `ps aux` | Lists all system processes with details. | `ps aux | grep chrome` |
| `kill PID` | Terminates a process by ID. | `kill 10234` |
| `pstree` | Displays process tree structure. | `pstree` |

💡 *Use `kill -9 PID` to forcefully stop a process if needed.*

---

## 🌐 Networking

| Command | Description | Example |
|----------|--------------|----------|
| `ping google.com` | Tests network connectivity. | `ping google.com` |
| `curl https://example.com` | Fetches web content or API data. | `curl https://api.github.com` |
| `wget https://example.com` | Downloads files from internet. | `wget https://example.com/file.zip` |

---

## ✔ Best Practice
**Always wrap variables inside double quotes**:
```bash
echo "$name"
echo "$age"
```
This prevents: word-splitting, globbing, errors with empty variables.

---