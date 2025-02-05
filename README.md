# LINUX SHELL SCRIPTING BASIC TO ADVANCE

### [Syllabus](./syllabus.md)

---

# **📜 Introduction to Shell Scripting**

## **📝 What is Shell?**  
A **shell** is a command-line interface (CLI) that allows users to interact with the operating system. It acts as an intermediary between the user and the kernel (core of the OS), interpreting commands and executing them.  

💡 Think of the shell as a **translator** that converts human-readable commands into machine-readable instructions.  

There are two main types of shells:  
1. **Command-Line Shells** – Text-based interface (e.g., Bash, Zsh, Fish)  
2. **Graphical Shells** – GUI-based interface (e.g., GNOME, KDE)  

The shell is powerful because it allows automation through **shell scripting**, making it essential for system administration, DevOps, and software development.  

---

## **🛠️ Different Types of Shells**  

There are multiple types of shells in Linux, each with its own features and syntax.  

| Shell Name  | Description |
|------------|-------------|
| **Bash** (Bourne Again Shell) | Most widely used shell, default in Linux distributions, supports scripting & automation |
| **Zsh** (Z Shell) | An improved Bash with better auto-completion, themes, and plugins |
| **Fish** (Friendly Interactive Shell) | User-friendly, with autosuggestions and syntax highlighting |
| **Ksh** (KornShell) | Faster than Bash, used in enterprise environments |
| **Tcsh** (TENEX C Shell) | Based on C Shell, good for C programmers |

To check which shell you are using, run:  
```bash
echo $SHELL
```

To list available shells on your system:  
```bash
cat /etc/shells
```

To switch shells, use:  
```bash
chsh -s /bin/zsh  # Change default shell to Zsh
```

---

## **🖥️ Shell vs Terminal vs Command Line**  

Many beginners confuse these terms, but they are different:  

| Term | Explanation |
|------|-------------|
| **Shell** | The program that interprets and executes commands (e.g., Bash, Zsh, Fish) |
| **Terminal** | The application/window that lets you interact with the shell (e.g., GNOME Terminal, Konsole, Alacritty) |
| **Command Line** | The text-based interface where you type and execute commands |

**Analogy:**  
- 🏠 The **Shell** is the kitchen where the food (commands) is prepared.  
- 🔲 The **Terminal** is the window that lets you see and interact with the kitchen.  
- 💬 The **Command Line** is the menu where you order food (type commands).  

You can open a terminal using:  
- **Ctrl + Alt + T** (Ubuntu, Debian, etc.)  
- **Super (Windows key) + T** (Some distros)  
- Searching for "Terminal" in the application menu  

---

## **⚙️ Setting Up a Shell Environment**  

Before scripting, set up a proper shell environment.  

1. **Use Vim as the Default Editor**  
   Open the terminal and type:  
   ```bash
   export EDITOR=vim
   ```
   To make it permanent, add it to your shell configuration file:  
   ```bash
   echo 'export EDITOR=vim' >> ~/.bashrc  # For Bash
   source ~/.bashrc
   ```

2. **Check Your Shell Version**  
   ```bash
   bash --version
   ```

3. **Update Your Shell (If Needed)**  
   For Bash:  
   ```bash
   sudo apt update && sudo apt install bash
   ```

---

## **🚀 Running Shell Scripts (`.sh` files)**  

A **shell script** is a file containing a sequence of shell commands. Instead of typing commands one by one, you write them in a file and execute them.  

### **1️⃣ Create a Shell Script**  
Let’s create a simple script using **Vim**.  

```bash
vim myscript.sh
```

Press `i` to enter **INSERT mode**, then type:  

```sh
#!/bin/bash
echo "Hello, World!"
```

Press `Esc`, type `:wq`, and press `Enter` to save and exit.  

### **2️⃣ Make the Script Executable**  
To run the script, you must give it **execute** permission:  

```bash
chmod +x myscript.sh
```

### **3️⃣ Run the Script**  
Now, execute it:  

```bash
./myscript.sh
```

💡 If you get a **"Permission Denied"** error, try:  
```bash
bash myscript.sh
```

---

## **🔑 Making a Script Executable (`chmod +x script.sh`)**  

In Linux, you need to **change file permissions** before executing scripts.  

- **`chmod` (Change Mode)** is used to modify file permissions.  
- The `+x` flag makes a file **executable**.  

### **1️⃣ Check File Permissions**  
```bash
ls -l myscript.sh
```

It will show something like this:  
```bash
-rw-r--r--  1 user  user  29 Feb 3 12:34 myscript.sh
```

The `rwx` (read, write, execute) permissions indicate:  
- `r` (read) → Can read the file  
- `w` (write) → Can modify the file  
- `x` (execute) → Can run the file as a program  

### **2️⃣ Add Execution Permission**  
```bash
chmod +x myscript.sh
```

Now, check again with `ls -l`:  
```bash
-rwxr-xr-x  1 user  user  29 Feb 3 12:34 myscript.sh
```
🎉 The script is now executable!

---

## **👨‍💻 Writing Your First Shell Script: `Hello, World!`**  

💡 The tradition of programming starts with a "Hello, World!" program. Let’s write one in shell script.  

### **1️⃣ Open Vim & Create a File**  
```bash
vim hello.sh
```

### **2️⃣ Write the Script**  
Press `i` to enter **INSERT mode**, then type:  

```sh
#!/bin/bash

# This is a comment
echo "Hello, World!"
```

### **3️⃣ Save & Exit**  
Press `Esc`, type `:wq`, and press `Enter`.  

### **4️⃣ Make it Executable**  
```bash
chmod +x hello.sh
```

### **5️⃣ Run the Script**  
```bash
./hello.sh
```

🎉 Output:  
```
Hello, World!
```

---

## **🎯 Summary**  

✅ Shell is the command-line interface for interacting with Linux.  
✅ There are different types of shells (Bash, Zsh, Fish, etc.).  
✅ The terminal is the program that lets you use the shell.  
✅ A shell script is a text file containing shell commands.  
✅ To execute a script, use `chmod +x script.sh` and run `./script.sh`.  
✅ Use Vim (`vim file.sh`) to edit shell scripts efficiently.  

---

## **🚀 Next Steps**  
Now that you've mastered the basics, we will move to **essential Linux commands**! Stay tuned! 🔥  

---

# **📜 Shell Basics & Essential Commands**  

## **📂 Navigating the Filesystem**  

### 🔹 `pwd` (Print Working Directory)  
Shows the full path of the **current directory** you are in.  

```bash
pwd
```
🔹 Example output:  
```
/home/sri
```
Use case: Knowing where you are before running commands.  

---

### 🔹 `ls` (List Directory Contents)  
Lists files and directories in the current location.  

```bash
ls
```

**Common flags:**  
- `-l` → Long listing format (shows permissions, owner, size, etc.)  
- `-a` → Shows hidden files (`.` files)  
- `-h` → Human-readable sizes (KB, MB, GB)  
- `-R` → Lists subdirectories recursively  

```bash
ls -lahR
```

---

### 🔹 `cd` (Change Directory)  
Moves between directories.  

```bash
cd /home/sri/Documents
```

Shortcuts:  
- `cd ..` → Move **one level up**  
- `cd ~` → Go to **home directory**  
- `cd -` → Go to **previous directory**  

---

## **📁 File & Directory Management**  

### 🔹 `touch` (Create a File)  
Creates a new empty file.  

```bash
touch myfile.txt
```

