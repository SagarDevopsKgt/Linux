# Linux 
Shell scripting are fundamental skills for DevOps engineers. Here’s a comprehensive guide to **essential Linux commands** and **shell scripting basics**, with examples and real-world scenarios.

---

## **Linux Commands for DevOps Engineers**

### **1. File & Directory Management**
| Command         | Use Case / Example                | Scenario                                    |
|-----------------|-----------------------------------|---------------------------------------------|
| `ls`            | List files and directories        | Check contents of `/var/log`                |
| `cd`            | Change directory                  | `cd /etc` to edit config files              |
| `pwd`           | Print current directory           | Confirm working directory in scripts        |
| `mkdir`         | Create new directory              | `mkdir /opt/app` for deployments            |
| `rm`            | Remove files/directories          | `rm -rf /tmp/*` to clean temp files         |
| `cp`            | Copy files/directories            | `cp config.yaml config.bak` for backup      |
| `mv`            | Move/rename files                 | `mv app.log app.log.old` for log rotation   |
| `touch`         | Create empty file                 | `touch readiness.txt` for readiness probe   |
| `find`          | Search for files                  | `find /var/log -name "*.log"` for logs      |

### **2. File Content Manipulation**
| Command         | Use Case / Example                | Scenario                                    |
|-----------------|-----------------------------------|---------------------------------------------|
| `cat`           | Display file content              | `cat /etc/passwd`                           |
| `head`          | First lines of file               | `head -n 10 app.log`                        |
| `tail`          | Last lines of file                | `tail -f app.log` to monitor logs           |
| `less`/`more`   | Scroll through file               | `less /var/log/syslog`                      |
| `grep`          | Search text in files              | `grep "ERROR" app.log`                      |
| `awk`           | Text processing                   | `awk '{print $1}' users.txt`                |
| `sed`           | Stream editor                     | `sed 's/dev/prod/g' config.txt`             |
| `sort`          | Sort lines                        | `sort users.txt`                            |
| `uniq`          | Unique lines                      | `uniq errors.txt`                           |

### **3. Permissions & Ownership**
| Command         | Use Case / Example                | Scenario                                    |
|-----------------|-----------------------------------|---------------------------------------------|
| `chmod`         | Change file permissions           | `chmod 755 deploy.sh`                       |
| `chown`         | Change file ownership             | `chown root:root config.yaml`               |

### **4. System Monitoring & Process Management**
| Command         | Use Case / Example                | Scenario                                    |
|-----------------|-----------------------------------|---------------------------------------------|
| `top`           | Real-time system monitor          | View CPU/RAM usage                          |
| `htop`          | Enhanced system monitor           | Easier process tracking                     |
| `ps`            | List running processes            | `ps aux | grep nginx`                       |
| `kill`          | Terminate process                 | `kill -9 1234` (process ID)                 |
| `free`          | Memory usage                      | `free -m`                                   |
| `df`            | Disk space                        | `df -h`                                     |
| `du`            | Disk usage                        | `du -sh /var/log`                           |
| `uptime`        | System uptime                     | Monitor server running time                 |

### **5. Networking**
| Command         | Use Case / Example                | Scenario                                    |
|-----------------|-----------------------------------|---------------------------------------------|
| `ping`          | Check connectivity                | `ping 8.8.8.8`                              |
| `curl`          | API/URL requests                  | `curl http://localhost:8080/health`         |
| `wget`          | Download files                    | `wget http://site.com/file.tar.gz`          |
| `netstat`       | Network status                    | `netstat -tulnp`                            |
| `ss`            | Socket statistics                 | `ss -tulwn`                                 |
| `scp`           | Secure copy files                 | `scp file user@host:/path/`                 |
| `ssh`           | Secure shell                      | `ssh user@host`                             |

### **6. Package Management**
| Command         | Use Case / Example                | Scenario                                    |
|-----------------|-----------------------------------|---------------------------------------------|
| `apt`, `yum`    | Install packages                  | `apt install nginx`                         |
| `dpkg`, `rpm`   | Manage packages                   | `dpkg -i package.deb`                       |

### **7. Miscellaneous**
| Command         | Use Case / Example                | Scenario                                    |
|-----------------|-----------------------------------|---------------------------------------------|
| `echo`          | Print text                        | `echo "Deploy Complete"`                    |
| `date`          | Show current date/time            | `date`                                      |
| `history`       | View command history              | `history | grep docker`                     |
| `env`           | Show environment variables        | `env`                                       |
| `export`        | Set environment variable          | `export PATH=$PATH:/opt/bin`                |

---

## **Shell Scripting Basics**

### **1. Script Structure**
```bash name=hello_world.sh
#!/bin/bash
echo "Hello, DevOps World!"
```

### **2. Variables**
```bash name=variables.sh
#!/bin/bash
name="DevOps"
echo "Welcome to $name"
```

### **3. Conditional Statements**
```bash name=if_example.sh
#!/bin/bash
if [ -f "/etc/passwd" ]; then
  echo "File exists"
else
  echo "File not found"
fi
```

### **4. Loops**
#### **For Loop**
```bash name=for_loop.sh
#!/bin/bash
for file in *.log; do
  echo "Processing $file"
done
```
#### **While Loop**
```bash name=while_loop.sh
#!/bin/bash
count=1
while [ $count -le 5 ]; do
  echo "Count: $count"
  ((count++))
done
```

### **5. Functions**
```bash name=function_example.sh
#!/bin/bash
greet() {
  echo "Hello, $1"
}
greet "DevOps Engineer"
```

### **6. Reading User Input**
```bash name=input.sh
#!/bin/bash
echo "Enter your name:"
read username
echo "Hello, $username"
```

### **7. Command-Line Arguments**
```bash name=arguments.sh
#!/bin/bash
echo "Script name: $0"
echo "First argument: $1"
echo "Second argument: $2"
```

### **8. Exit Status & Error Handling**
```bash name=exit_status.sh
#!/bin/bash
ls /notexist
if [ $? -ne 0 ]; then
  echo "Command failed!"
  exit 1
fi
```

### **9. Real-time DevOps Scenarios**

#### **a. Check if Service is Running**
```bash name=service_check.sh
#!/bin/bash
service="nginx"
if systemctl is-active --quiet $service; then
  echo "$service is running"
else
  echo "$service is not running"
fi
```

#### **b. Automated Backup Script**
```bash name=backup.sh
#!/bin/bash
src="/var/www/html"
dest="/backup/html_$(date +%F).tar.gz"
tar -czf $dest $src
echo "Backup done: $dest"
```

#### **c. Disk Space Monitoring**
```bash name=disk_check.sh
#!/bin/bash
threshold=80
usage=$(df / | tail -1 | awk '{print $5}' | sed 's/%//')
if [ $usage -gt $threshold ]; then
  echo "Disk usage is above $threshold%!"
fi
```

#### **d. Deploy Application**
```bash name=deploy.sh
#!/bin/bash
git pull origin main
./build.sh
systemctl restart app.service
echo "Deployment complete."
```

---

## **How to Practice**
- Set up a Linux VM or use WSL (Windows Subsystem for Linux) if on Windows.
- Try writing shell scripts for common admin tasks: backups, monitoring, deployments.
- Use commands in real scenarios (log analysis, process management, networking checks).

---

**Let me know if you want deep dive into any command, scripting concept, or real-world automation script!**
