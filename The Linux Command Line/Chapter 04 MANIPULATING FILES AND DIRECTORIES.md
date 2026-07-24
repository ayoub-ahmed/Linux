# 4 🐧 MANIPULATING FILES AND DIRECTORIES

Managing files and directories is one of the most common tasks in Linux. This chapter introduces the core commands used to create, copy, move, delete, and link files and directories.

## Commands Covered

| Command | Description |
|---------|-------------|
| `cp` | Copy files and directories |
| `mv` | Move or rename files and directories |
| `mkdir` | Create directories |
| `rm` | Remove files and directories |
| `ln` | Create hard and symbolic links |

These commands are among the most frequently used commands in Linux and form the foundation of everyday file management.

---

## Why Use the Command Line?

Most file operations can be performed using a graphical file manager (GUI), such as:

- Drag and drop files
- Copy and paste
- Rename files
- Delete files

However, the command line offers much greater **power, flexibility, and automation**.

For example, copying only HTML files that are newer than those in another directory is difficult in a GUI but very simple from the terminal:

```bash
cp -u *.html destination/
```

This command copies only:

- Files that do not already exist in the destination.
- Files that are newer than the existing copies.

As tasks become more complex, the command line becomes significantly faster and more efficient than graphical tools.

---

# Wildcards (Globbing)

Before learning the file manipulation commands, it's important to understand **wildcards**, one of the shell's most powerful features.

Wildcards (also called **globbing**) allow the shell to match filenames using patterns instead of typing each filename individually.

Instead of specifying every filename manually, you describe a pattern and let the shell find all matching files.

---

## Common Wildcards

| Wildcard | Meaning |
|-----------|---------|
| `*` | Matches zero or more characters |
| `?` | Matches exactly one character |
| `[abc]` | Matches any one character inside the brackets |
| `[!abc]` or `[^abc]` | Matches any character except those inside the brackets |
| `[[:class:]]` | Matches any character belonging to a character class |

---

## Character Classes

Character classes provide a portable way to match groups of characters.

| Character Class | Matches |
|-----------------|---------|
| `[:alnum:]` | Letters and numbers |
| `[:alpha:]` | Alphabetic letters |
| `[:digit:]` | Numbers |
| `[:lower:]` | Lowercase letters |
| `[:upper:]` | Uppercase letters |

---

## Wildcard Examples

| Pattern | Matches |
|----------|---------|
| `*` | All files |
| `g*` | Files beginning with `g` |
| `b*.txt` | Files beginning with `b` and ending with `.txt` |
| `Data???` | `Data` followed by exactly three characters |
| `[abc]*` | Files beginning with `a`, `b`, or `c` |
| `BACKUP.[0-9][0-9][0-9]` | `BACKUP.` followed by exactly three digits |
| `[[:upper:]]*` | Files beginning with an uppercase letter |
| `[![:digit:]]*` | Files that do not begin with a number |
| `*[[:lower:]123]` | Files ending with a lowercase letter or `1`, `2`, or `3` |

---

## Wildcards in Graphical File Managers

Wildcards are not limited to the command line.

Many Linux graphical file managers also support wildcard patterns.

### GNOME (Nautilus)

- Press **Ctrl + S**.
- Enter a wildcard pattern.
- Matching files in the current directory are selected.

### KDE (Dolphin / Konqueror)

Wildcards can be entered in:

- the **Location Bar**, or
- the **Filter** option.

Example:

```text
/usr/bin/u*
```

Displays every file inside `/usr/bin` whose name starts with **u**.

This demonstrates that many features originally developed for the shell are also available in modern graphical interfaces.

---

## Key Points

- Wildcards simplify filename selection.
- They eliminate the need to type every filename.
- Wildcards work with most commands that accept filenames.
- They are also supported by several Linux file managers.

---

# Dot Files

Files and directories whose names begin with a dot (`.`) are called **hidden files**.

Examples:

```text
.bashrc
.profile
.gitconfig
```

Hidden files are **not** special files.

Their names simply begin with a dot, causing commands such as `ls` to hide them by default.

Display hidden files using:

```bash
ls -a
```

or

```bash
ls -A
```

---

## Wildcards and Hidden Files

The wildcard

```bash
*
```

does **not** match hidden files.

To include hidden files:

```bash
.*
```

Depending on the shell configuration, this may also match:

```text
.
..
```

To exclude them, use patterns such as:

```bash
.[!.]*
```

or

```bash
.??*
```

---

## Character Ranges

Traditional Unix patterns like

```bash
[A-Z]
[a-z]
```

may not behave consistently because their behavior depends on locale settings.

Instead, the book recommends using character classes:

```bash
[[:upper:]]
```

```bash
[[:lower:]]
```

These are more portable and reliable across Linux systems.

---

## Key Points

- Hidden files begin with a dot (`.`).
- `ls -a` displays all hidden files.
- `*` does not match hidden files.
- Prefer character classes over traditional character ranges.

---

# mkdir — Create Directories

The `mkdir` command creates one or more directories.

## Syntax

```bash
mkdir directory...
```

The three dots (`...`) indicate that multiple directory names can be supplied.

---

## Create One Directory

```bash
mkdir dir1
```

Creates a single directory named `dir1`.

---

## Create Multiple Directories

```bash
mkdir dir1 dir2 dir3
```

Creates three directories using one command.

---

## Key Points

- Creates directories.
- Accepts multiple directory names.
- One command can create several directories simultaneously.
- The `...` notation in command syntax means the argument can be repeated.