# 🐧 Linux User Management and Automation (Using WSL)

## 📌 Objective

To create users in a Linux system, assign permissions, manage processes, automate tasks using a shell script, and schedule it using cron jobs.

---

## 🛠️ Environment

* Operating System: Windows 10/11
* Tool Used: Windows Subsystem for Linux (WSL - Ubuntu)

---

## 🔹 1. User Management

### ➤ Create a User

```bash
sudo useradd -m user1
```

### ➤ Set Password

```bash
sudo passwd user1
```

### ➤ Verify User

```bash
cat /etc/passwd | grep user1
```

---

## 🔹 2. Group Management

### ➤ Create Group

```bash
sudo groupadd devteam
```

### ➤ Add User to Group

```bash
sudo usermod -aG devteam user1
```

### ➤ Verify Group

```bash
groups user1
```

---

## 🔹 3. File Permissions

### ➤ Create File

```bash
touch file.txt
```

### ➤ Change Permissions

```bash
chmod 755 file.txt
```

### ➤ Change Ownership

```bash
sudo chown user1:devteam file.txt
```

### ➤ Check Permissions

```bash
ls -l
```

---

## 🔹 4. Process Management

### ➤ View Running Processes

```bash
ps aux
```

### ➤ Monitor Processes

```bash
top
```

### ➤ Kill Process

```bash
kill <PID>
```

### ➤ Force Kill

```bash
kill -9 <PID>
```

---

## 🔹 5. Shell Script Automation

### ➤ Create Script File

```bash
nano user_automation.sh
```

### ➤ Script Content

```bash
#!/bin/bash

echo "Creating users..."

sudo useradd -m userA
echo "userA:1234" | sudo chpasswd

sudo useradd -m userB
echo "userB:1234" | sudo chpasswd

echo "Creating group..."
sudo groupadd project

sudo usermod -aG project userA
sudo usermod -aG project userB

echo "Creating shared directory..."
mkdir -p ~/shared

sudo chown :project ~/shared
sudo chmod 770 ~/shared

echo "Listing users..."
cut -d: -f1 /etc/passwd

echo "Automation completed successfully!"
```

---

## 🔹 6. Make Script Executable

```bash
chmod +x user_automation.sh
```

---

## 🔹 7. Execute Script

```bash
sudo ./user_automation.sh
```

---

## 🔹 8. Cron Job Scheduling

### ➤ Install Cron

```bash
sudo apt update
sudo apt install cron
```

### ➤ Start Cron Service

```bash
sudo service cron start
```

### ➤ Open Crontab

```bash
crontab -e
```

### ➤ Add Cron Job (Runs Daily at 9 AM)

```bash
0 9 * * * /home/yourusername/user_automation.sh
```

### ➤ Verify Cron Job

```bash
crontab -l
```

---

## 📸 Screenshots to Include

1. User creation (`useradd`)
2. Group creation (`groupadd`)
3. Script file opened in editor
4. Script execution output
5. Cron job entry (`crontab -l`)
6. File permissions (`ls -l`)

---

## ⚠️ Notes

* WSL provides a Linux-like environment but is not a full Linux system.
* Some services like `cron` must be started manually.
* Use `sudo` for administrative commands.

---

## ✅ Conclusion

Successfully implemented Linux user management, file permissions, process handling, automation using shell scripting, and scheduling tasks using cron jobs in a WSL environment.
