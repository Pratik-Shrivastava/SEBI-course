# 🐚 SHELL PROGRAMMING (Expanded Conceptual Guide — with Detailed UNIX Commands)

---

## 🧩 1️⃣ SHELL SCRIPTING BASICS

### Concept
A **Shell Script** is a file containing UNIX/Linux commands executed sequentially by a shell like **bash**, **sh**, or **zsh**.

**Diagram:**
```
User → Shell (bash/sh) → Kernel → Hardware
```

### Steps to Create and Run
1. Create file: `myscript.sh`  
2. Add shebang: `#!/bin/bash`  
3. Add commands  
4. Make executable: `chmod +x myscript.sh`  
5. Run: `./myscript.sh`

**Example:**
```bash
#!/bin/bash
echo "Hello IFSCA Officer!"
```

### MCQs
| Question | Answer |
|-----------|---------|
| Shebang (#!) defines | ✅ Interpreter path |
| File extension | ✅ .sh |
| Make script executable | ✅ chmod +x |

---

## 🧮 2️⃣ SHELL VARIABLES

### Concept
Variables hold temporary values and are accessed using `$`.

**Syntax:**
```bash
name="IFSCA"
echo "Welcome $name"
```

### Special Variables
| Type | Example | Meaning |
|------|----------|----------|
| User-defined | count=10 | Declared by user |
| Environment | $PATH, $HOME | System-level variables |
| Positional | $1, $2 | Script arguments |
| Special | $?, $$ | Exit code, PID |

### MCQs
| Question | Answer |
|-----------|---------|
| Access variable | ✅ $var |
| $PATH stores | ✅ Executable search path |
| $? shows | ✅ Exit status |

---

## 🧳 3️⃣ SHELL SCRIPT ARGUMENTS

### Concept
Arguments provide **external input** to scripts.

**Example:**
```bash
#!/bin/bash
echo "User: $1"
echo "Date: $2"
```
Run:
```bash
./info.sh admin 2025-11-08
```
**Output:**
```
User: admin
Date: 2025-11-08
```

**Special Variables:** `$0`=script name, `$#`=number of arguments, `$@`=all arguments.

### MCQs
| Question | Answer |
|-----------|---------|
| $1 | ✅ First argument |
| $# | ✅ Argument count |
| $@ | ✅ All arguments |

---

## 🔀 4️⃣ IF STATEMENT

### Concept
Conditional execution of commands.

**Syntax:**
```bash
if [ condition ]
then
   command
else
   other_command
fi
```

**Example:**
```bash
if [ $age -ge 18 ]
then
echo "Eligible"
else
echo "Not eligible"
fi
```

**Operators:**
- Numeric: `-eq`, `-gt`, `-lt`
- String: `=`, `!=`
- File: `-f`, `-d`, `-r`

### MCQs
| Question | Answer |
|-----------|---------|
| End of if | ✅ fi |
| Compare integers | ✅ -eq |
| String test | ✅ = |

---

## 🔁 5️⃣ LOOPS

### Concept
Repeat tasks efficiently using loops.

| Loop | Description | Syntax |
|-------|--------------|--------|
| for | Iterate over list | `for var in list; do ...; done` |
| while | Run while condition true | `while [ cond ]; do ...; done` |
| until | Run until condition true | `until [ cond ]; do ...; done` |

**Examples:**
```bash
for i in 1 2 3; do echo "Step $i"; done

count=1
while [ $count -le 3 ]; do echo $count; count=$((count+1)); done
```

### MCQs
| Question | Answer |
|-----------|---------|
| Loop terminator | ✅ done |
| While continues if | ✅ Condition true |
| For loop | ✅ Iterates over list |

---

## 🔙 6️⃣ RETURN & EXIT STATUS

### Concept
Indicates command **success/failure**: `0=success`, non-zero=failure.

**Syntax:**
```bash
command
echo $?
```

**Example:**
```bash
grep "IFSCA" data.txt
if [ $? -eq 0 ]; then echo "Found"; else echo "Not Found"; fi
```

### MCQs
| Question | Answer |
|-----------|---------|
| Success code | ✅ 0 |
| $? shows | ✅ Exit status |
| exit | ✅ Ends script |

---

## 💻 7️⃣ BASIC UNIX COMMANDS (Detailed Explanations)

### Category 1: FILE HANDLING
| Command | Function | Syntax / Example | Notes |
|----------|-----------|------------------|-------|
| ls | List directory contents | ls -l | -l = long list, -a = hidden files |
| cp | Copy files/directories | cp file1 file2 | -r = recursive |
| mv | Move or rename | mv old new | Moves/renames |
| rm | Delete files | rm file.txt | -r removes recursively |
| cat | Display or merge | cat file.txt | cat f1 f2 > all.txt |
| touch | Create empty file | touch report.txt | Creates new if missing |

**Mini Diagram:**
```
Create → touch
List → ls
Copy → cp
Move → mv
Delete → rm
View → cat
```

### Category 2: DIRECTORY OPERATIONS
| Command | Function | Example |
|----------|-----------|----------|
| pwd | Print working directory | pwd |
| cd | Change directory | cd /home/user |
| mkdir | Create directory | mkdir newfolder |
| rmdir | Remove empty directory | rmdir oldfolder |

### Category 3: PERMISSIONS & OWNERSHIP
| Command | Function | Example |
|----------|-----------|----------|
| chmod | Change file permissions | chmod 755 file.sh → rwxr-xr-x |
| chown | Change file owner | chown user:group file |

**Permissions Breakdown:**  r = read, w = write, x = execute  
Owner | Group | Others

### Category 4: SYSTEM INFORMATION
| Command | Function | Example |
|----------|-----------|----------|
| uname -a | System kernel info | Shows OS, version |
| df -h | Disk usage | Displays space |
| top | Running processes | Real-time usage |
| who / w | Logged-in users | Shows sessions |

### Category 5: TEXT PROCESSING
| Command | Function | Example |
|----------|-----------|----------|
| grep | Search text | grep "IFSCA" file.txt |
| awk | Field-based processing | awk '{print $1,$2}' file.txt |
| sed | Replace text | sed 's/old/new/g' file.txt |
| sort | Sort lines | sort names.txt |
| cut | Extract columns | cut -d',' -f2 file.csv |

### Category 6: COMPRESSION & ARCHIVING
| Command | Function | Example |
|----------|-----------|----------|
| tar | Create/extract archives | tar -cvf files.tar file1 file2 |
| gzip | Compress file | gzip data.txt |
| zip/unzip | Zip/unzip files | zip backup.zip *.txt / unzip backup.zip |

**Quick Syntax Recap:**
```bash
ls -l
cp a.txt b.txt
mv b.txt c.txt
rm c.txt
cat file.txt
touch new.txt
grep "IFSCA" log.txt
chmod 755 run.sh
```

### MCQs
| Question | Answer |
|-----------|---------|
| Search pattern | ✅ grep |
| Make executable | ✅ chmod +x |
| List hidden files | ✅ ls -a |

---

## ✅ FINAL REVISION TABLE
| Concept | Description | Example |
|----------|--------------|----------|
| Script Basics | Batch of shell commands | myscript.sh |
| Variables | Store data | name="IFSCA" |
| Arguments | Command-line inputs | $1, $# |
| If Statement | Conditional logic | [ $x -gt 0 ] |
| Loops | Repeat execution | for, while |
| Return | Exit status | $?, exit 0 |
| UNIX Commands | File/system tools | ls, grep, chmod |

---

## 🧠 IFSCA EXAM TIPS

✅ Include shebang at start: `#!/bin/bash`  
✅ `$?` → Previous command’s status (0 = success)  
✅ `fi` ends if; `done` ends loops  
✅ Command Summary:
```
ls → list files
cp → copy
mv → move/rename
rm → delete
cat → display
touch → create file
grep → search
chmod → change permission
```
✅ Difference between **return** (functions) and **exit** (scripts)  
✅ Practice:
- Count files in directory  
- Check if file exists  
- Print current user and date