You can create **multiple files** at once:  

```bash
touch file1.txt file2.txt file3.txt
```

---

### 🔹 `mkdir` (Make Directory)  
Creates a new directory.  

```bash
mkdir myfolder
```

Create **multiple directories**:  

```bash
mkdir dir1 dir2 dir3
```

Create a **nested directory structure**:  

```bash
mkdir -p parent/child/grandchild
```
`-p` ensures parent directories exist.

---

### 🔹 `rm` (Remove File/Directory)  
Deletes files or directories.  

```bash
rm myfile.txt
```

**Flags:**  
- `-r` → Delete **directories** recursively  
- `-f` → Force deletion (no confirmation)  

```bash
rm -rf myfolder
```
⚠️ **Be careful** when using `rm -rf`, as it **permanently deletes** files.

---

### 🔹 `cp` (Copy Files & Directories)  
Copies files or directories.  

```bash
cp file1.txt file2.txt
```

Copy a **directory**:  

```bash
cp -r folder1 folder2
```
`-r` is needed for directories.

---

### 🔹 `mv` (Move/Rename Files)  
Moves or renames a file.  

```bash
mv oldname.txt newname.txt
```

Move a file into a different directory:  

```bash
mv file.txt /home/sri/Documents/
```

---

### 🔹 `find` (Search for Files)  
Finds files based on name, size, etc.  

```bash
find /home -name "file.txt"
```

Find files by size:  

```bash
find / -size +100M
```

---

## **📄 Viewing & Editing Files**  

### 🔹 `cat` (View File Contents)  
Displays the contents of a file.  

```bash
cat file.txt
```

---

### 🔹 `tac` (Reverse `cat`)  
Displays a file **backwards**.  

```bash
tac file.txt
```

---

### 🔹 `less` / `more` (Scroll Through Files)  
Allows **scrolling** through large files.  

```bash
less file.txt
```
Press `q` to exit.  

---

### 🔹 `head` / `tail` (First/Last Lines)  
Show first 10 lines:  

```bash
head file.txt
```

Show last 10 lines:  

```bash
tail file.txt
```

Show last 50 lines:  

```bash
tail -n 50 file.txt
```

---

### 🔹 `nano` / `vim` (Edit Files)  

Open file in **Nano** (easier for beginners):  

```bash
nano file.txt
```

Open file in **Vim**:  

```bash
vim file.txt
```

---

### 🔹 `sed` (Stream Editor - Modify Text)  
Replace all occurrences of "foo" with "bar" in a file:  

```bash
sed 's/foo/bar/g' file.txt
```

---

### 🔹 `awk` (Pattern Scanning & Processing)  
Print **column 1** from a file:  

```bash
awk '{print $1}' file.txt
```

---

## **🖥️ Disk & Storage Commands**  

### 🔹 `df` (Disk Free)  
Shows disk usage.  

```bash
df -h
```

---

### 🔹 `du` (Disk Usage)  
Shows size of a file or directory.  

```bash
du -sh folder
```

---

### 🔹 `lsblk` (List Block Devices)  
Shows mounted disks.  

```bash
lsblk
```

---

### 🔹 `mount` / `umount` (Attach/Detach Disks)  
Mount a USB drive:  

```bash
mount /dev/sdb1 /mnt
```

Unmount:  

```bash
umount /mnt
```

---

## **👤 User Management**  

### 🔹 `whoami`  
Displays the current user.  

```bash
whoami
```

### 🔹 `who`  
Shows all logged-in users.  

```bash
who
```

### 🔹 `id`  
Shows user **UID**, **GID**, and **groups**.  

```bash
id
```

### 🔹 `adduser` / `deluser`  
Create a new user:  

```bash
sudo adduser username
```

Delete a user:  

```bash
sudo deluser username
```

---

## **🔐 Permissions & Ownership**  

### 🔹 `chmod` (Change Permissions)  

```bash
chmod 755 file.sh
```

### 🔹 `chown` (Change Owner)  

```bash
chown user:group file.txt
```

---

## **⚙️ Process Management**  

### 🔹 `ps` (Show Running Processes)  
```bash
ps aux
```

### 🔹 `top` / `htop` (Monitor Processes)  
```bash
top
```

For a better UI:  
```bash
htop
```

### 🔹 `kill` / `pkill` (Terminate Process)  
Kill a process by PID:  

```bash
kill 1234
```

Kill a process by name:  

```bash
pkill firefox
```

---

## **🌐 Networking Basics**  

### 🔹 `ping` (Test Connectivity)  
```bash
ping google.com
```

### 🔹 `netstat` / `ss` (Network Status)  
```bash
netstat -tulnp
```
```bash
ss -tulnp
```

### 🔹 `nslookup` (DNS Lookup)  
```bash
nslookup google.com
```

### 🔹 `curl` / `wget` (Download Files)  
```bash
curl -O http://example.com/file.zip
```

```bash
wget http://example.com/file.zip
```

---

## **🎯 Summary**  
✅ Navigated the filesystem with `cd`, `ls`, `pwd`.  
✅ Managed files with `touch`, `mkdir`, `rm`, `cp`, `mv`, `find`.  
✅ Viewed and edited files using `cat`, `less`, `vim`, `sed`, `awk`.  
✅ Monitored system resources with `df`, `du`, `top`, `htop`.  
✅ Managed users and permissions with `adduser`, `chmod`, `chown`.  
✅ Monitored processes with `ps`, `kill`, `pkill`.  
✅ Used networking commands like `ping`, `curl`, `wget`.  

---

This should cover everything you need! Let me know if you want any modifications. 🚀

--- 

# **📜 Variables and Data Types in Shell Scripting**  

In shell scripting, **variables** are used to store values, which can be retrieved and manipulated throughout the script. There are different types of variables, including **environment variables, local variables, arrays, and special variables**.

---

## **🔹 1. Creating Variables**  

Shell variables do **not** use data types like in other programming languages. They are treated as **strings** by default.

```bash
variable_name="Hello, World!"
```

❌ **No spaces** around `=`:  

```bash
name=Sri    # ✅ Correct  
name = Sri  # ❌ Incorrect (throws an error)
```

---

### **📌 Accessing Variables**  
Use the **`$`** symbol before the variable name:

```bash
echo $variable_name
```

You can also use **`${}`** for better readability:

```bash
echo "The message is: ${variable_name}"
```

---

### **📌 Assigning Command Output to a Variable**  

```bash
current_date=$(date)
echo "Today's date is: $current_date"
```

You can also use **backticks** (not recommended):

```bash
current_date=`date`
```

---

## **🔹 2. Environment Variables (`export`, `env`)**  

Environment variables are **global variables** that are available system-wide.  

### **📌 Viewing All Environment Variables**  

```bash
env
```
or  

```bash
printenv
```

---

### **📌 Creating an Environment Variable**  

```bash
export MY_ENV_VAR="I am global!"
```

This makes `MY_ENV_VAR` accessible in **subshells** and child processes.

Check its value:

```bash
echo $MY_ENV_VAR
```

---

### **📌 Removing an Environment Variable**  

```bash
unset MY_ENV_VAR
```

⚠️ This only removes it **temporarily**. If you want it to persist, add `export MY_ENV_VAR="value"` in `~/.bashrc` or `~/.bash_profile`.

---

## **🔹 3. Local vs Global Variables**  

