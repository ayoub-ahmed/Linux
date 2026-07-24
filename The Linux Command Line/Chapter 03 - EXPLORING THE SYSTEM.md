
# 3 🐧 EXPLORING THE SYSTEM

Now that we know how to move around the filesystem, it is time for a guided tour of our Linux system.

Before exploring, we will learn some useful commands:

| Command | Description |
|---|---|
| `ls` 📂 | List directory contents |
| `file` 🔍 | Determine file type |
| `less` 📖 | View file contents |

---

# More Fun with `ls` 📂

The `ls` command is one of the most frequently used Linux commands.

It allows us to:

- View directory contents
- Identify files and directories
- Examine important file attributes

The simplest usage:

```bash
ls
````

Example:

```text
Desktop
Documents
Music
Pictures
Public
Templates
Videos
```

---

## Listing a Specific Directory

We can specify a directory path:

```bash
ls /usr
```

Example:

```text
bin
games
include
lib
local
sbin
share
src
```

---

## Listing Multiple Directories

The `ls` command can display multiple directories:

```bash
ls ~ /usr
```

Example:

```text
/home/me:
Desktop Documents Music Pictures Public Templates Videos

/usr:
bin games include lib local sbin share src
```

---

## Long Format Listing 🔎

The output format can be changed using:

```bash
ls -l
```

Example:

```text
drwxrwxr-x 2 me me 4096 2025-10-26 17:20 Desktop
drwxrwxr-x 2 me me 4096 2025-10-26 17:20 Documents
drwxrwxr-x 2 me me 4096 2025-10-26 17:20 Music
```

The option `-l` enables the **long format**, showing additional information about files.

---

# Options and Arguments ⚙️

Most Linux commands follow this structure:

```bash
command -options arguments
```

A command can have:

- **Options** → modify the command behavior
    
- **Arguments** → specify the objects the command acts on
    

Example:

```bash
ls -lt
```

Explanation:

|Part|Meaning|
|---|---|
|`ls`|Command|
|`-l`|Long format|
|`-t`|Sort by modification time|

---

## Short Options and Long Options

Short options use one character after a dash:

```bash
-l
```

Long options use a word after two dashes:

```bash
--reverse
```

Example:

```bash
ls -lt --reverse
```

This reverses the sorting order.

> ⚠️ Command options and filenames in Linux are case-sensitive.

Example:

```text
-l ≠ -L
```

---

# Table 3-1: Common `ls` Options 📋

|Option|Long Option|Description|
|---|---|---|
|`-a`|`--all`|Lists all files, including hidden files beginning with a period (`.`).|
|`-A`|`--almost-all`|Like `-a`, but does not show `.` and `..`.|
|`-d`|`--directory`|Shows information about a directory itself instead of its contents.|
|`-F`|`--classify`|Adds an indicator character to filenames (for example `/` for directories).|
|`-h`|`--human-readable`|Displays file sizes in a human-readable format.|
|`-l`||Displays results in long format.|
|`-r`|`--reverse`|Displays results in reverse order.|
|`-S`||Sorts results by file size.|
|`-t`||Sorts results by modification time.|

---



# A Longer Look at Long Format 🔎

As we saw earlier, the `-l` option makes `ls` display information in long format.

This format provides important details about files.

Example:

```text
-rw-r--r-- 1 root root 3576296 2017-04-03 11:05 Experience ubuntu.ogg
-rw-r--r-- 1 root root 1186219 2017-04-03 11:05 kubuntu-leaflet.png
-rw-r--r-- 1 root root 47584 2017-04-03 11:05 logo-Edubuntu.png
````

A long listing contains several fields describing the file.

---

# Table 3-2: Long Listing Fields for `ls` 📋

| Field              | Meaning                                                                                                                                                                                                                                                                                             |
| ------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `-rw-r--r--` 🔐    | File access rights. The first character indicates the file type. A `-` means a regular file, while `d` means a directory. The next three characters represent the owner's permissions, the next three represent the group permissions, and the final three represent permissions for everyone else. |
| `1`                | Number of hard links associated with the file.                                                                                                                                                                                                                                                      |
| `root`             | Username of the file owner.                                                                                                                                                                                                                                                                         |
| `root`             | Name of the group that owns the file.                                                                                                                                                                                                                                                               |
| `32059`            | File size in bytes.                                                                                                                                                                                                                                                                                 |
| `2017-04-03 11:05` | Date and time of the last modification.                                                                                                                                                                                                                                                             |
| `oo-cd-cover.odf`  | Name of the file.                                                                                                                                                                                                                                                                                   |

---

# Determining a File’s Type with `file` 🔍

When exploring Linux, it is useful to know what kind of data a file contains.

The `file` command determines the actual file type.

Usage:

```bash
file filename
```

Example:

```bash
file picture.jpg
```

Output:

```text
picture.jpg: JPEG image data, JFIF standard 1.01
```

---

## Everything Is a File 🐧

One of the fundamental ideas in Unix-like systems is:

> Everything is a file.

Linux treats many system resources as files, including:

- Regular files
    
- Devices
    
