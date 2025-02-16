# Week 2: Linux System Administration & Automation Solution

## 🚀 Task :
### Create a user devops_user and add them to a group devops_team.

  **Solution:**
  
  sudo useradd -m -G devops_team -s /bin/bash devops_user

  ### Set a password and grant **sudo** access.
 **Solution:**
  sudo passwd dev
 #### granting sudo access
  sudo gpasswd -a devops_user sudo

  #### Restrict SSH login for certain users in `/etc/ssh/sshd_config`.
  **Solution:**
- Run `sudo nano /etc/ssh/sshd_config` to edit the ssh configuration file.
- Append `DenyUsers devops_user` to the file.
- Save the file and restart the ssh service using `sudo systemctl restart sshd

  
