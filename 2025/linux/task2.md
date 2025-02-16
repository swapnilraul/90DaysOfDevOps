# File & Directory Permissions
## Create /devops_workspace and a file project_notes.txt.
**solution**
sudo mkdir /devops_workspace
  ### changing the ownership of the directory
  sudo chown ubuntu:ubuntu /devops_workspace

  touch /devops_workspace/project_notes.txt
### Set permissions:
   **Owner can edit**, **group can read**, **others have no access**.
  **Solution:**   
    chmod 640 /devops_workspace/project_notes.txt
- Use `ls -l` to verify permissions.

  **Solution:**

  ubuntu@ip-65-0-87-32:~$ ls -l /devops_workspace/project_notes.txt
  -rw-r----- 1 ubuntu ubuntu 0 Feb 14 18:48 /devops_workspace/project_notes.txt
