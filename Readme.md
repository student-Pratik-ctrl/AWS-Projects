# AWS EBS Snapshot Cross Region Migration Project

## 📌 Project Overview

This project demonstrates how to:

- Launch EC2 instances in different AWS regions
- Create and attach EBS volumes
- Create partitions and filesystem
- Mount EBS volume
- Store files inside EBS
- Create snapshots
- Copy snapshots between regions
- Restore data in another region

---

# 🏗️ Architecture Diagram

![](./Architecture_ebs.png)

---

# EBS SNAPSHOTS

---

# I. Launch Instance In N. Virginia Region

## 1. Launch EC2 Instance

![](./1.png)

---

## 2. Create & Attach Volume

### Create Volume

![](./Screenshot%202026-05-06%20201208.png)

### Attach Volume

![](./Screenshot%202026-05-06%20201335.png)

---

## 3. See The List Of All Block Storage Devices

### Command

```bash
lsblk
sudo blkid
```

![](./Screenshot%202026-05-06%20190230.png)

---

## 4. Make Disk Partitions and Create Filesystem (XFS)

### Create Partition

```bash
sudo fdisk /dev/nvme1n1
```

### Inside fdisk

```bash
n
p
1
Enter
+1G
w
```

![](./Screenshot%202026-05-06%20190638.png)

---

### Create Filesystem

```bash
sudo mkfs.xfs /dev/nvme1n1p1
```

![](./Screenshot%202026-05-06%20190449.png)

---

## 5. Edit The System Filesystem Table

### Command

```bash
sudo vim /etc/fstab
```

### Add Entry

```bash
/dev/nvme1n1p1 /home/ec2-user/project xfs defaults 0 0
```

![](./Screenshot%202026-05-06%20191445.png)

---

## 6. Mount EBS And Create Folder

### Commands

```bash
mkdir project
sudo mount /home/ec2-user/project
```

![](./Screenshot%202026-05-06%20192012.png)

---

## 7. Create Files Inside Project Folder

### Commands

```bash
cd project
touch tcs{1..100}.txt
ls
```

![](./Screenshot%202026-05-06%20203225.png)

---

# II. Create Snapshot

## 1. Action → Create Snapshot

### Navigate

```text
EC2 → Volumes → Actions → Create Snapshot
```

![](./Screenshot%202026-05-06%20192800.png)

---

## 2. Go To Snapshots

![](./Screenshot%202026-05-06%20203621.png)

---

## 3. Copy Snapshot To Mumbai Region

### Navigate

```text
Snapshots → Actions → Copy Snapshot
```

![](./Screenshot%202026-05-06%20203806.png)

---

## 4. Configure Destination Region

### Select Region

```text
ap-south-1 (Mumbai)
```

![](./Screenshot%202026-05-06%20203925.png)

---

# III. Launch New Instance In Mumbai Region

## 1. Switch To Mumbai Region

![](./3.png)

---

## 2. Check Snapshot

![](./Screenshot%202026-05-06%20193330.png)

---

## 3. Create Volume From Snapshot

### Navigate

```text
Snapshots → Actions → Create Volume From Snapshot
```

![](./Screenshot%202026-05-06%20204741.png)

![](./Screenshot%202026-05-06%20204840.png)

---

## 4. Check Volumes And Attach

### Navigate

```text
Volumes → Actions → Attach Volume
```

![](./Screenshot%202026-05-06%20205010.png)

---

## 5. Connect Mumbai EC2 And Show Disk

### Command

```bash
lsblk
```

![](./4.png)

---

## 6. Edit The System Filesystem Table

### Command

```bash
sudo vim /etc/fstab
```

### Add Entry

```bash
/dev/nvme1n1p1 /home/ec2-user/projects xfs defaults 0 0
```

![](./5.png)

---

## 7. Mount EBS Volume

### Commands

```bash
mkdir projects
sudo mount /home/ec2-user/projects
lsblk
```

![](./Screenshot%202026-05-06%20205605.png)

---

## 8. Verify Restored Files

### Commands

```bash
ls
cd projects
ls
```

![](./Screenshot%202026-05-06%20205717.png)

![](./Screenshot%202026-05-06%20205810.png)

---

# ✅ Project Outcome

Successfully migrated EBS volume data from:

- N. Virginia Region (`us-east-1`)
➡️ to
- Mumbai Region (`ap-south-1`)

using AWS EBS Snapshots.

---

# 🛠️ AWS Services Used

- Amazon EC2
- Amazon EBS
- Amazon EBS Snapshot

---
