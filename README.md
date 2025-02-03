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
