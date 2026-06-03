# Day 08 – Cloud Server Setup: Docker, Nginx & Web Deployment

## Cloud Provider

AWS EC2

## Instance Details

* OS: Ubuntu Server
* Instance Type: t2.micro
* Security Group Rules:

  * SSH (22)
  * HTTP (80)

---

## SSH Connection

### Command Used

```bash
ssh -i my-key.pem ubuntu@<PUBLIC_IP>
```

### Result

Successfully connected to the EC2 instance using SSH.

---

## System Update

### Commands

```bash
sudo apt update
sudo apt upgrade -y
```

### Result

Updated package lists and installed the latest available updates.

---

## Docker Installation

### Commands

```bash
sudo apt install docker.io -y

sudo systemctl enable docker

sudo systemctl start docker

docker --version
```

### Result

Docker was installed successfully and the service started correctly.

---

## Nginx Installation

### Commands

```bash
sudo apt install nginx -y

sudo systemctl enable nginx

sudo systemctl start nginx

sudo systemctl status nginx
```

### Result

Nginx service started successfully.

---

## Web Access Verification

### Test

Opened browser and visited:

```text
http://<PUBLIC_IP>
```

### Result

The Nginx welcome page was displayed successfully.

---

## Nginx Logs

### View Logs

```bash
sudo cat /var/log/nginx/access.log
```

### Save Logs

```bash
sudo cp /var/log/nginx/access.log ~/nginx-logs.txt
```

### Result

Successfully extracted Nginx access logs and saved them to a separate file.

---

## Commands Used

```bash
sudo apt update
sudo apt upgrade -y

sudo apt install docker.io -y
sudo systemctl enable docker
sudo systemctl start docker

sudo apt install nginx -y
sudo systemctl enable nginx
sudo systemctl start nginx

docker --version
systemctl status nginx

sudo cat /var/log/nginx/access.log
```

---

## Challenges Faced

* Configuring security group rules correctly.
* Verifying port 80 was accessible.
* Ensuring Nginx service was running properly.

---

## What I Learned

* How to launch and connect to an AWS EC2 instance.
* How to install and manage Docker on Linux.
* How to install and manage Nginx.
* How to configure security groups for web access.
* How to access and save service logs for troubleshooting.

---

## Conclusion

Successfully deployed a cloud server, installed Docker and Nginx, accessed the Nginx web page from the internet, and collected logs from the server. This was my first complete cloud deployment exercise and helped me understand real-world server management.

