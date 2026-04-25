# Homelab Cloud Storage with TrueNAS & Cloudflare  

**DEMO URL : https://youtu.be/WGM9GrnDn1Q?si=oIZsEgIF-t5PHynF&t=130**




**Documentation URL: https://mohanbalaji.vercel.app/Homelab_Cloud_Storage**

## 📌 Overview  
This project is a **self-hosted cloud storage solution** using **TrueNAS** on a repurposed machine, accessible securely from anywhere via **Cloudflare Tunnel**. It provides a cost-effective, secure, and scalable alternative to cloud storage services.  

![Project4-DojD5jta](https://github.com/user-attachments/assets/ecca3c51-daae-45dc-95ce-61bfda56d0a8)


## 🔧 Tech Stack  
- **TrueNAS** – For storage management  
- **Cloudflare Tunnel** – Secure remote access without exposing ports  
- **File Browser** – Web-based file management UI  
- **Custom Domain (Namecheap Students)** – Easy access via a personalized domain  
- **Intel i3 3rd Gen (Old Device)** – Optimized to run TrueNAS on bare metal  


## 🚀 Features  
✅ **Secure Remote Access** – No open ports, fully protected via Cloudflare  
✅ **Efficient Storage Management** – TrueNAS pools & datasets for structured storage  
✅ **Web-Based File Management** – Simple UI with File Browser  
✅ **Custom Domain Integration** – Seamless access using a free domain  
✅ **Low-Cost Self-Hosted Solution** – Uses repurposed hardware  

## 🛠️ Architecture Diagram

![Infrastructure diagram](https://github.com/user-attachments/assets/d5e47a6f-2615-4edc-ac51-1ea420c8f2e9)

## 🛠️ Setup Guide  

### 1️⃣ Install TrueNAS on Bare Metal  
- Download [TrueNAS](https://www.truenas.com/download-truenas-core/)  
- Flash it to a USB using **Rufus**  
- Boot from USB and install TrueNAS  

### 2️⃣ Configure Storage  
- Set up **Storage Pools & Datasets**  
- Assign storage paths  

### 3️⃣ Install File Browser  
- Run `docker run -d -p 8080:80 filebrowser/filebrowser`  
- Access at `http://your-server-ip:8080`

### 3️⃣ Install NextCloud (Similar to Google Drive)
- Run `$ docker run -d -p 8080:80 nextcloud`  

### 4️⃣ Secure Remote Access with Cloudflare Tunnel  
- Create a Cloudflare account  
- Install the **Cloudflare Tunnel** client  
- Run:  
  ```bash
  cloudflared tunnel login  
  cloudflared tunnel create my-tunnel  
  cloudflared tunnel route dns my-tunnel yourdomain.com  
  cloudflared tunnel run my-tunnel  
