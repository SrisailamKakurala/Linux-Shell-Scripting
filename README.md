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