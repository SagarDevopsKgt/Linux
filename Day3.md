Absolutely! Here's a **clean and readable cheat sheet** for the `ls` command with commonly used options — perfect for learning or quick reference.

---

# 📄 `ls` Command Cheat Sheet (Linux)

| Option                         | Description                                                   |
| ------------------------------ | ------------------------------------------------------------- |
| `ls`                           | List files and directories in the current directory           |
| `ls -a`                        | Show all files including hidden files (start with `.`)        |
| `ls -A`                        | Show all except `.` and `..`                                  |
| `ls -l`                        | Long listing format (permissions, size, owner, date)          |
| `ls -lh`                       | Long format with **human-readable** file sizes (e.g., KB, MB) |
| `ls -R`                        | Recursively list subdirectories                               |
| `ls -d */`                     | Show only directories                                         |
| `ls -S`                        | Sort files by **size**, largest first                         |
| `ls -t`                        | Sort by **modification time**, newest first                   |
| `ls -ltr`                      | Long listing, sorted by time, **oldest first**                |
| `ls -r`                        | Reverse the sorting order                                     |
| `ls -i`                        | Display **inode** numbers                                     |
| `ls -F`                        | Add indicator (`/` for dirs, `*` for executables)             |
| `ls -1`                        | Display **one entry per line**                                |
| `ls -n`                        | Like `-l` but show **numeric IDs** for owner/group            |
| `ls -g`                        | Like `-l` but **omit owner** info                             |
| `ls -G`                        | **Hide group info** in long listing                           |
| `ls -X`                        | Sort files by extension                                       |
| `ls --color=auto`              | Use colors to distinguish file types                          |
| `ls -v`                        | Natural sort of version numbers                               |
| `ls -p`                        | Add `/` after directory names                                 |
| `ls -m`                        | Stream output, comma-separated                                |
| `ls --group-directories-first` | List directories before files                                 |

---

### 🔁 Common Combos

| Command              | Meaning                                            |
| -------------------- | -------------------------------------------------- |
| `ls -lah`            | Long listing with all files & human-readable sizes |
| `ls -ltr`            | Long listing, sort by time, oldest first           |
| `ls -lS`             | Long listing sorted by size                        |
| `ls -d */`           | Show only subdirectories                           |
| `alias ll='ls -lah'` | Custom shortcut for detailed listing               |

---


Absolutely! Here's a practical breakdown of:

---

## 📁 `cd` (Change Directory) — Common Options & Variants

### ✅ Basic Syntax:

```bash
cd [directory_path]
```

---

### 🔹 **Common Use Cases of `cd`**

| Command           | Description                                        |
| ----------------- | -------------------------------------------------- |
| `cd`              | Go to **home directory** (`$HOME`)                 |
| `cd ~`            | Same as above — home directory                     |
| `cd /`            | Go to root directory                               |
| `cd ..`           | Go **one level up** (parent directory)             |
| `cd ../..`        | Go **two levels up**                               |
| `cd -`            | Switch to the **previous directory** (very handy!) |
| `cd /path/to/dir` | Go to a **specific absolute path**                 |
| `cd ~/Downloads`  | Go to a directory under the home folder            |
| `cd ./folder`     | Use a **relative path** (inside current directory) |

---

### 🔹 **Using Variables with `cd`**

| Example      | Description                                       |
| ------------ | ------------------------------------------------- |
| `cd $HOME`   | Go to home directory                              |
| `cd $OLDPWD` | Go to previous directory                          |
| `cd $PWD`    | Stay in the same directory (returns current path) |

--Useful Directory Navigation Aliases

| Alias                  | Command                         |
| ---------------------- | ------------------------------- |
| `alias ..='cd ..'`     | Shortcut for going up one level |
| `alias ...='cd ../..'` | Go up two levels                |
| `alias c='clear'`      | Clear screen quickly            |
| `alias home='cd ~'`    | Go to home directory quickly    |



Would you like this formatted as a downloadable PDF or printable table too?
