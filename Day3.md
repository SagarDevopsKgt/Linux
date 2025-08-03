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

Would you like this formatted as a downloadable PDF or printable table too?
