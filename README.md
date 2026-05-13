# AWS Web Application Deployment Project

## Overview
This project demonstrates deployment and management of web applications on AWS cloud using EC2 instances. The project includes launching Amazon Linux and Ubuntu EC2 instances, configuring Apache and Nginx web servers, deploying Spotify and Tinder clone applications, and creating AMIs for application replication.

---

## Technologies Used
- AWS EC2
- Amazon Linux
- Ubuntu
- Apache (httpd)
- Nginx
- HTML/CSS
- AWS AMI
- SSH

---

# Architecture Diagram

<img src="Architecture diagram.png" width="1000">

---

# Project Tasks

## Part 1: Launch EC2 Instances
- Launched Amazon Linux EC2 instance
- Launched Ubuntu EC2 instance
- Connected using SSH

### EC2 Instances
<img src="Screenshot 2026-04-29 143701.png" width="900">

---

## Part 2: Spotify Application Deployment
- Installed Apache Web Server
- Configured Apache on Port 81
- Deployed Spotify Clone Application

### Spotify Application Output
<img src="Screenshot 2026-04-29 141154.png" width="900">

---

## Part 3: Tinder Application Deployment
- Installed Nginx Web Server
- Configured Nginx on Port 85
- Deployed Tinder Clone Application

### Tinder Application Output
<img src="Screenshot 2026-04-29 133742.png" width="1000">

---

## Part 4: AMI Replication
- Created AMI of Spotify Server
- Copied AMI to Mumbai Region
- Launched replicated instance

### AMI Creation
<img src="Screenshot 2026-04-29 140323.png" width="900">

### Replicated Spotify Application
<img src="Screenshot 2026-04-29 141409.png" width="900">

---

# Project Summary
Successfully deployed Spotify and Tinder clone applications on AWS EC2 instances using Apache and Nginx web servers. Also implemented AMI-based replication to demonstrate scalability and application migration across AWS regions.