- System information
    

File extensions are not required to match the actual content.

For example:

```text
picture.jpg
```

does not necessarily mean the file contains a JPEG image.

The `file` command checks the content instead of relying on the filename.

---

# Viewing File Contents with `less` 📖

The `less` command is used to view text files.

Usage:

```bash
less filename
```

Example:

```bash
less /etc/passwd
```

---

## Why View Text Files?

Many important Linux files are stored as readable text.

Examples:

- Configuration files ⚙️
    
- System settings
    
- Shell scripts 📝
    

Reading these files helps us understand how Linux works.

Later, we will learn how to:

- Edit configuration files
    
- Modify system settings
    
- Write our own scripts
    

For now, we only examine their contents.

---

# WHAT IS “TEXT”? 📝

Computers represent all information using numbers.

Every piece of data is converted into a numeric representation.

Some formats are complex, such as:

- Compressed video files
    
- Multimedia formats
    

Others are simple, such as:

## ASCII Text

ASCII stands for:

**American Standard Code for Information Interchange**

It is a simple encoding system that maps characters to numbers.

Example:

```text
A → 65
B → 66
```

---

## Plain Text vs Documents

Plain text is a simple mapping:

```
Character → Number
```

Example:

50 characters of text:

```
50 characters = 50 bytes
```

Plain text files contain:

- Characters
    
- Numbers
    
- Basic control codes
    

Such as:

- Tabs
    
- Carriage returns
    
- Line feeds
    

---

Unlike plain text, documents created by:

- Microsoft Word
    
- LibreOffice Writer
    

contain additional information:

- Formatting
    
- Fonts
    
- Layout
    
- Document structure
    

---

Linux uses text files extensively.

Many Linux tools are designed to work with text files.

Even Windows includes:

```text
NOTEPAD.EXE
```

which is a plain ASCII text editor.

---


# Using `less` 📖

Once the `less` program starts, it allows us to scroll forward and backward through a text file.

Example:

```bash
less /etc/passwd
````

The `/etc/passwd` file contains information about system user accounts.

If the file is longer than one screen, we can move through it page by page.

To exit `less`:

```text
q
```

---

# Table 3-3: `less` Commands ⌨️

| Command                | Action                                                |
| ---------------------- | ----------------------------------------------------- |
| `PAGE UP` or `b`       | Scroll back one page                                  |
| `PAGE DOWN` or `SPACE` | Scroll forward one page                               |
| `↑` Up arrow           | Scroll up one line                                    |
| `↓` Down arrow         | Scroll down one line                                  |
| `G`                    | Move to the end of the text file                      |
| `1G` or `g`            | Move to the beginning of the text file                |
| `/characters`          | Search forward for characters                         |
| `n`                    | Search for the next occurrence of the previous search |
| `h`                    | Display help screen                                   |
| `q`                    | Quit `less`                                           |

---

# LESS IS MORE 📚

The `less` program was designed as an improved replacement for an older Unix program called `more`.

The name `less` comes from the phrase:

> "Less is more"

---

## Pager Programs

`less` belongs to a category of programs called **pagers**.

Pagers allow users to view long text documents page by page.

Comparison:

|Program|Features|
|---|---|
|`more`|Can move forward through text only|
|`less`|Can move forward and backward and provides additional features|

---

# Taking a Guided Tour 🗺️

The Linux filesystem layout is similar to other Unix-like systems.

The design is based on a standard called:

**Linux Filesystem Hierarchy Standard (FHS)**

Not all Linux distributions follow the standard exactly, but most are very similar.

---

During this tour, we will explore the filesystem and practice navigation skills.

Many interesting Linux files are stored as human-readable text.

---

## Exploration Steps 🔍

When exploring directories:

### 1. Enter a directory

```bash
cd directory
```

### 2. List directory contents

```bash
ls -l
```

### 3. Check interesting files

```bash
file filename
```

### 4. View text files

```bash
less filename
```

---

## Recovering the Terminal 🛠️

If we accidentally open a non-text file and the terminal display becomes corrupted:

```bash
reset
```

can restore the terminal.

---

## Copy and Paste Tip 💡

When using a mouse:

- Double-click a filename → copy it
    
- Middle-click → paste it into commands
    

---

Linux encourages exploration.

Normal users are usually protected from damaging important system files.

The system administrator has the responsibility of managing system-wide changes.

If a command produces an error, simply continue exploring.

> In Linux, there are no secrets. 🐧

---

# Table 3-4: Directories on Linux Systems 📁

| Directory                  | Comments                                                                                                                                     |     |
| -------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------- | --- |
| `/`                        | The root directory where everything begins.                                                                                                  |     |
| `/bin`                     | Contains essential binary programs required for the system to boot and run. Modern Linux distributions have replaced it with `/usr/bin`.     |     |
| `/boot`                    | Contains the Linux kernel, initial RAM disk image, and boot loader files. Important files include `/boot/grub/grub.cfg` and `/boot/vmlinuz`. |     |
| `/dev`                     | Contains device nodes. Linux treats devices as files, and the kernel maintains information about devices here.                               |     |
| `/etc`                     | Contains system-wide configuration files. Examples include `/etc/crontab`, `/etc/fstab`, and `/etc/passwd`.                                  |     |
| `/home`                    | Contains user home directories. Normal users can write files only in their own home directories.                                             |     |
| `/lib`                     | Contains shared libraries used by core system programs. Similar to Windows DLL files. Modern systems use `/usr/lib`.                         |     |
| `/lost+found`              | Used for filesystem recovery after corruption. Usually remains empty unless a recovery event occurs.                                         |     |
| `/media`                   | Contains mount points for removable media such as USB drives and CD-ROMs.                                                                    |     |
| `/mnt`                     | Contains mount points for manually mounted devices.                                                                                          |     |
| `/opt`                     | Used for installing optional software, often third-party applications.                                                                       |     |
| `/proc`                    | A virtual filesystem maintained by the Linux kernel. Provides information about the kernel and hardware.                                     |     |
| `/root`                    | Home directory of the root user.                                                                                                             |     |
| `/run`                     | Stores runtime data in memory using tmpfs. Modern replacement for some uses of `/tmp`.                                                       |     |
| `/sbin`                    | Contains system administration binaries used for important system tasks. Modern systems use `/usr/sbin`.                                     |     |
| `/sys`                     | Contains detailed information about hardware devices detected by the kernel.                                                                 |     |
| `/tmp`                     | Stores temporary files created by programs. Some distributions clear it during reboot.                                                       |     |
| `/usr`                     | Contains programs and support files used by normal users. One of the largest directories on Linux systems.                                   |     |
| `/usr/bin`                 | Contains executable programs installed by the Linux distribution.                                                                            |     |
| `/usr/lib`                 | Contains shared libraries used by programs in `/usr/bin`.                                                                                    |     |
| `/usr/local`               | Contains software installed manually by administrators, commonly from source code.                                                           |     |
| `/usr/sbin`                | Contains additional system administration programs.                                                                                          |     |
| `/usr/share`               | Contains shared data used by programs, such as configuration files, icons, backgrounds, and sound files.                                     |     |
| `/usr/share/doc`           | Contains documentation files organized by installed packages.                                                                                |     |
| `/var`                     | Stores data that changes frequently, such as databases, print queues, and user mail.                                                         |     |
| `/var/log`                 | Contains system log files used for monitoring and troubleshooting.                                                                           |     |
| `~/.config` and `~/.local` | Store user-specific configuration and application state data for desktop applications.                                                       |     |

---


# Symbolic Links 🔗

While exploring Linux directories, we may find entries like this:

```text
lrwxrwxrwx 1 root root 11 2025-08-11 07:34 libc.so.6 -> libc-2.6.so
````

