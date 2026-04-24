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
sudo useradd user1
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
