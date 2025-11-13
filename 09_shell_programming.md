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
2. Environment variables (PATH, HOME)
3. Special variables ($#, $?, $$, etc.)

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

### **Filesystem Commands**
```bash
ls
ls -l
pwd
cd dir
mkdir dir
rmdir dir
touch file
cp src dst
mv src dst
rm file
rm -r dir
```

### **Viewing Files**
```bash
cat file
head -n 5 file
tail -n 5 file
less file
more file
```

### **Search & Filter**
```bash
grep "text" file
grep -i "text" file
grep -r "text" /path
sort file
uniq file
wc file
```

### **Permissions**
```bash
chmod 755 file
chmod u+x script.sh
chown user:group file
```

### **Processes**
```bash
ps
ps aux
kill PID
pstree
```

### **Networking**
```bash
ping google.com
curl https://example.com
wget https://example.com
```

---

## 8. Important Special Variables

| Variable | Meaning |
|---------|----------|
| `$$` | PID of current script |
| `$!` | PID of last background job |
| `$?` | Exit status of last command |
| `$0` | Script name |
| `$#` | Argument count |
| `$@` | All arguments (separately) |
| `$*` | All arguments (single string) |
| `$1...$n` | Positional parameters |

---

## ✔ Best Practice
**Always wrap variables inside double quotes**:
```bash
echo "$name"
echo "$age"
```
This prevents: word-splitting, globbing, errors with empty variables.

---