Notice:

- The first character is `l`
    
- The listing appears to contain two filenames
    

This indicates a special type of file called a:

- **Symbolic Link**
    
- **Soft Link**
    
- **Symlink**
    

---

## What Is a Symbolic Link?

A symbolic link is a file that points to another file.

It allows one file to be accessed using multiple names.

This is useful because the actual file can change while programs continue using the same name.

---

## Why Use Symbolic Links? 💡

Imagine a program needs a shared resource called:

```text
foo
```

However, the file has frequent version updates.

Instead of changing every program whenever the version changes, we create a symbolic link.

Example:

Actual file:

```text
foo-2.6
```

Symbolic link:

```text
foo → foo-2.6
```

When a program opens:

```text
foo
```

it actually accesses:

```text
foo-2.6
```

---

## Updating Versions 🔄

Suppose a new version is released:

```text
foo-2.7
```

We can:

1. Install the new file
    
2. Remove the old symbolic link
    
3. Create a new link:
    

```text
foo → foo-2.7
```

Advantages:

✅ Programs continue working  
✅ The installed version remains visible  
✅ Multiple versions can exist at the same time  
✅ Easy rollback if the new version has problems

---

## Example: Linux Shared Libraries

In a Fedora system, we may see:

```text
libc.so.6 -> libc-2.6.so
```

This means:

Programs requesting:

```text
libc.so.6
```

actually receive:

```text
libc-2.6.so
```

The symbolic link hides version changes from applications.

---

# Hard Links 🔗

Hard links are another type of link in Linux.

Like symbolic links, they allow files to have multiple names.

However, they work differently internally.

A hard link points directly to the file data, while a symbolic link points to another filename.

The differences between:

- Symbolic Links
    
- Hard Links
    

will be explained in a later chapter.

---

# Summing Up ✅

After completing this tour, we learned many important concepts about the Linux system.

We explored:

- Files and directories 📁
    
- File types 🔍
    
- Text files 📖
    
- Filesystem structure 🗂️
    
- Symbolic links 🔗
    
- Hard links
    

---

## Key Idea 💡

One of the most important characteristics of Linux is openness.

Many important system files are stored as plain human-readable text.

Unlike many proprietary systems, Linux allows users to:

- Examine system files
    
- Study how the system works
    
- Understand internal components
    

> Linux makes everything available for examination and learning. 🐧
