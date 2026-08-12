Web Server Setup with Azure VM

Requirement:

Azure Free Account
Azure Portal
SSH client (PowerShell, Windows Terminal, or PuTTY)

Step1: Create Virtual Machine
1. search for azure vm and click on create 
2. select below setings in Basics 
Subscription             Azure subscription 1
Resource group           Azure-RG
Virtual machine name     Nginx
Region                   Central India
Availability options     No infrastructure redundancy required
Zone options             Self-selected zone
Security type            Trusted launch virtual machines
Enable secure boot       Yes
Enable vTPM              Yes
Integrity monitoring     No
Image                    Ubuntu Server 24.04 LTS - Gen2
VM architecture          x64
Size                     Standard B2ats v2 (2 vcpus, 1 GiB memory)
Enable Hibernation       No
Authentication type      Password
Username                 ubuntu
Public inbound ports     SSH (22)
Azure Spot               No

3. Review and create 


Step2: Get the Public IP
Open the VM and copy the ip --->(20.219.x.xxx)

Step3: Connect the Virtual Machine using Terminal   (you can also download the opnenSSH for windows)

1. open terminal and type (ssh -i ubuntu_1.pem ubuntu@20.219.5.210)...download pem key for 1st time while creating vm
2.yes 
3. type your password
4. sudo su -

Step4: Update and install Nginx. run below commands one by one

1.sudo apt update
2.sudo apt upgrade -y
3.sudo apt update
4.sudo apt upgrade -y
5.systemctl status nginx
6.apt install nginx -y
7.systemctl status nginx
8.sudo systemctl enable nginx
9.sudo systemctl start nginx

Step5: Configure the network security group
1. Open your VM and navigate to networking on left panel
2. You will see inbound rule, click on add inbound rule
3. Setting	                   Value
------------------------------------------
Source	                       Any
Source Port                   	*
Destination	                   Any
Protocol	                     TCP
Destination Port              	80
Action	                       Allow
Priority	                    300/310
Name	                       Allow-HTTP

4.Click Add.

Step6: Test the webpage

1. visit http://<public-ip>  ( refer step 2)
2. you will see the nginx welcome page
3. you can also replace the default webpage with diffrent html file 
4. open terminal and navigate to cd /var/www/html
5. you will find--> index.nginx-debian.html (you can edit the html file using vi editor)
