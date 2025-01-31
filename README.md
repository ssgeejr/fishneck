# fishneck
Cybersecurity Tools and Personal Study

Tools: 
## VMWare
https://blogs.vmware.com/workstation/2024/05/vmware-workstation-pro-now-available-free-for-personal-use.html

## Kali Homepage
https://www.kali.org/

## Kali Images
https://www.kali.org/get-kali/#kali-installer-images

## Kali VM's
https://www.kali.org/get-kali/#kali-virtual-machines


### CREDENTIALS 
Kali's Default Credentials
Kali changed to a non-root user policy by default since the release of 2020.1.

This means:

During the installation of amd64 images, it will prompt you for a standard user account to be created.

Any default operating system credentials used during Live Boot, or pre-created image (like Virtual Machines & ARM) will be:


User: kali
Password: kali


Vagrant image (based on their policy):
Username: vagrant
Password: vagrant


Amazon EC2:
User: kali
Password: <ssh key>
Default Tool Credentials


Some tools shipped with Kali, will use their own default hardcoded credentials (others will generate a new password the first time its used). The following tools have the default values:


BeEF-XSS
Username: beef
Password: beef
Configuration File: /etc/beef-xss/config.yaml


MySQL
User: root
Password: (blank)
Setup Program: mysql_secure_installation


OpenVAS
Username: admin
Password: <Generated during setup>
Setup Program: openvas-setup


Metasploit-Framework
Username: postgres
Password: postgres
Configuration File: /usr/share/metasploit-framework/config/database.yml


PowerShell-Empire/Starkiller
Username: empireadmin
Password: password123


# Wireshark
https://www.wireshark.org/#downloadLink

# NMAP
https://nmap.org/download.html

# NCAP
https://npcap.com/

# Metasploit-Framework
https://www.metasploit.com/

# Nessus
https://community.tenable.com/s/article/Nessus-Essentials?language=en_US

# Snort
https://www.snort.org/

# TCPDump
https://appsource.microsoft.com/en-us/product/web-apps/microolap.tcpdump?tab=overview

# WINDump
https://www.winpcap.org/windump/

# Maltego
https://www.maltego.com/



## CISA CSET
https://github.com/cisagov/cset/releases


# Tools list for Penetration Testing
https://online.yu.edu/katz/blog/best-kali-linux-tools-for-hacking-penetration-testing

