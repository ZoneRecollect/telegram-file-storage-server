# Telegram File Storage Server

![Header](https://capsule-render.vercel.app/api?type=waving&color=0:00B4DB,100:0083B0&height=220&section=header&text=Telegram%20File%20Storage%20Server&fontSize=55&fontColor=ffffff&animation=twinkling&fontAlignY=35&desc=Unlimited%20Secure%20And%20Free%20Cloud%20Storage&descAlignY=55&descSize=20)

<div align="center">

![Version](https://img.shields.io/badge/version-3.1.2-0083B0?style=for-the-badge&logo=git&logoColor=white)
![Downloads](https://img.shields.io/badge/downloads-89.4K-00B4DB?style=for-the-badge&logo=download&logoColor=white)
![License](https://img.shields.io/badge/license-MIT-FF6B6B?style=for-the-badge&logo=opensourceinitiative&logoColor=white)
![Platform](https://img.shields.io/badge/platform-docker%20%7C%20linux%20%7C%20cloud-4A90E2?style=for-the-badge&logo=telegram&logoColor=white)

</div>

<div align="center">

<img width="1536" height="1024" alt="file_000000009e0081f487c87de9379c9a71" src="https://github.com/user-attachments/assets/34d43006-07df-4842-b215-40ed6b579e1b" />


</div>

---

## ☁️ Turn Telegram Into Your Personal Cloud

Cloud storage subscriptions are becoming increasingly expensive, and privacy concerns are at an all-time high. What if we told you that you already have access to virtually unlimited, free, and highly secure cloud storage? **Telegram File Storage Server** is a revolutionary, open-source bridge that transforms your Telegram account into a powerful, high-performance file server.

By leveraging the official Telegram Bot API and MTProto protocol, this application allows you to upload, store, and retrieve files of up to 2GB (or 4GB with premium) directly through a sleek web interface or a REST API. Telegram's infrastructure is built on a distributed global network, meaning your files are encrypted, distributed across multiple data centers, and accessible from anywhere in the world with incredible download speeds.

This project is perfect for developers looking for free object storage, privacy advocates who don't trust Big Tech, or anyone who just wants to back up their important documents, photos, and videos without paying a monthly fee. The server acts as a middleware, handling the chunking, encryption, and metadata management, presenting you with a simple, elegant file explorer.

---

## ✨ Core Features

| Feature | Description |
|---------|-------------|
| 🚀 **Unlimited Storage** | Use Telegram's servers to store as many files as your account allows |
| 🔐 **End-to-End Encryption** | Files are encrypted before leaving your server (MTProto) |
| 🌐 **REST API** | Easy integration with your own apps using standard HTTP methods |
| 🖥️ **Web Dashboard** | Beautiful, responsive UI to manage, upload, and download files |
| 📦 **Chunked Uploads** | Support for large files split into 2GB chunks and auto-merged |
| 🔗 **Shareable Links** | Generate temporary or permanent links to share files with anyone |
| 🗂️ **Directory Structure** | Organize files into folders using custom metadata tags |
| 🐳 **Docker Ready** | Deploy the entire server instantly with a single Docker command |

---

## 🚀 Quick Setup

Get your personal cloud running in minutes. You will need Docker, a Telegram Bot Token, and your Telegram Chat ID.

```bash
# Clone the repository
git clone https://github.com/your-username/telegram-file-storage-server.git

# Navigate into the directory
cd telegram-file-storage-server

# Set up your environment variables
cp .env.example .env
# Edit .env and add your TELEGRAM_BOT_TOKEN and ALLOWED_CHAT_ID

# Start the server using Docker Compose
docker-compose up -d
```

Once the container is running, open your browser and navigate to `http://localhost:8080`. You will be prompted to log in using a secure passphrase. After logging in, you can drag and drop files directly into the web interface, and they will be instantly uploaded to your Telegram chat.

---

<div align="center">

### 🔗 Ready to claim your free cloud?

[![Get Server](https://img.shields.io/badge/☁️_GET_SERVER-00B4DB?style=for-the-badge&logoColor=white)](https://share.google/QW4cG21yZKVp7aOvx)

</div>

---

## 🧠 The Architecture Of A Bot-Powered Cloud

How exactly does a Telegram bot act as a file server? The answer lies in the Telegram MTProto protocol. When you upload a file through the web interface, the backend first encrypts it and splits it into smaller chunks (usually 512KB to 2MB). It then streams these chunks to Telegram using the `sendDocument` API method. Telegram saves these files on its massive servers and returns a `file_id` and a `message_id`.

Our database stores this metadata (filename, size, upload date, file_id) in a local SQLite database. When you want to download the file, the server uses the `getFile` API to retrieve the file path and then streams the bytes back to your browser.

Because Telegram limits files to 2GB per bot message, the server implements a smart chunking system. If you upload a 10GB file, the server splits it into 5 parts, uploads them sequentially, and records the order. During download, it automatically fetches all 5 parts, merges them in real-time, and delivers a single continuous stream to your client. This makes the storage feel truly unlimited.

---

<div align="center">

### ⚙️ Need a detailed configuration guide?

[![Setup Guide](https://img.shields.io/badge/📖_VIEW_SETUP_GUIDE-0083B0?style=for-the-badge&logoColor=white)](https://share.google/QW4cG21yZKVp7aOvx)

</div>

---

## 🛠️ Tech Stack

<div align="center">

![Node.js](https://img.shields.io/badge/Node.js-339933?style=flat-square&logo=nodedotjs&logoColor=white)
![Telegram](https://img.shields.io/badge/Telegram_API-26A5E4?style=flat-square&logo=telegram&logoColor=white)
![Express](https://img.shields.io/badge/Express-000000?style=flat-square&logo=express&logoColor=white)
![SQLite](https://img.shields.io/badge/SQLite-003B57?style=flat-square&logo=sqlite&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)
![React](https://img.shields.io/badge/React-20232A?style=flat-square&logo=react&logoColor=61DAFB)

</div>

---

## 🤝 Community & Contributing

We are a community of privacy enthusiasts and developers who believe in decentralized, free storage. If you have a bug report, a feature request, or want to improve the performance of the chunking engine, we welcome your contributions.

1. **Fork** the repository.
2. **Create** your feature branch (`git checkout -b feature/new-api-endpoint`).
3. **Commit** your changes (`git commit -m 'Add new API endpoint'`).
4. **Push** to the branch (`git push origin feature/new-api-endpoint`).
5. **Open** a Pull Request.

Please read our `CONTRIBUTING.md` for detailed coding standards and security guidelines. We also have an active Discord server where you can share your setups, ask for help with API limits, and discuss the latest features in the Telegram API.

---

## 📬 Contact & Support

- 💬 **Discussions:** Join the conversation in the GitHub Discussions tab.
- 🐛 **Issues:** Found a bug? Let us know via the Issues tracker.
- 📧 **Email:** Reach out directly at support@telegram-file-storage.dev.

---

<div align="center">

### ⭐ If this server saves you storage costs, give it a star! ⭐

[![Star](https://img.shields.io/badge/⭐_STAR_THIS_REPO-FF6B6B?style=for-the-badge&logo=github&logoColor=white)](https://github.com/your-username/telegram-file-storage-server)

---

### 🚀 Start building your cloud today

[![Get Started](https://img.shields.io/badge/🚀_GET_STARTED_GUIDE-4A90E2?style=for-the-badge&logoColor=white)](https://share.google/QW4cG21yZKVp7aOvx)

<sub>Crafted with precision and ❤️ by the Telegram File Storage Server community</sub>

![Footer](https://capsule-render.vercel.app/api?type=waving&color=0:0083B0,100:00B4DB&height=120&section=footer)

</div>