| Type            | Scope           | Example  |
|----------------|----------------|----------|
| **Local**      | Available **only** within the current shell session. | `name="Sri"` |
| **Global**     | Available in **subshells** and **child processes**. | `export MY_VAR="Hello"` |

### **📌 Example: Local vs. Global**
```bash
#!/bin/bash

local_var="I'm local!"
export global_var="I'm global!"

bash -c 'echo "Inside Subshell: $local_var"'  # Won't work
bash -c 'echo "Inside Subshell: $global_var"' # Will work
```

---

## **🔹 4. Positional Parameters (`$1`, `$2`, `$@`, `$#`)**  

Positional parameters are used to **pass arguments** to shell scripts.

### **📌 Example Script**
```bash
#!/bin/bash

echo "First argument: $1"
echo "Second argument: $2"
echo "All arguments: $@"
echo "Number of arguments: $#"
```

Run the script:

```bash
bash myscript.sh hello world
```

🔹 Output:
```
First argument: hello
Second argument: world
All arguments: hello world
Number of arguments: 2
```

| Symbol | Description |
|--------|-------------|
| `$1, $2, $3 ...` | Arguments passed to the script |
| `$@` | All arguments as a **list** |
| `$*` | All arguments as a **single string** |
| `$#` | Number of arguments |

---

## **🔹 5. Special Variables (`$?`, `$$`, `$!`, `$*`)**  

### **📌 `$?` → Exit Status of Last Command**
```bash
ls /nonexistent_folder
echo "Exit status: $?"
```
`0` → Success ✅  
`1+` → Error ❌  

---

### **📌 `$$` → Process ID (PID) of the Script**
```bash
echo "PID of this script: $$"
```

---

### **📌 `$!` → PID of Last Background Process**
```bash
sleep 10 &
echo "Background process PID: $!"
```

---

## **🔹 6. Arrays in Shell (`declare -a`, `@`, `*`)**  

Unlike other languages, **Bash** only supports **one-dimensional arrays**.

### **📌 Defining an Array**  
```bash
my_array=("apple" "banana" "cherry")
```

---

### **📌 Accessing Elements**  
```bash
echo "First element: ${my_array[0]}"
echo "All elements: ${my_array[@]}"
echo "Number of elements: ${#my_array[@]}"
```

🔹 Output:
```
First element: apple
All elements: apple banana cherry
Number of elements: 3
```

---

### **📌 Adding & Removing Elements**
```bash
my_array+=("date")   # Append an element
unset my_array[1]    # Remove "banana"
```

---

## **🔹 7. Associative Arrays (`declare -A`)**  

Associative arrays allow **key-value pairs** (like dictionaries in Python).

```bash
declare -A my_dict
my_dict["name"]="Sri"
my_dict["age"]=21
```

Access values:
```bash
echo "Name: ${my_dict["name"]}"
echo "Age: ${my_dict["age"]}"
```

---

## **🔹 8. Readonly Variables (`readonly`)**  

Prevent a variable from being changed:

```bash
readonly myvar="Can't be changed"
myvar="New Value"   # ❌ Error!
```

---

## **🎯 Summary**  
✅ **Defined** and **accessed** shell variables.  
✅ **Understood** local vs global variables.  
✅ **Used** positional parameters (`$1`, `$2`, `$@`, `$#`).  
✅ **Worked with** special variables (`$?`, `$$`, `$!`, `$*`).  
✅ **Implemented** both indexed and associative arrays.  
✅ **Made variables readonly** with `readonly`.  

---

This should cover everything in depth! Let me know if you want me to tweak anything. 🚀

--- 

# **📜 Input & Output in Shell Scripting**

Handling **input and output** efficiently is one of the most critical skills in shell scripting. This section covers:

✅ Taking user input 📥  
✅ Printing formatted output 📤  
✅ Managing **standard input (stdin), output (stdout), and error (stderr)**  
✅ **File redirection** for better control over outputs  
✅ **Piping** to connect commands  
✅ **Here Documents** for multi-line input  

---

## **🔹 1. Reading User Input (`read`)**

The `read` command is used to **take input** from the user interactively.

### **📌 Basic Usage**
```bash
#!/bin/bash
echo "Enter your name: "
read name
echo "Hello, $name!"
```

🔹 **Explanation:**  
- `read name` stores the user's input in the variable `$name`.  
- `echo "Hello, $name!"` prints the stored value.  

### **📌 Prompting on the Same Line**
```bash
read -p "Enter your favorite color: " color
echo "You like $color!"
```
✅ **`-p`** allows inline prompts.  

---

### **📌 Silent Input (`-s` Flag)**
Use this for **passwords** or sensitive inputs:  
```bash
read -s -p "Enter password: " password
echo -e "\nPassword saved (not displayed for security)."
```
✅ **`-s`** hides input (used for passwords).  

---

### **📌 Reading Multiple Inputs**
```bash
read -p "Enter your first and last name: " first last
echo "First Name: $first, Last Name: $last"
```
✅ **Multiple variables** are assigned automatically.  

---

### **📌 Setting a Timeout for Input**
```bash
read -t 5 -p "Enter something (5 sec timeout): " input
echo "You entered: $input"
```
✅ **`-t`** sets a timeout in **seconds**.  

---

### **📌 Reading Input as an Array**
```bash
read -a names
echo "You entered: ${names[0]}, ${names[1]}"
```
✅ **`-a`** stores input as an **array**.  

---

## **🔹 2. Printing Output (`echo`, `printf`)**

### **📌 Using `echo`**
```bash
echo "Hello, World!"
```

**Escape Sequences in `echo`**
```bash
echo -e "Line 1\nLine 2\tTabbed"
```
✅ `-e` enables **escape sequences** like `\n`, `\t`, etc.  

---

### **📌 Using `printf` for Formatted Output**
```bash
printf "Name: %s, Age: %d\n" "Sri" 21
```
✅ `printf` is like **C-style formatting**, allowing **precision control**.  

✅ Format Specifiers:  
| Specifier | Meaning |
|-----------|---------|
| `%s` | String |
| `%d` | Integer |
| `%f` | Floating point |

---

## **🔹 3. Standard Input, Output, and Error (`stdin`, `stdout`, `stderr`)**

🔹 **Three standard data streams** in UNIX-like systems:

| Stream | Description | File Descriptor |
|--------|-------------|----------------|
| **Standard Input (`stdin`)** | Takes input from the keyboard (default). | `0` |
| **Standard Output (`stdout`)** | Prints normal output to the screen. | `1` |
| **Standard Error (`stderr`)** | Prints error messages. | `2` |

Example:
```bash
ls valid_directory  # Goes to stdout
ls invalid_directory  # Goes to stderr
```

---

## **🔹 4. File Redirection (`>`, `>>`, `<`, `2>`, `2>>`, `&>`, `/dev/null`)**

**Redirection** allows controlling where **input and output** go.

### **📌 Redirecting Output to a File**
```bash
echo "Hello, File!" > output.txt
```
✅ `>` **overwrites** the file.  

---

### **📌 Appending to a File (`>>`)**
```bash
echo "Another Line" >> output.txt
```
✅ `>>` **appends** to the file instead of overwriting.  

---

### **📌 Redirecting Input from a File (`<`)**
```bash
wc -l < output.txt
```
✅ Reads input **from a file** instead of keyboard.  

---

### **📌 Redirecting Errors (`2>`)**
```bash
ls nonexistent_folder 2> error.log
```
✅ `2>` redirects **stderr** to `error.log`.  

