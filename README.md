# Linux-Systems-Administration-_
Act as a system administrator in order to troubleshoot a malfunctioning Linux server.
Step 1: Ensure/Double Check Permissions on Sensitive Files

Permissions on /etc/shadow should allow only root read and write access.

Command to inspect permissions:

ls -l /etc/shadow


Command to set permissions (if needed):

sudo chomod u+rw /etc/shadow


Permissions on /etc/gshadow should allow only root read and write access.

Command to inspect permissions:

ls -l /etc/gshadow


Command to set permissions (if needed):

sudo chomod u+rw /etc/gshadow


Permissions on /etc/group should allow root read and write access, and allow everyone else read access only.

Command to inspect permissions:

ls -l /etc/group


Command to set permissions (if needed):

sudo chmod 644 /etc/group


Permissions on /etc/passwd should allow root read and write access, and allow everyone else read access only.

Command to inspect permissions:

ls -l /etc/passwd


Command to set permissions (if needed):

sudo chmod 644 /etc/passwd


Step 2: Create User Accounts

Add user accounts for sam, joe, amy, sara, and admin with the useradd command.

Command to add each user account (include all five users):

sudo useradd sam -m
sudo useradd joe -m
sudo useradd amy -m
sudo useradd sara -m
sudo useradd admin -m


Ensure that only the admin has general sudo access.

Command to add admin to the sudo group:

Sudo gpasswd -a admin sudocat


Step 3: Create User Group and Collaborative Folder

Add an engineers group to the system.

Command to add group:

sudo groupadd engineers


Add users sam, joe, amy, and sara to the managed group.

Command to add users to engineers group (include all four users):

sudo gpasswd -a sam engineers
sudo gpasswd -a joe engineers
sudo gpasswd -a amy engineers
sudo gpasswd -a sara engineers


Create a shared folder for this group at /home/engineers.

Command to create the shared folder:

mkdir /home/engineers


Change ownership on the new engineers’ shared folder to the engineers group.

Command to change ownership of engineers’ shared folder to engineers group:

sudo chown 1019 engineers/


Step 4: Lynis Auditing

Command to install Lynis:

Sudo apt install lynis


Command to view documentation and instructions:

man lynis


Command to run an audit:

lynis system audit


Provide a report from the Lynis output with recommendations for hardening the system.

Screenshot of report output:


Bonus

Command to install chkrootkit:

sudo apt install chkrootkit


Command to view documentation and instructions:

Man chkrootkit 


Command to run expert mode:

Sudo chkrootkit -x


Provide a report from the chrootkit output with recommendations for hardening the system.

Screenshot of end of sample output:

