# Linux User Management

Effective user management in Linux includes creating users, managing groups, assigning privileges, and executing commands as different users.

## User Commands

```bash
# Create a user with home directory
sudo useradd -m alex
sudo passwd alex      # set password

# Modify user
sudo usermod -aG developers alex   # add to group
sudo usermod -s /bin/bash alex     # change shell

# Delete user
sudo userdel alex       # keep home
sudo userdel -r alex    # remove home

# Manage groups
sudo addgroup developers
sudo delgroup developers

# Password management
sudo passwd alex      # change password
sudo passwd -l alex   # lock account
sudo passwd -u alex   # unlock account

# Execute commands as another user
su -                 # switch to root
sudo cat /etc/shadow  # run command as root