✅ **Appending Errors (`2>>`)**
```bash
ls another_nonexistent 2>> error.log
```
✅ **Does not overwrite, appends instead**.  

---

### **📌 Redirecting Both Output & Errors (`&>`)**
```bash
ls /valid /invalid &> output.log
```
✅ **Both stdout & stderr** go to `output.log`.  

---

### **📌 Discarding Output (`/dev/null`)**
```bash
ls nonexistent_folder 2> /dev/null
```
✅ `/dev/null` is a **black hole**—errors disappear!  

---

## **🔹 5. Piping (`|`)**

Piping (`|`) **connects** the output of one command to another.

### **📌 Example: Send `ls` output to `grep`**
```bash
ls -l | grep "txt"
```
✅ Lists **only `.txt` files**.  

---

### **📌 Example: Count Number of Files**
```bash
ls | wc -l
```
✅ `wc -l` counts **lines**, giving file count.  

---

### **📌 Example: Filter System Processes**
```bash
ps aux | grep "bash"
```
✅ Lists **all `bash` processes** running.  

---

## **🔹 6. Here Documents (`<<EOF`)**  

🔹 **Here Documents** (`<<EOF`) allow **multi-line input** inside scripts.

### **📌 Example: Multi-line Input**
```bash
cat <<EOF
This is a multi-line text block.
It can contain multiple lines.
EOF
```
✅ Everything **between `EOF` markers** is treated as input.  

---

### **📌 Example: Write Multi-line to a File**
```bash
cat <<EOF > myfile.txt
Hello, this is line 1.
This is line 2.
EOF
```
✅ Creates `myfile.txt` with given content.  

---

## **🎯 Summary**  
✅ Used `read` for **user input** (normal, silent, timeout, arrays).  
✅ Used `echo` and `printf` for **formatted output**.  
✅ Understood **`stdin` (0), `stdout` (1), `stderr` (2)**.  
✅ Used **file redirection** (`>`, `>>`, `2>`, `&>`, `/dev/null`).  
✅ Used **piping (`|`)** to connect commands.  
✅ Used **Here Documents (`<<EOF`)** for multi-line input.  

---

# **📜 Decision Making & Loops in Shell Scripting**

Effective control flow is essential for writing robust scripts. This guide covers **if-else statements**, **case statements**, different types of **loops**, and **loop control** commands like `break` and `continue`.

---

## **1. Decision Making**

### **🔹 If-Else Statements**

**Syntax:**
```bash
if [ condition ]; then
    # Commands to execute if condition is true
elif [ another_condition ]; then
    # Commands if the first condition is false and another_condition is true
else
    # Commands to execute if all conditions are false
fi
```

**Example:**
```bash
#!/bin/bash
echo "Enter a number:"
read num

if [ $num -gt 10 ]; then
    echo "The number is greater than 10."
elif [ $num -eq 10 ]; then
    echo "The number is exactly 10."
else
    echo "The number is less than 10."
fi
```

**Notes:**
- **`[ condition ]`** is the test command (also written as `test condition`).
- Use **`-gt`** (greater than), **`-eq`** (equal), **`-lt`** (less than) for numeric comparisons.
- String comparisons use **`=`** or **`==`** (in double brackets `[[ ... ]]`), and **`!=`** for inequality.
- Using **`[[ ... ]]`** (double brackets) provides extended test functionality, including regex matching and improved handling of variables.

---

### **🔹 Case Statements**

The **`case`** statement is ideal for matching a variable against a set of patterns.

**Syntax:**
```bash
case "$variable" in
    pattern1)
        # Commands for pattern1
        ;;
    pattern2)
        # Commands for pattern2
        ;;
    *)
        # Default commands if no pattern matches
        ;;
esac
```

**Example:**
```bash
#!/bin/bash
echo "Enter a letter:"
read letter

case "$letter" in
    [a-z])
        echo "Lowercase letter";;
    [A-Z])
        echo "Uppercase letter";;
    [0-9])
        echo "Digit";;
    *)
        echo "Unknown character";;
esac
```

**Notes:**
- Patterns support **wildcards** (`*`, `?`) and **character classes** (`[a-z]`).
- Each block ends with **`;;`** to separate cases.
- The **`*`** pattern acts as the default case.

---

## **2. Loops**

Loops enable you to execute a block of commands repeatedly.

### **🔹 For Loop**

The **`for`** loop iterates over a list of items.

**Syntax:**
```bash
for item in list; do
    # Commands using $item
done
```

**Examples:**

1. **Iterating Over a List:**
    ```bash
    #!/bin/bash
    for fruit in apple banana cherry; do
        echo "I like $fruit"
    done
    ```

2. **Iterating Over Files in a Directory:**
    ```bash
    #!/bin/bash
    for file in /path/to/directory/*; do
        echo "Found file: $file"
    done
    ```

3. **C-style For Loop (Bash Specific):**
    ```bash
    #!/bin/bash
    for (( i=1; i<=5; i++ )); do
        echo "Iteration $i"
    done
    ```

---

### **🔹 While Loop**

The **`while`** loop runs as long as a condition is true.

**Syntax:**
```bash
while [ condition ]; do
    # Commands to execute while condition is true
done
```

**Example:**
```bash
#!/bin/bash
count=1
while [ $count -le 5 ]; do
    echo "Count: $count"
    ((count++))  # Increment count (alternative: count=$((count+1)))
done
```

**Notes:**
- Ensure the loop has a condition that eventually becomes false to avoid an **infinite loop**.
- Arithmetic operations can be done using **`(( ))`**.

---

### **🔹 Until Loop**

The **`until`** loop is similar to `while` but continues until the condition becomes true (i.e., it runs while the condition is false).

**Syntax:**
```bash
until [ condition ]; do
    # Commands to execute until condition becomes true
done
```

**Example:**
```bash
#!/bin/bash
count=1
until [ $count -gt 5 ]; do
    echo "Count: $count"
    ((count++))
done
```

**Notes:**
- Choose between `while` and `until` based on whether you want the loop to run **while** a condition is true or **until** it becomes true.

---

## **3. Loop Control**

### **🔹 Break**

The **`break`** statement terminates the loop immediately.

**Example:**
```bash
#!/bin/bash
for num in {1..10}; do
    if [ $num -eq 5 ]; then
        echo "Breaking at $num"
        break  # Exit loop when num equals 5
    fi
    echo "Number: $num"
done
```

**Notes:**
- `break` stops the execution of the innermost loop.
- It can be combined with a numeric argument to break out of multiple nested loops (in Bash).

---

### **🔹 Continue**

The **`continue`** statement skips the current iteration and moves to the next iteration of the loop.

**Example:**
```bash
#!/bin/bash
for num in {1..10}; do
    if [ $num -eq 5 ]; then
        echo "Skipping $num"
        continue  # Skip the rest of the loop body for num=5
    fi
    echo "Number: $num"
done
```

**Notes:**
- `continue` only affects the current iteration; subsequent iterations continue normally.

---

## **🎯 Summary**

- **If-Else Statements:**  
  - Use `[ condition ]` or `[[ condition ]]` for tests.
  - Supports `if`, `elif`, and `else` for multi-branch decisions.

- **Case Statements:**  
  - Excellent for matching variable patterns with wildcards.
  - Use `;;` to end each block, and `*` as a default case.

- **For Loop:**  
  - Iterates over lists or files.
  - Supports C-style iteration in Bash with `(( ... ))`.

