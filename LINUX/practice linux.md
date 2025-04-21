# TASK 1

## 🌐how to check size of any folder 

- ubuntu@ip-172-31-25-24:~$ du -sh /home/ubuntu/

5.6G    /home/ubuntu/



## 🌐 Create a user devops_user and add them to a group devops_team. Set a password and grant sudo access. Restrict SSH login for certain users in /etc/ssh/sshd_config.


- ubuntu@ip-172-31-25-24:~$ sudo useradd -m devops_user -s /bin/bash

- ubuntu@ip-172-31-25-24:~$ sudo groupadd devops_team

- ubuntu@ip-172-31-25-24:~$ sudo usermod -aG devops_team devops_user


## another method to directly create user and directly add in group


### first create group 

- sudo groupadd devops_team

### and below command user will be created and also will be added in group 

- sudo useradd -m -s /bin/bash -G devops_team ram_singh

### to grant access add the user in sudo group /etc/group u can see there 

- ubuntu@ip-172-31-25-24:~$ sudo usermod -aG sudo devops_user




## 🚀Real scenario with find 
- ![image](https://github.com/user-attachments/assets/222f9028-907a-4f67-98a8-ef917f4d617b)



# 🚀 Blocking user or group to do ssh

- Edit the SSH configuration file like below :

- sudo vim /etc/ssh/sshd_config >>>>>this will open window press i then follow the below steps to add command for allowing and disallowing

- DenyUsers user1 user2   >>>>this will deny 

- AllowUsers devops_user adminuser  >>>>this will allow only these specific users

like wise you can also block group so eventually it will block all users under that group

- DenyGroups developers testers >>>>All users who belong to these groups are not allowed SSH access.
- AllowGroups devops_team admins >>>All users who belong to these groups are allowed SSH access.

once done then press esc + wq to save the file 
  
After changing this file, restart SSH:

- sudo systemctl restart ssh

# 🔍 Why is it ssh and not sshd?

- Ubuntu uses the openssh-server package, and the service is registered as ssh.service.

- Other distros like CentOS or RHEL often call it sshd.

# 🔐 What is /etc/ssh/sshd_config?

- This is the main configuration file for the SSH server (the daemon: sshd). It controls:

- Who can log in via SSH

- How they authenticate (password, key, etc.)

- Which users are allowed or denied access

- Other security settings (port, timeout, root login, etc.)

- 📌 If you make changes here, it affects all SSH remote access to your system.



# Delete everything from specific folder exceept that folder 

## if u inside the folder 

-`rm -rf ./*`

## if outside the folder and lets say want to delete file from practice_20Apr foldder

- `rm -rf practice_20apr/*`




# TASK 2

## 🌐 File & Directory Permissions

Task:
- Create `/devops_workspace` and a `file project_notes.txt`.
- Set permissions:
  - **Owner can edit**, **group can read**, **others have no access**.
-Use ls -l to verify permissions.

![image](https://github.com/user-attachments/assets/9a466954-551d-4962-81ef-8adaf7ac9b8a)



# TASK 3

## Process Management & Monitoring
Task:
- Start a background process (ping google.com > ping_test.log &).
  - Use ps, top, and htop to monitor it.
  - Kill the process and verify it's gone.
 
ubuntu@ip-172-31-25-24:~$ ping google.com > ping_test.log & >>>>>this will save the output in file ping_test.log and because of & will be running continiously in background


ubuntu@ip-172-31-25-24:~$ jobs >>>>>>>>>>>>> to verify running process

[1]+  Stopped                 vim /etc/ssh/ssh_config  (wd: ~/practice_20Apr)

[2]-  Running                 ping google.com > ping_test.log & >>>>>>>>>>>>>>>>>>>>>>>>>>>>>

## `top`

press / then type ping and press enter     >>>>>will filter ping running process

## `ps`

![image](https://github.com/user-attachments/assets/bd5f3721-d861-4d42-b6c1-bcf02dbc99a6)


## `htop`

Use arrow keys to find the ping process

Or press / and type ping to filter

You can kill it directly from htop by selecting and pressing F9, then choose signal 9


## `kill`


![image](https://github.com/user-attachments/assets/c929182e-37c7-4d80-a905-c3303477feb1)




# TASK 4

Automate Backups with Shell Scripting

- Write a shell script to back up /devops_workspace as backup_$(date +%F).tar.gz.
- Save it in /backups and schedule it using cron.
- Make the script display a success message in green text using echo -e.

## Script:

![image](https://github.com/user-attachments/assets/e7c09d45-31a3-40b6-8778-9bf03ec30832)

## Crontab to automate the script

![image](https://github.com/user-attachments/assets/1428e504-8e6f-44ea-b832-10307e31468d)



## NOTE while running these scripts I felt error because script was assigned to root not ubuntu so i changed it after that started working

![image](https://github.com/user-attachments/assets/ae1261a3-2cae-40f6-9148-dacd8749bf09)





