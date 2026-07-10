# 🐧 Chapter 1 - The Shell & Terminal Basics

## 💻 What is the Shell?

The **Shell** is a program that receives commands from the keyboard and sends them to the operating system for execution.

Most Linux distributions use **Bash (Bourne Again Shell)**, an improved version of the original Unix shell (**sh**).

> **Flow:**  
> ⌨️ Keyboard → 🐚 Shell → 🐧 Operating System → ✅ Result

---

# 🖥️ Terminal Emulator

A **Terminal Emulator** is a graphical application that gives you access to the shell.

Examples:

- **GNOME** → `gnome-terminal`
- **KDE** → `Konsole`

---

# 📍 Shell Prompt

Example:

```bash
[me@linuxbox ~]$
```

Meaning:

| Symbol | Description |
|--------|-------------|
| `me` | Username |
| `linuxbox` | Computer name |
| `~` | Home directory |
| `$` | Regular user |

If the prompt ends with:

```bash
#
```

⚠️ You are logged in as the **Root (Superuser)**.

---

# ❌ Invalid Commands

Example:

```bash
kaekfjaeifj
```

Output:

```bash
command not found
```

💡 Bash couldn't find a command with that name.

---

# 🕘 Command History

The shell remembers previously executed commands.

| Key | Action |
|-----|--------|
| ⬆️ | Previous command |
| ⬇️ | Next command |

---

# ✏️ Cursor Movement

Edit commands without retyping them.

| Key | Action |
|-----|--------|
| ⬅️ | Move left |
| ➡️ | Move right |

---

# 📋 Copy & Paste

Default terminal shortcuts:

| Shortcut | Action |
|----------|--------|
| `Ctrl + Shift + C` | 📄 Copy |
| `Ctrl + Shift + V` | 📌 Paste |

You can also:

- 🖱️ Select text with the mouse.
- 🖱️ Click the middle mouse button to paste.

> **Note:** `Ctrl + C` ❌ is **not Copy** in the terminal. It interrupts the running process.

---

# ⚡ Basic Commands

### 🗓️ Show Date & Time

```bash
date
```

Displays the current date and time.

---

### ⏳ Check System Uptime

```bash
uptime
```

Shows:

- System uptime
- Logged-in users
- Load average

---

### 💾 Check Disk Space

```bash
df
```

Displays disk usage information.

---

### 🧠 Check Memory Usage

```bash
free
```

Displays RAM and Swap usage.

---

# 🖥️ Virtual Consoles

Switch to a virtual console:

```text
Ctrl + Alt + F1 ... F6
```

Return to the graphical desktop (varies by distribution):

```text
Alt + F7
```

---

# 🚪 Exit the Terminal

Close the current shell session:

```bash
exit
```

Or simply press:

```text
Ctrl + D
```

---

# 🎯 Key Takeaways

- 🐚 The **Shell** executes commands.
- 🖥️ A **Terminal Emulator** provides access to the shell.
- 💲 `$` = Regular user.
- 👑 `#` = Root user.
- ⬆️⬇️ Browse command history.
- ⬅️➡️ Edit commands quickly.
- 🛠️ Essential beginner commands:
  - `date`
  - `uptime`
  - `df`
  - `free`
  - `exit`

---

# 🧪 Try It Yourself

✅ Open the terminal.

✅ Type a fake command.

```bash
kaekfjaeifj
```

✅ Press **⬆️** to recall it.

✅ Edit it using **⬅️ ➡️**.

✅ Run:

```bash
date
uptime
df
free
```

✅ Exit the terminal:

```bash
exit
```