- **While Loop:**  
  - Repeats as long as a condition is true.
  - Use `(( count++ ))` for arithmetic incrementation.

- **Until Loop:**  
  - Runs until a condition becomes true.

- **Loop Control:**  
  - `break` exits the loop completely.
  - `continue` skips the current iteration.

---

This comprehensive guide should serve as a solid reference for decision making and loops in shell scripting. It covers both basic and advanced use cases, ensuring you’re well-equipped for both learning and production-level scripting. Happy scripting! 🚀

---

# **📜 Functions in Shell Scripting**

Functions in shell scripting allow you to encapsulate code into reusable blocks. They help make your scripts modular, more organized, and easier to maintain. In this guide, we’ll cover:

- **Defining Functions**
- **Calling Functions**
- **Function Arguments**
- **Returning Values (`return` and `$?`)**
- **Recursive Functions**

---

## **1. Defining Functions**

A function is defined by a name followed by a set of parentheses and a block of code enclosed in curly braces.

**Syntax:**
```bash
function_name() {
    # Commands
}
```

**Alternate Syntax (optional keyword):**
```bash
function function_name {
    # Commands
}
```

**Example:**
```bash
#!/bin/bash

# Define a simple function
greet() {
    echo "Hello, World!"
}

# Call the function
greet
```

**Notes:**
- Function names should be descriptive and follow standard naming conventions.
- There is no need to specify parameters in the parentheses—they are accessed via special variables (explained below).

---

## **2. Calling Functions**

Once defined, call a function simply by typing its name in the script.

**Example:**
```bash
#!/bin/bash

say_hi() {
    echo "Hi there!"
}

# Calling the function
say_hi
```

You can also call functions from within other functions or conditional statements.

---

## **3. Function Arguments**

Functions can accept arguments, which are accessed using positional parameters similar to script-level arguments.

**Example:**
```bash
#!/bin/bash

# Function that accepts arguments
greet_person() {
    # $1 is the first argument, $2 the second, etc.
    echo "Hello, $1 $2!"
}

# Calling with arguments
greet_person "Sri" "Kumar"
```

**Accessing All Arguments:**
- `$@` represents all the arguments passed.
- `$#` returns the number of arguments.

**Example Using All Arguments:**
```bash
#!/bin/bash

list_args() {
    echo "You provided $# arguments."
    for arg in "$@"; do
        echo "Argument: $arg"
    done
}

list_args "one" "two" "three"
```

**Notes:**
- Always quote `$@` (i.e., `"$@"`) to preserve argument boundaries, especially if arguments contain spaces.

---

## **4. Returning Values**

Shell functions return an exit status (an integer between 0 and 255) using the `return` command. This is typically used to indicate success (0) or failure (non-zero).

**Example:**
```bash
#!/bin/bash

is_even() {
    if [ $(($1 % 2)) -eq 0 ]; then
        return 0  # 0 indicates success (true)
    else
        return 1  # Non-zero indicates false
    fi
}

# Call function with an argument
is_even 4
result=$?  # Capture the return value (exit status)
if [ $result -eq 0 ]; then
    echo "4 is even."
else
    echo "4 is odd."
fi
```

**Capturing Function Output vs. Return Value:**

- **Return Value:** Limited to numeric exit status (good for flags or success/failure).
- **Output:** To return text or complex data, use `echo` and capture with command substitution.

**Example Returning a String:**
```bash
#!/bin/bash

get_greeting() {
    echo "Hello, $1!"
}

greeting=$(get_greeting "Sri")
echo "$greeting"
```

**Notes:**
- Use `return` only for numeric statuses; for strings, output them and capture with `$()`.

---

## **5. Recursive Functions**

Recursive functions are functions that call themselves. They can be useful for tasks like traversing directories, processing tree structures, or solving mathematical problems. However, be cautious of infinite recursion.

**Example: Factorial Calculation**

```bash
#!/bin/bash

# Recursive function to calculate factorial
factorial() {
    if [ $1 -le 1 ]; then
        echo 1
    else
        # Call the function recursively and use command substitution for arithmetic
        local prev=$(factorial $(($1 - 1)))
        echo $(($1 * prev))
    fi
}

# Calculate factorial of 5
result=$(factorial 5)
echo "Factorial of 5 is: $result"
```

**Notes:**
- Always define a base case (here, when `$1` is less than or equal to 1) to prevent infinite recursion.
- Recursive functions can be less efficient than iterative solutions in Bash due to overhead, but they are useful for understanding the concept.

---

## **🎯 Summary**

- **Defining Functions:**  
  - Use `function_name() { ... }` to encapsulate code.
  - Functions make scripts modular and reusable.

- **Calling Functions:**  
  - Simply call by name (e.g., `greet`).

- **Function Arguments:**  
  - Use `$1`, `$2`, ..., `$@`, and `$#` to access arguments.

- **Returning Values:**  
  - Use `return` for numeric status.
  - Use `echo` and command substitution (`$(...)`) for returning strings or complex data.

- **Recursive Functions:**  
  - Functions that call themselves with a base case.
  - Useful for tasks like factorials and directory traversal.

---

This guide covers functions in shell scripting from basics to advanced usage. Experiment with these examples in your scripts using Vim, and feel free to expand on them for more complex scenarios. Happy scripting! 🚀

--- 


# **📜 Working with Files & Directories in Scripts**

Managing files and directories is a core aspect of shell scripting. In this guide, you'll learn how to:

- Check file/directory existence and permissions
- Read from and write to files in your scripts
- Search for files using various commands
- Sort and compare file contents for processing data

---

## **1. Checking File Existence & Attributes**

Before performing operations on a file or directory, it’s important to verify its existence and permissions using test operators.

### **Test Operators Overview**

| Operator | Description |
|----------|-------------|
| `-e`     | Checks if the file or directory **exists**. |
| `-f`     | Checks if it exists and is a **regular file**. |
| `-d`     | Checks if it exists and is a **directory**. |
| `-r`     | Checks if the file is **readable**. |
| `-w`     | Checks if the file is **writable**. |
| `-x`     | Checks if the file is **executable**. |

### **Example: Checking a File**

```bash
#!/bin/bash

file="example.txt"

if [ -e "$file" ]; then
    echo "File exists."
else
    echo "File does not exist."
fi
```

### **Example: Detailed Checks**

```bash
#!/bin/bash

file="script.sh"

if [ -f "$file" ]; then
    echo "$file is a regular file."
fi

if [ -r "$file" ]; then
    echo "$file is readable."
fi

if [ -w "$file" ]; then
    echo "$file is writable."
fi

if [ -x "$file" ]; then
    echo "$file is executable."
fi

# Checking if a directory exists
dir="/home/sri/Documents"

if [ -d "$dir" ]; then
    echo "Directory exists: $dir"
fi
```

---

## **2. Reading & Writing Files in Scripts**

### **Reading Files**

You can read files line-by-line or all at once using various methods.

#### **Method 1: Using a While Loop**

```bash
#!/bin/bash

filename="data.txt"

if [ ! -f "$filename" ]; then
    echo "File not found!"
    exit 1
fi

while IFS= read -r line; do
    echo "Line: $line"
done < "$filename"
```

**Notes:**
- `IFS=` prevents leading/trailing whitespace issues.
- `-r` prevents backslash escapes from being interpreted.

#### **Method 2: Using `cat`**

```bash
#!/bin/bash

cat data.txt
```

*This method is simpler for quick viewing, but less flexible for processing.*

