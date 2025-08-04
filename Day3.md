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





MKDIR stands for **"make directory"**,
used to create one or more new directories.

---

### ✅ Basic Syntax

```bash
mkdir [OPTIONS] directory_name
```

---

### 🔧 Common `mkdir` Options

| Option      | Description                                                                 |
| ----------- | --------------------------------------------------------------------------- |
| `-p`        | Create parent directories as needed. Prevents errors if dirs already exist. |
| `-v`        | Verbose mode – shows what is being created.                                 |
| `-m`        | Set permissions (mode) while creating the directory.                        |
| `--help`    | Show help for the command.                                                  |
| `--version` | Show version of `mkdir`.                                                    |

---

### 🧪 Examples

```bash
mkdir newfolder
```

> Create `newfolder` in the current directory.

```bash
mkdir -p /var/www/project/logs
```

> Create the full path structure, including any missing parent folders.

```bash
mkdir -v folder1 folder2 folder3
```

> Create multiple directories and show confirmation.

```bash
mkdir -m 755 mydir
```

> Create a directory with specific permissions (`rwxr-xr-x`).

---

## 🧠 Expert-Level Interview Questions on `mkdir`

---

### 🔹 **1. What's the difference between `mkdir dir` and `mkdir -p dir`?**

**Answer:**

* `mkdir dir` fails if the parent directory doesn't exist.
* `mkdir -p dir` creates all necessary parent directories and **does not throw an error** if the directory already exists.

---

### 🔹 **2. How do you create a directory structure with multiple levels in one command?**

```bash
mkdir -p /opt/app/{logs,tmp,config}
```

**Answer:**

* Creates `/opt/app/logs`, `/opt/app/tmp`, and `/opt/app/config` using brace expansion.

---

### 🔹 **3. How do you set directory permissions during creation?**

```bash
mkdir -m 700 /secure/data
```

**Answer:**

* `-m` sets the mode/permissions (in this case: `rwx------`).

---

### 🔹 **4. How do you check if a directory exists before creating it in a shell script?**

```bash
[ ! -d "/mydir" ] && mkdir /mydir
```

**Answer:**

* Uses test `-d` to check if the directory exists. If it doesn’t, `mkdir` creates it.

---

### 🔹 **5. What happens if you run `mkdir existing_dir` without `-p`?**

**Answer:**

* It throws an error:

  ```bash
  mkdir: cannot create directory 'existing_dir': File exists
  ```

---

### 🔹 **6. How does `mkdir -p` behave differently in a pipeline or automation tool like Jenkins?**

**Answer:**

* It prevents scripts from failing due to "directory already exists" errors — making it **idempotent** and safer in CI/CD workflows.

---

### 🔹 **7. Can you create multiple nested folders with one command?**

```bash
mkdir -p /data/{2023,2024}/{Q1,Q2,Q3,Q4}
```

**Answer:**

* Yes. This uses **brace expansion** to create:

  * `/data/2023/Q1`, `/data/2023/Q2`, ...
  * `/data/2024/Q1`, `/data/2024/Q2`, etc.

---

