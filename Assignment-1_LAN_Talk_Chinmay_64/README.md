# Assignment 1: LAN Talk - Local Wi-Fi Chat Application (PHP)

**Author:** Chinmay T A (Roll No: 64, S7 CSEA)  
**Subject:** Web Technology / PHP Laboratory  

A zero-dependency, multi-user LAN chat application developed with **PHP**, **HTML**, and **CSS**.

## 🚀 Overview
LAN Talk enables multiple devices (laptops, desktops, phones) connected to the same Wi-Fi router or Local Area Network to exchange messages in real time. It requires no database server (MySQL/PostgreSQL), no Node.js, and no external JavaScript libraries.

## 📁 Repository Structure
```text
├── index.php                      # User join and PHP session initialization portal
├── chat.php                       # Real-time message streaming, input form, and PRG controller
├── logout.php                     # Session termination and cleanup
├── messages.txt                   # Flat-file database storage for chat history
├── style.css                      # Chat bubble layout and mobile-responsive styling
├── Assignment_Report.md           # Complete academic lab report and technical specifications
├── Assignment-1_Report_1Page.pdf  # Single-page A4 summary report ready for submission
├── LAN_Talk_Report.pdf            # Alternative named copy of the 1-page report
└── README.md                      # Installation, LAN setup, and operational guide
```

## ✨ Highlights
- **Zero Database Setup:** Uses atomic file writes (`FILE_APPEND | LOCK_EX`) to `messages.txt`.
- **Duplicate Prevention:** Implements the Post/Redirect/Get (PRG) pattern to prevent duplicate submissions on refresh.
- **Security:** Built-in XSS defense using `htmlspecialchars()`.
- **Local Network Accessible:** Any device on the same local Wi-Fi can chat by browsing to the host's LAN IP address.

## 🛠️ Method 1: Running with XAMPP (Standard Lab Method)
1. Install [XAMPP](https://www.apachefriends.org/) (if not already installed).
2. Copy this entire project folder into your Apache document root:
   ```text
   C:\xampp\htdocs\chat-app
   ```
3. Open the **XAMPP Control Panel** and click **Start** next to **Apache**.
4. Test locally in your browser:
   ```text
   http://localhost/chat-app/
   ```

## ⚡ Method 2: Running with Built-in PHP Server (Quickest, No XAMPP Needed)
If you have PHP installed on your system or extracted in a folder:
1. Open PowerShell / Command Prompt inside this project folder:
   ```cmd
   cd c:\Users\ASUS\Downloads\anu\Chinmay_Assignment-1_LAN_Talk
   ```
2. Start the built-in server listening on all network interfaces:
   ```cmd
   php -S 0.0.0.0:8000
   ```
3. Open your browser and visit:
   ```text
   http://localhost:8000/
   ```

## 📱 Connecting From Another Laptop or Mobile Phone on the Same Wi-Fi
1. On the host computer, open PowerShell or Command Prompt and run:
   ```cmd
   ipconfig
   ```
2. Locate your **IPv4 Address** (for example: `192.168.1.15`).
3. On the second laptop or mobile phone connected to the **same Wi-Fi network**, open a web browser and go to:
   - For XAMPP:
     ```text
     http://192.168.1.15/chat-app/
     ```
   - For Built-in PHP server (port 8000):
     ```text
     http://192.168.1.15:8000/
     ```
4. Enter your name on device 1, enter a friend's name on device 2, and start chatting across devices in real time!
   *(Note: If the second device cannot load the page, allow Apache / PHP through Windows Firewall or temporarily allow port 80 / 8000).*

## 📄 Documentation & PDF Report
- [`Assignment_Report.md`](Assignment_Report.md): Full comprehensive technical report.
- [`Assignment-1_Report_1Page.pdf`](Assignment-1_Report_1Page.pdf): Single-page official academic report PDF in Chinmay T A's name (Roll No. 64).