---

### **Writing to Files**

#### **Method 1: Using Redirection**

```bash
#!/bin/bash

echo "Hello, World!" > output.txt
```

- **`>`** overwrites the file.
- **`>>`** appends to the file:

```bash
echo "Appending this line." >> output.txt
```

#### **Method 2: Here Documents**

Useful for writing multi-line text into a file.

```bash
#!/bin/bash

cat <<EOF > config.txt
# Configuration File
username=sri
password=secret
EOF
```

---

## **3. Searching Files**

Searching within files or for files themselves is a common task.

### **Using `grep`**

`grep` searches for patterns within files.

#### **Basic Usage**

```bash
grep "search_term" filename.txt
```

#### **Common Flags:**

- **`-i`**: Ignore case
- **`-n`**: Show line numbers
- **`-r` or `-R`**: Recursive search in directories

```bash
grep -in "error" logs/*.log
```

### **Using `find`**

`find` is used to search for files and directories based on conditions.

#### **Basic Usage**

```bash
find /path/to/search -name "filename.txt"
```

#### **Common Options:**

- **`-type f`**: Find regular files
- **`-type d`**: Find directories
- **`-size`**: Search by file size (e.g., `+100M` for files larger than 100MB)
- **`-mtime`**: Modified time (e.g., `-mtime -7` for files modified in the last 7 days)

```bash
find /var/log -type f -name "*.log" -mtime -7
```

### **Using `locate`**

`locate` uses a prebuilt database to quickly find files.

#### **Usage**

```bash
locate filename.txt
```

**Notes:**
- Database may need updating with `sudo updatedb`.
- Very fast but might not reflect very recent changes.

---

## **4. Sorting & Comparing Files**

### **Sorting Files**

#### **`sort` Command**

Sorts lines of text alphabetically or numerically.

```bash
sort unsorted.txt > sorted.txt
```

#### **Common Flags:**

- **`-n`**: Numeric sort
- **`-r`**: Reverse order
- **`-u`**: Unique sort (removes duplicates)

```bash
sort -n numbers.txt
```

### **Removing Duplicates**

#### **`uniq` Command**

`uniq` filters out repeated lines. It usually works best on sorted input.

```bash
sort names.txt | uniq > unique_names.txt
```

#### **Flags:**

- **`-c`**: Prepend counts to each unique line
- **`-d`**: Only print duplicate lines

```bash
sort names.txt | uniq -c
```

### **Comparing Files**

#### **`diff` Command**

Compares two files line by line and shows the differences.

```bash
diff file1.txt file2.txt
```

**Flags:**

- **`-u`**: Unified format (more readable)
- **`-i`**: Ignore case differences

```bash
diff -u file1.txt file2.txt
```

#### **`cmp` Command**

`cmp` compares two files byte by byte and is useful for binary files.

```bash
cmp file1.bin file2.bin
```

**Notes:**
- `cmp` outputs nothing if the files are identical; otherwise, it reports the first difference.

---

## **🎯 Summary**

- **File/Directory Checks:**
  - Use test operators like `-e`, `-f`, `-d`, `-r`, `-w`, `-x` to ensure files and directories exist and have proper permissions.
- **Reading/Writing Files:**
  - Use loops (with redirection) and commands like `cat` for reading.
  - Use redirection (`>` and `>>`) or here documents (`<<EOF`) for writing.
- **Searching Files:**
  - `grep` for searching content inside files.
  - `find` for locating files based on patterns, types, or modification times.
  - `locate` for rapid file searches using a prebuilt database.
- **Sorting and Comparing Files:**
  - `sort` and `uniq` for ordering text and removing duplicates.
  - `diff` for comparing file contents line by line.
  - `cmp` for byte-level file comparison.

---

This comprehensive guide should help you confidently manage files and directories in your shell scripts, covering everything from basic existence checks to complex file searching and sorting. Happy scripting! 🚀

---

# **📜 Text Processing & String Manipulation in Shell Scripting**

Text processing is one of the most common and powerful operations in shell scripting. Shell scripts often involve processing logs, parsing data, formatting outputs, and handling text-based configurations. This guide will cover:

- **`awk`** - Text pattern scanning and processing
- **`sed`** - Stream editor for modifying text
- **String Operations** - Extracting, modifying, and manipulating strings
- **Regular Expressions** - Pattern matching with `grep`, `egrep`, and `sed`
- **Pattern Matching** - Using `[[ ... ]]` for string comparisons  

---

## **1️⃣ AWK Basics - The Text Processing Powerhouse**

`awk` is a powerful tool for pattern scanning and text processing.

### **Basic Syntax**

```bash
awk 'pattern { action }' filename
```

### **Example: Print a Specific Column**

```bash
awk '{print $1}' data.txt  # Prints the first column
awk '{print $2, $3}' data.txt  # Prints columns 2 and 3
```

### **Example: Print Lines Matching a Condition**

```bash
awk '$3 > 1000 { print $1, $2 }' employees.txt
```
*(Prints the first and second column where the third column is greater than 1000.)*

### **Built-in Variables**

| Variable | Description |
|----------|-------------|
| `$0`     | Entire line |
| `$1, $2` | Fields (columns) |
| `NR`     | Line number |
| `NF`     | Number of fields (columns) |

```bash
awk '{ print NR, $0 }' data.txt  # Print line number and full line
```

### **Example: Print the Last Column of Each Line**

```bash
awk '{print $NF}' data.txt
```

---

## **2️⃣ SED Basics - The Stream Editor**

`sed` (Stream Editor) is used for modifying text in-place.

### **Basic Syntax**

```bash
sed 's/pattern/replacement/' filename
```

### **Find & Replace First Occurrence in Each Line**

```bash
sed 's/apple/orange/' fruits.txt
```

### **Replace All Occurrences Using `g` (Global)**

```bash
sed 's/apple/orange/g' fruits.txt
```

### **Delete Lines Matching a Pattern**

```bash
sed '/error/d' logs.txt  # Deletes lines containing "error"
```

### **Replace Only in Specific Lines**

```bash
sed '2s/apple/orange/' fruits.txt  # Replaces only in line 2
```

### **Example: Remove Whitespace from Each Line**

```bash
sed 's/^[ \t]*//;s/[ \t]*$//' file.txt
```

*(Removes leading and trailing spaces.)*

---

## **3️⃣ String Operations in Shell Scripting**

### **Find String Length**

```bash
str="Hello, World!"
echo "Length: ${#str}"  # Output: 13
```

### **Extract Substring (`substr`)**

```bash
str="Hello, World!"
echo "${str:7}"    # Output: World!
echo "${str:7:5}"  # Output: World
```

### **Find Index of a Substring (`index`)**

```bash
str="Hello, World!"
expr index "$str" "World"  # Output: 8
```

### **Cut a String (`cut`)**

```bash
echo "hello:world:2024" | cut -d':' -f2  # Output: world
```
*(Splits by `:` and prints the second field.)*

---

## **4️⃣ Regular Expressions (`grep`, `egrep`, `sed -r`)**

### **Using `grep` for Pattern Matching**

```bash
grep "error" logs.txt  # Finds lines containing "error"
grep -i "warning" logs.txt  # Case-insensitive search
grep -E "ERROR|WARNING" logs.txt  # Matches multiple words
```

### **Regular Expressions in `sed` (`-r` for Extended Regex)**

```bash
sed -r 's/[0-9]+/NUM/' data.txt
```
*(Replaces all numbers with "NUM".)*

