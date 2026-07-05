# Local Web Server Setup with HTTPS (Nginx + WSL)

## Project Objective

The objective of this project is to configure a local web server using Nginx on Ubuntu (WSL), host a static website, and secure it using a self-signed SSL certificate for HTTPS.

---

## Tools Used

- Windows 11
- Windows Subsystem for Linux (WSL)
- Ubuntu
- Nginx
- OpenSSL
- Visual Studio Code
- Git & GitHub
- Google Chrome

---

## Project Structure

```
local-web-server-https/
│── index.html
│── style.css
│── default
│── README.md
└── screenshots/
```

---

## Setup Steps

### 1. Install WSL and Ubuntu

Install Ubuntu using Windows Subsystem for Linux (WSL).

---

### 2. Update Ubuntu

```bash
sudo apt update
sudo apt upgrade -y
```

---

### 3. Install Nginx

```bash
sudo apt install nginx -y
```

---

### 4. Start Nginx

```bash
sudo service nginx start
```

---

### 5. Create a Static Website

Created:

- index.html
- style.css

Copied them to:

```
/var/www/html
```

---

### 6. Generate a Self-Signed SSL Certificate

```bash
sudo openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout /etc/nginx/ssl/server.key -out /etc/nginx/ssl/server.crt
```

---

### 7. Configure Nginx

Edited the default Nginx configuration to enable HTTPS using the generated SSL certificate.

---

### 8. Test Nginx Configuration

```bash
sudo nginx -t
```

---

### 9. Restart Nginx

```bash
sudo service nginx restart
```

---

### 10. Verify the Website

HTTP:

```
http://localhost
```

HTTPS:

```
https://localhost
```

A browser warning appears because the certificate is self-signed. This is expected for local development.

---

## Screenshots

Add the following screenshots inside the `screenshots` folder.

- HTTP website
- HTTPS website
- Nginx configuration test (`sudo nginx -t`)
- Nginx service running

---

## What I Learned

During this project, I learned how to:

- Install Ubuntu using WSL.
- Install and configure the Nginx web server.
- Host a static website locally.
- Generate a self-signed SSL certificate using OpenSSL.
- Configure HTTPS for local development.
- Test and restart Nginx after configuration changes.
- Understand the difference between HTTP and HTTPS.
- Organize project files and document the project using a README.

---

## Author

**Monica**
