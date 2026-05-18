
# 🚀 Python  Application Deployment on AWS EC2 using Apache & Gunicorn

# **Project Introduction**

**Python-App Deployment** is a web-based application developed using Python, where the application runs using a built-in server and can also be deployed using Gunicorn for production-level performance.

Project objective:

Launching and configuring AWS EC2 instances
Hosting Python web applications on Linux servers
Managing Python virtual environments
Installing and configuring Apache HTTP Server
Running Flask applications using Gunicorn WSGI server
Configuring security groups and networking
Using GitHub for source code management

# **1. Architecture Diagram**

![](./img/Python_architecture.png)

```
⚙️ Technologies Used
🐍 Python 3
🌐 Flask
🔫 Gunicorn
☁️ AWS EC2
🔧 Apache HTTP Server
🐧 Amazon Linux
🗂️ Git & GitHub
```
```
📂 Project Structure
pythonapp/
│
├── app.py
├── requirements.txt
```
# 2. Instance Setup

## 2.1 Launch Instance

![](./img/Screenshot%202026-05-18%20181047.png)

## 2.2 Names & OS

Name : `Python`

OS : `Amazon Linux`

![](./img/Screenshot%202026-05-18%20191210.png)

## 2.3 AMI & Instance Type

AMI : `Default`

Architecture : `Default`

Instance Type : `t3.micro` (2CPU & 1GB Memory)

![](./img/Screenshot%202026-05-18%20191344.png)

## 2.4 Key & Network

Key : `Pratik-Virginia-Key` (Exiting One)

Security Group : `Launch-Wizard-2` (Exiting One)

![](./img/Screenshot%202026-05-18%20191636.png)

## 2.5 Start Instance

![](./img/Screenshot%202026-05-18%20191808.png)

## 2.6 Connect

![](./img/Screenshot%202026-05-18%20191808.png)

## 2.7 Copy SSH Client Link

![](./img/Screenshot%202026-05-18%20192038.png)

# 3. Installing Packages



## 3.1 Connect Instance With Public IP

```jsx
ssh -i Pratik-Virginia-Key.pem ec2-user@54.161.38.170
```

## 3.2 Update Packages

```jsx
sudo yum update
```

## 3.3 Install Git

```jsx
sudo yum install git -y
```
![](./img/Screenshot%202026-05-18%20182522.png)

## 3.4 Git Clone Repo

```jsx
git clone https://github.com/iamtruptimane/pythonapp
```

## 3.5 Install Python

```jsx
sudo yum install python3 -y
```
![](./img/Screenshot%202026-05-18%20183130.png)

## 3.6 Install PIP

```jsx
sudo yum install python3-pip -y
```


## 3.7 View Git, Python & PIP Version

```jsx
git --versio
python --version
pip --version
```
![](./img/Screenshot%202026-05-18%20192958.png)

# 4. Running Python App

## 4.1 Go To Directory Which Create Via Git Clone

```jsx
cd / pythonapp;
```

![](./img/Screenshot%202026-05-18%20192622.png)

## 4.2 Create Virtual Environment (venv) Inside Project Folder

```jsx
sudo python3 -m venv myenv
```
![](./img/Screenshot%202026-05-18%20183927.png)

## 4.3 Bash Activated venv

```jsx
sudo bash myenv/bin/activate
```


## 4.4 Install Requirements Inside Project Folder

```jsx
sudo pip install -r requirements.txt
```

## 4.5 To Run App (FrontGround)

```jsx
python3 app.py

If Press Ctrl + C → App Stops
```

## 4.6 To Run App In BackGround

```jsx
gunicorn --bind 0.0.0.0:5000 app:app --daemon
```

# 5. **Access** On Browser

## 5.1 To Add Port Number 5000

### 5.1.1 Go To Security Groups

![](./img/Screenshot%202026-05-18%20193228.png)

### 5.1.2 Edit Inbound Rules

![](./img/Screenshot%202026-05-18%20185914.png)

### 5.1.3 Add Rule → Type : Custom TCP → Port Range : 3000 → Source : Anywhere-IPv4 → Save Rules

![](./img/Screenshot%202026-05-18%20193350.png)

## 5.2 Hit It On Browser And Put File Name

`public ip:5000`

![](./img/Screenshot%202026-05-18%20185625.png)

```
# 🔥 Key Learnings

- AWS EC2 setup
- Linux server management
- Python virtual environments
- Flask application deployment
- Gunicorn configuration
- Apache server basics
- GitHub integration
```
# Summary
It Enables Users To Access The Application Through A Public IP On Port 5000, Demonstrating Basic Cloud Deployment And Application Hosting In A Structured Environment.