---

## **5️⃣ Pattern Matching with `[[ ... ]]`**

### **String Equality Check**

```bash
if [[ "$str1" == "$str2" ]]; then
    echo "Strings are equal"
fi
```

### **String Contains Substring**

```bash
if [[ "$str" == *"world"* ]]; then
    echo "String contains 'world'"
fi
```

### **String Starts/Ends With**

```bash
if [[ "$str" == Hello* ]]; then
    echo "Starts with Hello"
fi

if [[ "$str" == *World! ]]; then
    echo "Ends with World!"
fi
```

---

## **🎯 Summary**

| Topic | Description |
|--------|-------------|
| `awk` | Column-based processing, pattern scanning |
| `sed` | Stream editing, find/replace, deletion |
| String Operations | Extracting substrings, length, cutting fields |
| `grep` | Searching text with regex |
| `[[ ... ]]` | Pattern matching and string operations |

Mastering these tools will make you a **text-processing ninja** in shell scripting! 🏆

---

# **⚙️ Process Management & Job Control in Shell Scripting**

In Linux, processes run in either the foreground or the background. Managing them efficiently is crucial for system performance and automation.

## **1️⃣ Background & Foreground Jobs (`bg`, `fg`, `jobs`)**

When you run a command, it executes in the **foreground** by default, meaning it occupies the terminal until it completes. You can send it to the **background** to free the terminal.

### **Run a Process in the Background (`&`)**
```bash
sleep 60 &  # Runs 'sleep 60' in the background
```
📌 **Output:**  
```bash
[1] 12345  # [Job ID] PID (Process ID)
```

### **List Running Jobs (`jobs`)**
```bash
jobs
```
📌 **Example Output:**
```bash
[1]+ Running    sleep 60 &
```

### **Bring a Background Job to the Foreground (`fg`)**
```bash
fg %1  # Brings Job 1 to the foreground
```

### **Send a Foreground Process to the Background (`Ctrl+Z` & `bg`)**
1. **Pause the process:** Press `Ctrl + Z`
2. **Send it to the background:**
   ```bash
   bg %1
   ```

---

## **2️⃣ Process Signals (`kill`, `pkill`, `trap`)**

Processes can be stopped, restarted, or managed using signals.

### **List Running Processes (`ps`, `top`, `htop`)**
```bash
ps aux  # Lists all processes
ps -ef  # Alternative format
top  # Live system monitoring
htop  # Interactive process manager (install separately)
```

### **Kill a Process by PID (`kill`)**
```bash
kill 12345  # Sends default SIGTERM (terminate) signal
kill -9 12345  # Force kill (SIGKILL)
```

### **Kill a Process by Name (`pkill`)**
```bash
pkill firefox  # Kills all 'firefox' processes
pkill -9 chrome  # Force kill Chrome
```

### **Trap Signals (`trap`)**
The `trap` command lets you handle signals inside scripts.

```bash
trap "echo 'Process interrupted! Cleaning up...'; exit 1" SIGINT SIGTERM
while true; do
    echo "Running..."
    sleep 2
done
```
📌 **Now, pressing `Ctrl+C` will trigger the custom message before exiting.** 🔥

---

## **3️⃣ Scheduling Tasks (`cron`, `crontab`, `at`, `batch`)**

### **Run Commands at Specific Intervals (`cron`)**

**Crontab Format:**
```
* * * * * command_to_run
- - - - -
| | | | | 
| | | | └── Day of the week (0-7, Sun=0)
| | | └──── Month (1-12)
| | └────── Day of the month (1-31)
| └──────── Hour (0-23)
└────────── Minute (0-59)
```

### **Example Cron Jobs**
```bash
crontab -e  # Edit the cron table
```
| Cron Expression | Action |
|-----------------|--------|
| `0 * * * * echo "Hourly task"` | Runs every hour |
| `30 2 * * * backup.sh` | Runs `backup.sh` daily at 2:30 AM |
| `*/5 * * * * cleanup.sh` | Runs `cleanup.sh` every 5 minutes |
| `0 0 1 * * report.sh` | Runs `report.sh` on the 1st of every month |

### **One-time Scheduled Tasks (`at`)**
To run a job **once at a specific time**:
```bash
at 14:30
```
📌 **Then enter commands and press `Ctrl+D`.**

### **Batch Processing (`batch`)**
Runs a job **when the system load is low**:
```bash
batch
```
📌 **Then enter the commands to execute.**

---

## **🎯 Summary**

| Command | Description |
|---------|-------------|
| `jobs` | Lists background jobs |
| `fg %1` | Brings job #1 to the foreground |
| `bg %1` | Resumes job #1 in the background |
| `kill PID` | Terminates a process |
| `pkill name` | Kills processes by name |
| `trap` | Captures signals in scripts |
| `cron` | Schedules recurring tasks |
| `at` | Schedules one-time tasks |
| `batch` | Runs tasks when system is idle |

Master these, and you'll have **pro-level process control in Linux!** 🚀

---

# **⚡ Advanced Shell Scripting Techniques**

Once you've mastered the basics, you need **advanced techniques** to write **efficient, reliable, and production-grade shell scripts**.

---

## **1️⃣ Command Substitution (`$(command)`, `` `command` ``)**

Command substitution allows you to **store** or **use the output** of a command inside another command or a variable.

### **✅ Syntax**
```bash
VAR=$(command)   # Recommended modern syntax
VAR=`command`    # Old backtick syntax (Avoid)
```

### **🔹 Example**
```bash
DATE=$(date +"%Y-%m-%d")  # Stores today's date in DATE variable
echo "Today is $DATE"
```
📌 **Output:**  
```bash
Today is 2025-02-05
```

### **🔹 Use in Strings**
```bash
echo "Current user: $(whoami)"
echo "Home directory: $(echo $HOME)"
```

📌 **Why Prefer `$(command)` Over Backticks?**
- **Nested commands** work in `$( )`, but are tricky with backticks.
```bash
echo "$(echo "Hello, $(whoami)")"
```
✅ **Works fine** with `$( )`, but backticks require escaping.

---

## **2️⃣ Arithmetic Operations (`expr`, `bc`, `$(( ))`)**

Shell scripting supports **basic arithmetic**, but **floating-point operations** require `bc`.

### **✅ Integer Arithmetic (`$(( ))`)**
```bash
x=10
y=5
sum=$((x + y))  # Addition
echo "Sum: $sum"
```

📌 **Operators:**
| Operator | Meaning |
|----------|---------|
| `+` | Addition |
| `-` | Subtraction |
| `*` | Multiplication |
| `/` | Division (Integer only) |
| `%` | Modulus (Remainder) |
| `**` | Exponentiation |

---

### **✅ Floating-Point Arithmetic (`bc`)**
```bash
result=$(echo "scale=2; 10 / 3" | bc)
echo "10 / 3 = $result"
```
📌 **Output:**  
```bash
10 / 3 = 3.33
```

### **✅ Using `expr` (Older Method)**
```bash
sum=$(expr 10 + 5)
echo "Sum: $sum"
```
📌 **Notes:**
- **Spaces** are required between numbers and operators.
- **Use `$(( ))` for modern scripts.**

---

## **3️⃣ Debugging Scripts (`set -x`, `trap`, `bash -x script.sh`)**

Debugging is essential for **troubleshooting complex scripts**.

