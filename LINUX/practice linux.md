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

























