
### 📄 SSH & Netcat Guide (Chat + File Transfer)


# 🔐 SSH & 📡 Netcat (nc) Guide for Remote Communication and File Transfer

This guide covers:
- SSH login & file transfers
- Terminal chat with Netcat
- File & directory sharing with/without progress

Tested on **Kali Linux**, **Termux**, and other Linux environments on the same local network.

---

## 🧩 Termux Setup (Optional)

```bash
pkg update && pkg upgrade
pkg install openssh
pkg install netcat
pkg install pv       # For progress bar in file transfers
````



## 🔑 SSH Commands

### ✅ Start SSH Server on Remote (Kali / Termux)

```bash
sshd
```

### ✅ Set or Change SSH Password

```bash
passwd
```

### ✅ Find IP Address

```bash
ip a
```

Look for something like: `inet 192.168.x.x`

### ✅ SSH Into Remote System

```bash
ssh username@remote_ip
```

**Example:**

```bash
ssh kali@192.168.1.10
```

---

## 📥 Download File from Remote via SSH

```bash
scp username@remote_ip:/path/to/file /local/destination
```

**Example:**

```bash
scp kali@192.168.1.10:/home/kali/report.pdf ~/Downloads/
```

---

## 📤 Upload File to Remote via SSH

```bash
scp file.txt username@remote_ip:/remote/destination/path
```

**Example:**

```bash
scp notes.txt kali@192.168.1.10:/home/kali/
```

---

## 📡 Netcat Chat

### ✅ On Receiver (Listener):

```bash
nc -l -p 1234
```

### ✅ On Sender (Client):

```bash
nc <receiver_ip> 1234
```

Now type and chat in real-time.

---

## 📁 File Transfer with Netcat

### ✅ Receiver (Save file):

```bash
nc -l -p 1234 > filename.ext
```

### ✅ Sender (Send file):

```bash
nc <receiver_ip> 1234 < filename.ext
```

### 🔄 With Progress (on Sender):

```bash
pv filename.ext | nc <receiver_ip> 1234
```

---

## 🗃️ Directory Transfer via Netcat

### ✅ Step 1: Compress Folder on Sender

```bash
tar -cvf folder.tar folder/
```

### ✅ Step 2: Send

```bash
pv folder.tar | nc <receiver_ip> 1234
```

### ✅ Receiver (Extract)

```bash
nc -l -p 1234 > folder.tar
tar -xvf folder.tar
```

---

## ⚠️ Notes & Tips

* Use `ip a` to check IP.
* Make sure both devices are on the same Wi-Fi or LAN.
* Use high ports (e.g., 1234 or 4444) to avoid permission issues.
* SSH is encrypted, but Netcat is **not** — don't use `nc` on public networks.

---

Happy Hacking! 🐙💻