### **✅ Enable Debug Mode (`set -x`)**
```bash
#!/bin/bash
set -x  # Enables debugging
echo "This is a test"
set +x  # Disables debugging
```
📌 **Output (Shows each command before execution):**
```bash
+ echo 'This is a test'
This is a test
```

### **✅ Run Script in Debug Mode (`bash -x`)**
```bash
bash -x script.sh
```

### **✅ Capture Errors Using `trap`**
```bash
trap 'echo "Error at line $LINENO"; exit 1' ERR
ls nonexistentfile  # This will trigger the error trap
```

---

## **4️⃣ Error Handling (`||`, `&&`, `set -e`, `set -u`)**

### **✅ Conditional Execution (`||` and `&&`)**
```bash
mkdir test_dir && cd test_dir  # If mkdir succeeds, then cd
rm file.txt || echo "File not found"  # If rm fails, print message
```

### **✅ Stop Script on First Error (`set -e`)**
```bash
set -e
cp file1.txt backup/  # If this fails, script exits immediately
```

### **✅ Treat Unset Variables as Errors (`set -u`)**
```bash
set -u
echo "Username: $USER_VAR"  # If USER_VAR is unset, script exits
```

---

## **5️⃣ Logging (`tee`, `logger`)**

Logging is essential for **monitoring script execution**.

### **✅ Log Output to File (`tee`)**
```bash
echo "Script started" | tee -a script.log
```
📌 **Writes to both terminal and `script.log`.**

### **✅ System Logs (`logger`)**
```bash
logger -p user.info "Custom log message"
```
📌 **Writes to `/var/log/syslog` (Linux) or `/var/log/messages` (Mac).**

---

## **🎯 Summary**

| Feature | Command | Use Case |
|---------|---------|----------|
| **Command Substitution** | `$(command)` | Store output of a command in a variable |
| **Integer Math** | `$(( ))` | Simple arithmetic (`+`, `-`, `*`, `/`, `%`) |
| **Floating-Point Math** | `bc` | Precise decimal calculations |
| **Debugging** | `set -x`, `bash -x script.sh` | See command execution step-by-step |
| **Error Handling** | `set -e`, `trap` | Stop script on errors |
| **Logging** | `tee`, `logger` | Store script output in logs |

Master these techniques and you'll be scripting like a **pro Linux admin!** 🚀

---

# **🌐 Networking & Automation in Shell Scripting**

Shell scripting can be **powerful for automating networking tasks**, such as **fetching remote data, checking network status, executing remote commands, and even web scraping.** Let’s dive deep! 🔥

---

## **1️⃣ Fetching Remote Data (`wget`, `curl`)**

Fetching data from the internet is a common task, and we use **`wget`** and **`curl`** for this.

### **✅ `wget` – Downloading Files**
`wget` is used for **downloading files** from the web.

#### **🔹 Basic Usage**
```bash
wget https://example.com/file.zip
```
📌 **This downloads `file.zip` from `example.com`.**

#### **🔹 Download with Custom Filename**
```bash
wget -O myfile.zip https://example.com/file.zip
```

#### **🔹 Download Multiple Files**
```bash
wget -i urls.txt  # Reads URLs from a file
```

#### **🔹 Resume Interrupted Downloads**
```bash
wget -c https://example.com/largefile.zip
```

---

### **✅ `curl` – Fetch Data & APIs**
`curl` is more powerful than `wget`, as it supports **APIs, JSON, authentication, and more**.

#### **🔹 Basic Usage**
```bash
curl https://example.com
```

#### **🔹 Save Output to File**
```bash
curl -o output.html https://example.com
```

#### **🔹 Download Large Files (Resume Support)**
```bash
curl -C - -O https://example.com/largefile.zip
```

#### **🔹 Fetch API Response**
```bash
curl -s https://api.github.com/users/octocat
```

#### **🔹 Send POST Request**
```bash
curl -X POST -d "name=John" https://example.com/api
```

---

## **2️⃣ Checking Network Status (`ping`, `netstat`, `traceroute`)**

Network troubleshooting is crucial in system administration.

### **✅ `ping` – Check if a Host is Reachable**
```bash
ping -c 4 google.com
```
📌 **Sends 4 packets to `google.com` and checks response time.**

---

### **✅ `netstat` – View Network Connections**
```bash
netstat -tulnp
```
📌 **Shows all active network connections and listening ports.**  
- `-t` → TCP connections  
- `-u` → UDP connections  
- `-l` → Listening ports  
- `-n` → Show numeric IPs instead of resolving names  
- `-p` → Show process ID using the port  

🔹 **Alternative in modern systems:** Use `ss`
```bash
ss -tulnp
```

---

### **✅ `traceroute` – Trace Network Route**
```bash
traceroute google.com
```
📌 **Shows each hop a packet takes to reach the destination.**  

---

## **3️⃣ Remote Execution (`ssh`, `scp`, `rsync`)**

### **✅ `ssh` – Secure Remote Access**
```bash
ssh user@remote-server
```
📌 **Logs into a remote server as `user`.**

#### **🔹 Execute Command on Remote Machine**
```bash
ssh user@remote-server "ls -l /home/user"
```

#### **🔹 Run Script on Remote Server**
```bash
ssh user@remote-server 'bash -s' < local_script.sh
```

---

### **✅ `scp` – Secure Copy Between Machines**
```bash
scp file.txt user@remote-server:/home/user/
```
📌 **Copies `file.txt` to remote server.**

#### **🔹 Copy Remote File to Local**
```bash
scp user@remote-server:/home/user/file.txt .
```

---

### **✅ `rsync` – Efficient File Sync**
```bash
rsync -avz file.txt user@remote-server:/home/user/
```
📌 **Syncs file efficiently with compression.**

#### **🔹 Sync Entire Directory**
```bash
rsync -avz /local/folder/ user@remote-server:/remote/folder/
```

---

## **4️⃣ Web Scraping Basics (`curl`, `grep`, `jq`)**

### **✅ `curl` + `grep` – Extract Specific Data**
```bash
curl -s https://example.com | grep "keyword"
```

### **✅ `curl` + `jq` – Parse JSON APIs**
```bash
curl -s https://api.github.com/users/octocat | jq '.name'
```
📌 **Extracts `name` field from JSON response.**

---

## **5️⃣ Automated Backup Scripts**

### **✅ Simple Backup Script**
```bash
#!/bin/bash

# Variables
SOURCE_DIR="/home/user/documents"
BACKUP_DIR="/home/user/backup"
TIMESTAMP=$(date +"%Y%m%d_%H%M%S")
BACKUP_FILE="backup_$TIMESTAMP.tar.gz"

# Create Backup
tar -czf "$BACKUP_DIR/$BACKUP_FILE" "$SOURCE_DIR"

# Show Message
echo "Backup created: $BACKUP_FILE"
```

📌 **Schedule this with `cron` for automatic backups!**

---

## **🎯 Summary**

| Feature | Command | Use Case |
|---------|---------|----------|
| **Fetching Data** | `wget`, `curl` | Download files, fetch API responses |
| **Network Check** | `ping`, `netstat`, `traceroute` | Troubleshoot network issues |
| **Remote Execution** | `ssh`, `scp`, `rsync` | Access and copy files remotely |
| **Web Scraping** | `curl`, `grep`, `jq` | Extract data from web pages |
| **Automation** | `cron`, `tar`, `rsync` | Automate backups and syncing |

Master these networking and automation techniques, and you'll be scripting like a **pro sysadmin!** 🚀

---



