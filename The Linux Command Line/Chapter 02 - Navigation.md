# Chapter 02 - Navigation

## 📖 Overview

Navigation is one of the most fundamental Linux skills. Before working with files, scripts, or system administration, you must understand how to move around the Linux filesystem. Linux organizes files using a **hierarchical directory structure (filesystem tree)**, and the command line provides simple commands to navigate it efficiently.

---

# 🌳 Filesystem Tree

Linux stores files in a **hierarchical directory structure**, commonly known as the **filesystem tree**.

### Key Concepts

- 🌱 The top of the filesystem is the **root directory (`/`)**.
- 📂 Every file and directory exists somewhere under the root directory.
- 📁 Directories can contain both **files** and **subdirectories**.
- 💽 Unlike Windows, Linux uses **a single filesystem tree**, regardless of how many storage devices are connected.
- 🔗 Additional storage devices are **mounted** into the existing filesystem instead of receiving separate drive letters.

### Example

```text
/
├── home
│   └── ayoub
├── usr
│   └── bin
├── etc
├── var
└── tmp
```

---

# 📍 Current Working Directory (CWD)

The **Current Working Directory (CWD)** is the directory you are currently working in.

When you open a terminal, Linux automatically places you inside your **home directory**.

Display the current directory using:

```bash
pwd
```

Example:

```text
/home/ayoub
```

> 💡 **pwd** stands for **Print Working Directory**.

---

# 🏠 Home Directory

Every user has a personal **home directory**.

Examples:

```text
/home/ayoub
/home/john
```

The home directory is commonly used to:

- 📄 Store personal files
- 📚 Save documents
- 💻 Keep projects
- ⚙️ Store application configuration files

Regular users normally have write permission only inside their own home directory.

---

# 📂 Listing Directory Contents

Use the **ls** command to display files and directories.

```bash
ls
```

Example output:

```text
Desktop
Documents
Downloads
Music
Pictures
Videos
```

You can also list another directory directly.

Example:

```bash
ls /usr/bin
```

---

# 🚀 Changing Directories

Use the **cd** command to move between directories.

Syntax:

```bash
cd directory_name
```

Example:

```bash
cd Documents
```

---

# 🛣️ Pathnames

A **pathname** specifies the location of a file or directory.

There are two types:

- 📌 Absolute Pathname
- 🔄 Relative Pathname

---

# 📌 Absolute Pathname

An **absolute pathname** always starts from the **root directory (`/`)**.

Example:

```bash
cd /usr/bin
```

Filesystem path:

```text
/
└── usr
    └── bin
```

### Advantages

- ✅ Always points to the same location.
- ✅ Independent of the current directory.

---

# 🔄 Relative Pathname

A **relative pathname** starts from the **current working directory**.

Example:

Current directory:

```text
/usr
```

Command:

```bash
cd bin
```

Result:

```text
/usr/bin
```

Linux assumes the path starts from the current directory.

### Advantages

- ✅ Shorter to type.
- ✅ Faster for everyday use.
- ✅ Commonly used by Linux users.

> 💡 Relative pathnames are generally preferred whenever possible because they require less typing.

---

# 📂 Special Directory Symbols

Linux provides two special symbols for navigation.

## 📍 Current Directory (`.`)

The **dot (`.`)** represents the **current directory**.

Example:

```bash
cd ./bin
```

Usually, `./` can be omitted.

These commands are identical:

```bash
cd ./bin
cd bin
```

---

## ⬆️ Parent Directory (`..`)

The **double dot (`..`)** represents the **parent directory**.

Example:

Current location:

```text
/usr/bin
```

Command:

```bash
cd ..
```

Result:

```text
/usr
```

---

# ⚖️ Absolute vs Relative Pathnames

Absolute:

```bash
cd /usr/bin
```

Relative:

```bash
cd bin
```

If your current directory is `/usr`, both commands reach the same destination.

> 💡 Use the shorter command whenever possible.

---

# 📝 Important Facts About Filenames

## 👀 Hidden Files

Files whose names begin with a period (`.`) are **hidden**.

Examples:

```text
.bashrc
.profile
.gitignore
```

Display hidden files using:

```bash
ls -a
```

---

## 🔠 Case Sensitivity

Linux filenames are **case-sensitive**.

These are three different files:

```text
file.txt
File.txt
FILE.txt
```

---

## 📄 File Extensions

Linux does **not** rely on file extensions to determine file types.

Examples:

```text
notes
notes.txt
notes.pdf
```

Applications may use extensions, but Linux itself does not require them.

---

## ✍️ Naming Recommendations

### ✅ Recommended

- Letters
- Numbers
- Hyphens (`-`)
- Underscores (`_`)
- Periods (`.`)

Examples:

```text
linux_notes.md
python_summary.md
chapter_02.md
```

### ❌ Avoid

- Spaces
- Special symbols

Bad examples:

```text
Linux Notes.md
My File!.txt
```

> 💡 Use underscores (`_`) instead of spaces to avoid command-line issues.

---

# ⚡ Useful `cd` Shortcuts

## 🏠 Go to Home Directory

```bash
cd
```

or

```bash
cd ~
```

---

## 🔙 Return to Previous Directory

```bash
cd -
```

---

## 👤 Go to Another User's Home Directory

```bash
cd ~username
```

Example:

```bash
cd ~bob
```

---

# 📋 Commands Learned

| Command | Description |
|----------|-------------|
| `pwd` | Print the current working directory |
| `ls` | List directory contents |
| `cd` | Change the current working directory |

---

# ✅ Key Takeaways

- 🌳 Linux uses a **single hierarchical filesystem tree**.
- 🌱 The root directory (`/`) is the starting point of the filesystem.
- 🏠 Every user has a personal home directory.
- 📍 `pwd` displays the current working directory.
- 📂 `ls` lists files and directories.
- 🚀 `cd` changes the current working directory.
- 📌 Absolute pathnames start from the root directory.
- 🔄 Relative pathnames start from the current working directory.
- 📍 `.` represents the current directory.
- ⬆️ `..` represents the parent directory.
- 👀 Hidden files begin with a period (`.`).
- 🔠 Linux filenames are case-sensitive.
- ✍️ Avoid spaces in filenames; use underscores (`_`) or hyphens (`-`) instead.