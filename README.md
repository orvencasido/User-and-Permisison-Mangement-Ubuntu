
# User and Permission Management on Ubuntu

### This project demonstrates how to manage users, groups, and file permissions in a Linux (Ubuntu) server. The entire setup is done on an AWS EC2 instance using Ubuntu.

## 🛠 Tools & Technologies

- 🔸 Ubuntu (Linux)
- 🔸 AWS EC2 Instance
- 🔸 SSH (Secure Shell)
- 🔸 Linux User Management Commands (`adduser`, `groupadd`, `usermod`, `chown`, `chmod`)
- 🔸 Terminal (Bash)

## 🚀 Project Overview
This project includes:

- Creating user accounts (`orven`, `francis`, `nicklas`)
- Creating team groups (`frontend-dev`, `backend-dev`)
- Assigning users to groups
- Setting up shared directories with correct group permissions
- Testing access control using actual user accounts

## 📋 Step-by-Step Guide
### ✅ 1. Launch EC2 and SSH In
- Create a new EC2 instance using Ubuntu.
- Set security groups.
- Connect using this ssd command: 
ssh -i your-key.pem ubuntu@your-ec2-public-ip

### ✅ 2. Create Users
- sudo adduser orven
- sudo adduser francis
- sudo adduser nicklas

### ✅ 3. Create groups
- sudo addgroup frontend-dev
- sudo addgroup backend-dev

### ✅ 4. Assign Users to Groups
- sudo usermod -aG frontend-dev orven
- sudo usermod -aG frontend-dev francis
- sudo usermod -aG backend-dev nicklas

### ✅ 5. Create Shared Team Directories
- sudo mkdir -p /shared/frontend-dev
- sudo mkdir -p /shared/backend-dev

### ✅ 6. Set Group Ownership
- sudo chown :devteam /shared/frontend-dev
- sudo chown :marketing /shared/backend-dev

### ✅ 7. Set Group Permissions
- sudo chmod 770 /shared/frontend-dev
- sudo chmod 770 /shared/backend-dev
- sudo chmod g+s /shared/frontend-dev
- sudo chmod g+s /shared/backend-dev

## 📸 Example Output
- $ ls -l /shared/frontend-dev/
- -rw-r--r-- 1 orven frontend-dev 0 May 9 17:00 test.txt

## 📎 Commands Reference
- `adduser`	Add new user
- `groupadd`	Add new group
- `usermod -aG`	Add user to group (append)
- `chown :group folder/`	Change group ownership
- `chmod 770`	Full access for owner/group, none for others
- `chmod g+s`	Make new files inherit group
- `userdel -r`	Delete user and their home directory

## 💡 Real-World Use Cases

- Enforce access control in shared directories.
- Manage department-based access.
- Practice Linux server hardening basics.
- Simulates actual enterprise server environments.

## 📚 Learning Outcomes
- Linux user and group management
- Secure file permission control
- Practical testing of access rights
- Basic user-level security practices

## 📂 Folder Structure
- /shared
- ├── devteam
- └── marketing

## 🧑‍💻 Author
Orven Casido - techwithorven.xyz





