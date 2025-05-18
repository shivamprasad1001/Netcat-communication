

# Netcat Message Communication using Port 12345

This guide explains how to use the `nc` (Netcat) command-line tool to send and receive messages over a network using **port 12345**.

---

## 📦 Requirements

- Netcat (`nc`) installed on both sender and receiver machines
- Open port `12345` (ensure no firewall is blocking it)

---

## 🔧 Usage

### 🖥️ Step 1: Start the Receiver (Listening Mode)

On one machine (or terminal), run:

```bash
nc -l 12345
````

This opens port `12345` and waits for an incoming connection.

---

### 💻 Step 2: Start the Sender (Connecting Mode)

On another machine (or terminal), connect to the receiver:

```bash
nc <receiver_ip_address> 12345
```

For local testing on the same machine, use:

```bash
nc 127.0.0.1 12345
```

---

### ✉️ Communication

Once connected:

* Type messages on either side and they will appear on the other side.
* To end the session, press `Ctrl+C` or close the terminal.

---

## 🧪 Example

**Terminal 1 (Receiver):**

```bash
nc -l 12345
```

**Terminal 2 (Sender):**

```bash
nc 127.0.0.1 12345
```

Start typing messages in either terminal to communicate.

---

## 🛠️ Tips

* Use `-v` for verbose output:

  ```bash
  nc -lv 12345
  ```

* Ensure firewalls (like UFW or iptables) allow traffic on port 12345.

---

## 📚 References

* [Netcat Wikipedia](https://en.wikipedia.org/wiki/Netcat)
* `man nc`

---

## 🔒 Disclaimer

Use Netcat responsibly. Do not use it for unauthorized access or communication.

