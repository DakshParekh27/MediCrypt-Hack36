<h1 align="center">Hack36 9.0 Template Readme</h1>
<p align="center">
</p>

[![Built at Hack36](https://raw.githubusercontent.com/nihal2908/Hack-36-Readme-Template/main/BUILT-AT-Hack36-9-Secure.png)](https://raw.githubusercontent.com/nihal2908/Hack-36-Readme-Template/main/BUILT-AT-Hack36-9-Secure.png)


## Introduction:
**MediCrypt** is a secure, end-to-end encrypted medical records management system that enables patients and doctors to exchange medical reports safely using **Hybrid Encryption (AES + RSA)**.  
All encryption and decryption occur **client-side**, ensuring that even the server or database never sees the unencrypted data.  

### 🩺 Workflow Summary:
1. **Doctor Key Setup:**  
   - Doctors generate RSA key pairs in the browser.  
   - Private key is encrypted with a password (AES-GCM).  
   - Only the encrypted private key and public key are stored in the database.  

2. **Patient Report Upload:**  
   - Patient encrypts the report using AES-256-GCM.  
   - The AES key is encrypted using the doctor’s public key (RSA-OAEP).  
   - Encrypted file and metadata are uploaded to the backend (stored in Cloudinary + MongoDB).  

3. **Doctor Decryption:**  
   - Doctor decrypts private key using password (AES).  
   - Decrypts AES key using private RSA key.  
   - Finally decrypts the medical report locally in the browser.  

🛡️ **Result:** Full end-to-end privacy — only patient and doctor can access the report.

---

## Demo Video Link:
<a href="#">Coming Soon</a>
  
## Presentation Link:
<a href="#"> PPT link here </a>
  
---

## Table of Contents:
- [Introduction](#introduction)
- [System Workflow](#workflow-summary)
- [Tech Stack](#technology-stack)
- [Encryption Flow](#encryption-flow)
- [Contributors](#contributors)

---

## Technology Stack:
### 🧠 Backend:
- Node.js  
- Express.js  
- MongoDB  
- Cloudinary  

### 💻 Frontend:
- React.js (Vite)  
- Web Crypto API (for client-side RSA + AES encryption)  
- Axios  

### 🔐 Security:
- AES-256-GCM  
- RSA-4096-OAEP  
- PBKDF2 key derivation  

---

## 🔐 Encryption Flow Diagram (Summary)
**Hybrid Encryption Steps:**<br>
Patient Device
├── Generates AES key → Encrypts report (AES-GCM)<br>
├── Encrypts AES key with Doctor’s Public RSA key<br>
├── Uploads encrypted report + encrypted AES key → Server<br>

Server (Zero Knowledge)<br>
├── Stores encrypted data (no decryption possible)<br>

Doctor Device<br>
├── Retrieves encrypted report + encrypted AES key<br>
├── Decrypts private key with password (AES)<br>
├── Uses private RSA key to decrypt AES key<br>
├── Decrypts and downloads report locally<br>

## Contributors:
Team Name : DEVLOK

- [Moksh Jain](https://github.com/Moksh-Jain-2212)
- [Parekh Daksh](https://github.com/DakshParekh27)
- [Vankish Gupta](https://github.com/vankishgupta)
- [Mudit Agarwal](https://github.com/Mudit1919)

### Made at:
[![Built at Hack36](https://raw.githubusercontent.com/nihal2908/Hack-36-Readme-Template/main/BUILT-AT-Hack36-9-Secure.png)](https://raw.githubusercontent.com/nihal2908/Hack-36-Readme-Template/main/BUILT-AT-Hack36-9-Secure.png)
