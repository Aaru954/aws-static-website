# aws-static-website
Static website deployment using HTML, CSS, JavaScript and AWS S3

# Myntra-Inspired Static Website Deployment on AWS EC2

##  Introduction

This project demonstrates the deployment of a Myntra-inspired static website on an AWS EC2 instance using Amazon Linux and Apache HTTP Server (`httpd`). It focuses on understanding cloud hosting, Linux server management, web server configuration, and static website deployment.

##   Objectives

- Launch and configure an AWS EC2 instance.
- Connect to the instance using SSH.
- Install and configure Apache HTTP Server.
- Deploy static website files on EC2.
- Access the website using the instance's public IPv4 address.

##   Architecture

**Request flow:**

User / Web Browser → Internet (HTTP Port 80) → AWS EC2 Instance → Apache HTTP Server → Static Website Files

The EC2 instance runs Amazon Linux and uses Apache HTTP Server (`httpd`) to serve the static website.
<img width="597" height="687" alt="Screenshot 2026-10-23 101009" src="https://github.com/user-attachments/assets/248a008e-920c-4533-8297-308275d9cbc9" />


##  Technologies Used

- **AWS EC2** – Virtual server for hosting the website
- **Amazon Linux** – Operating system
- **Apache HTTP Server (`httpd`)** – Web server
- **HTML, CSS, JavaScript** – Static website technologies, depending on the files used
- **SSH** – Remote server access
- **GitHub** – Project documentation and version control

##   Deployment Steps

### 1. Launch an EC2 Instance
- Launched an EC2 instance using Amazon Linux.
- Configured the key pair and security group.

### 2. Connect Using SSH
Connected to the EC2 instance using SSH.

### 3. Update Packages

```bash
sudo yum update -y
```

### 4. Install Apache

```bash
sudo yum install httpd -y
```

### 5. Start and Enable Apache

```bash
sudo systemctl start httpd
sudo systemctl enable httpd
sudo systemctl status httpd
```

### 6. Deploy Website Files

Placed the static website files in Apache's default document root:

```text
/var/www/html/
```

The main webpage can be named `index.html`.

### 7. Configure Security Group for Custom HTTP Port

-Changed the web server port from the default HTTP port 80 to 81.

-Configured Apache HTTP Server to listen on port 81.

-Updated the EC2 security group's inbound rules to allow TCP traffic on port 81.

-Allowed inbound HTTP traffic on port **81**.

### 8. Access the Website

```text
http://18.232.142.236:81//
```

Replace the placeholder with the actual public IPv4 address of the EC2 instance.

##  Screenshots

Files:
<img width="1338" height="407" alt="image" src="https://github.com/user-attachments/assets/02c57573-7a31-4978-a0cb-338bebda3498" />

EC2 Instance:
<img width="1907" height="557" alt="image" src="https://github.com/user-attachments/assets/7ca14591-bd06-4513-b5c2-2aad0e44c377" />

Terminal(Httpd Status):
<img width="1338" height="723" alt="Screenshot 2026-10-23 102637" src="https://github.com/user-attachments/assets/f187a774-32f0-4903-b38b-b5396f165722" />

Deployed Website:
<img width="1903" height="1046" alt="image" src="https://github.com/user-attachments/assets/87a12183-d386-454b-b61c-6b729735355d" />

##  Key Learnings

- AWS EC2 instance setup and management
- Linux commands and service management
- Apache installation and configuration
- Static website hosting
- HTTP traffic and security group configuration
- Cloud project documentation using GitHub

##  Security Notes

- Never upload private `.pem` files or AWS credentials to GitHub.
- Allow only the required inbound network traffic.
- HTTPS requires additional configuration and a valid TLS certificate.


##  Summary

Successfully documented the process of hosting a Myntra-inspired static website on AWS EC2 using Amazon Linux and Apache HTTP Server. This project provides practical exposure to Linux server administration, web server setup, security group configuration, and cloud-based static website hosting.
