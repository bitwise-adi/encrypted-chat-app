# 🛡️ NOVA — Secure Chat Application  

![Python](https://img.shields.io/badge/Python-3.11-blue.svg)
![GUI](https://img.shields.io/badge/GUI-CustomTkinter-green.svg)
![Encryption](https://img.shields.io/badge/Encryption-RSA-red.svg)
![Status](https://img.shields.io/badge/Status-Stable-brightgreen.svg)

---

## 📘 Overview  
**NOVA** is a Python-based **secure chat application** that allows multiple users to communicate safely over a local network.  
It uses **socket programming** for client-server communication and **RSA encryption** to ensure that all transmitted messages are **secure and private**.  
The app also features a sleek **CustomTkinter** GUI for an enhanced user experience.

---

## ⚙️ Features  
✅ End-to-End Encryption using RSA  
✅ Multi-client support (multiple users can chat simultaneously)  
✅ Dynamic Public Key Exchange between all clients  
✅ Modern, Dark-Themed UI with **CustomTkinter**  
✅ User Login screen  
✅ Message bubbles for sent/received messages  
✅ Real-time updates for connected users  

---

## 🏗️ Tech Stack  

| Component         |       Description |
|-------------------|-------------------|
| **Language**      |       Python 3.11 |
| **GUI Framework** | CustomTkinter |
| **Networking**    | Socket Programming|
| **Encryption**    | RSA (PyCryptodome) |
| **Data Serialization** | JSON |
| **Concurrency**   | Python Threading |

---

## 🧩 File Structure  

📂 NOVA/
├── client.py # Client-side GUI and socket logic
├── server.py # Server managing all client connections
├── crypto_utils.py # RSA key generation and encryption/decryption
└── pycache/ # Compiled cache files


---

## 🚀 How to Run  

### 1️⃣ Install Requirements  
Make sure Python 3.10+ is installed, then run:  
```bash
pip install customtkinter pycryptodome
```

### 2️⃣ Start the Server
Run the server on your host machine:
```bash
python server.py
```
You should see:
```[LISTENING] Server running on 127.0.0.1:5050```

### 3️⃣ Start the Client(s)
Run the client on one or more devices (same network):
```bash
python client.py
```
Each client will:
+ Show a Login screen
+ Ask for a Username
+ Then load the **Nova** UI

### 4️⃣ Chat Securely!
+ Type your message and press Send.
+ The message is encrypted using RSA with the recipient’s public key.
+ The server only routes messages — it cannot read them.
+ The recipient decrypts messages with their private key.
---

## 💬 How It Works  

1️⃣ **RSA Key Generation**  
Each client generates its own RSA key pair when started.  
The **public key** is sent to the server, while the **private key** stays securely with the client.  

2️⃣ **Public Key Exchange**  
The server distributes all clients’ public keys to each other, ensuring that every user can encrypt messages for others.  

3️⃣ **Encrypted Messaging**  
Messages are encrypted using the recipient’s public key before being sent.  
Only the recipient can decrypt them using their private key — even the server can’t read the message.  

4️⃣ **Threaded Communication**  
Each client runs in a separate thread, allowing smooth, real-time chatting without freezing the GUI.  

---

## 🧠 Example Run  

**Server Terminal**
```pgsql
[LISTENING] Server running on 127.0.0.1:5050
[NEW CONNECTION] ('127.0.0.1', 50250) as Adi
[NEW CONNECTION] ('127.0.0.1', 50251) as Lucky
```

**Client Window**
```pgsql
Welcome Adi! Secure chat initialized.
Lucky joined the chat!
You: hi
Lucky: [Encrypted Message]

```

### 📦 Future Enhancements
+ Hybrid RSA + AES encryption for faster performance
+ File transfer between users
+ Timestamped messages and delivery receipts
+ User authentication (username + password)
+ Cloud deployment for remote access

### 👨‍💻 Developers

| Field | Info |
|---|---|
| **Project Name** | NOVA — Secure Chat Application |
| **Developers** | Aditya Raj, Lucky Sinha, Manik Salarai, Md Huzayfah Daniyal |
| **Language** | Python |
| **Version** | 1.0 |
| **GitHub** | github.com/adityaraj-codes/encrypted-chat-app |

### 🧠 Inspiration
This project was built to understand the integration of network sockets, threading, and encryption in real-world secure communication.
It demonstrates how strong cryptography and modular UI design can combine to form a simple but powerful secure messaging tool.
