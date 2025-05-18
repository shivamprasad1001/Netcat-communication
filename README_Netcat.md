# 📡 Netcat (nc) Guide: Chat & File Transfer on Local Network

This document explains how to use **Netcat (`nc`)** for lightweight communication and file sharing.

---

## 🧩 Install Netcat and PV (for progress)

```bash
pkg install netcat
pkg install pv       # Optional: shows progress
````

---

## 💬 Real-Time Chat

### On Receiver:

```bash
nc -l -p 1234
```

### On Sender:

```bash
nc <receiver_ip> 1234
```

Now you can chat in real-time between devices. Press `Ctrl + C` to exit.

---

## 📁 Send a File

### Receiver:

```bash
nc -l -p 1234 > filename.ext
```

### Sender:

```bash
nc <receiver_ip> 1234 < filename.ext
```

#### With progress (optional using `pv`):

```bash
pv filename.ext | nc <receiver_ip> 1234
```

---

## 🗂️ Send a Directory

### Step 1: Compress the folder

```bash
tar -cvf folder.tar folder/
```

### Step 2: Send it

```bash
pv folder.tar | nc <receiver_ip> 1234
```

### Receiver:

```bash
nc -l -p 1234 > folder.tar
tar -xvf folder.tar
```

This will extract the folder after transfer.

---

## ⚠️ Warning

* Netcat **does not encrypt** communication or files.
* Use only on **trusted local networks** (LAN or hotspot).
* Do not expose Netcat ports to the public internet.

---

## ✅ Use Cases

* Quick file sharing between two devices
* Lightweight chat for CTFs or local scripting
* Temporary data pipelines (e.g., video, logs, backups)

---

Made for learners, hackers, and home-lab enthusiasts 🛠️💡
