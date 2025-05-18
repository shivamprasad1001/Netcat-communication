# 🔐 SSH Guide: Secure Remote Access & File Transfer

This document outlines how to use **SSH (Secure Shell)** to securely connect to remote systems and transfer files.

---

## 🧩 Install OpenSSH (on Termux or Debian-based systems)

```bash
pkg install openssh   # Termux
sudo apt install openssh-server  # Kali or Debian
```

---

## 🚀 Start SSH Server

```bash
sshd
```

To make it persistent (Linux only):
```bash
sudo systemctl enable ssh
sudo systemctl start ssh
```

---

## 🛡️ Set or Change SSH Password

```bash
passwd
```

---

## 🌐 Find IP Address

```bash
ip a
```

---

## 🔗 SSH Login from Another Device

```bash
ssh username@remote_ip
```

**Example:**

```bash
ssh kali@192.168.1.10
```

---

## 📥 Download File via SSH

```bash
scp username@remote_ip:/path/to/file /local/destination
```

Example:

```bash
scp kali@192.168.1.10:/home/kali/file.txt ~/Downloads/
```

---

## 📤 Upload File via SSH

```bash
scp file.txt username@remote_ip:/remote/destination/
```

---

## ✅ Notes

- SSH encrypts all data.
- Useful for remote access and secure file transfer.