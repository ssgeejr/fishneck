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

# Armitage
https://www.offsec.com/metasploit-unleashed/armitage/

# Nessus
https://community.tenable.com/s/article/Nessus-Essentials?language=en_US

# Snort
https://www.snort.org/

# TCPDump
https://appsource.microsoft.com/en-us/product/web-apps/microolap.tcpdump?tab=overview

# WINDump
https://www.winpcap.org/windump/
https://github.com/hsluoyz/WinDump

# Maltego
https://www.maltego.com/

# GRASSMARLIN
https://github.com/nsacyber/GRASSMARLIN
https://sourceforge.net/projects/grassmarlin.mirror/
https://www.infosecinstitute.com/resources/scada-ics-security/situational-awareness-ics-using-grass-marlin/
https://www.osti.gov/servlets/purl/1409972
https://github.com/nsacyber/GRASSMARLIN/blob/master/GRASSMARLIN_Briefing_20170210.pptx

# Iodine
https://github.com/yarrick/iodine

# DNSCAT2
https://www.kali.org/tools/dnscat2/
https://github.com/iagox86/dnscat2

# Security Onion
https://github.com/Security-Onion-Solutions/securityonion

# Netbox
https://github.com/netbox-community/netbox
https://github.com/netbox-community/netbox-docker



```
	wget https://github.com/nsacyber/GRASSMARLIN/releases/download/v3.2.1/grassmarlin_3.2.1.kali-1_amd64.deb
	sudo apt install ./grassmarlin_3.2.1.kali-1_amd64.deb
```

# SHODAN
https://www.shodan.io/

#GreyNoise
https://viz.greynoise.io/

#BinaryEdge
https://www.binaryedge.io/

#Netlas
https://netlas.io/

#ZoomEye
https://www.zoomeye.ai/

#Censys
https://censys.com/

# GHDB
https://www.exploit-db.com/google-hacking-database

# TheDude (MIKROTIC The Dude)
https://softfamous.com/the-dude/download/

# OpenVAS
https://www.openvas.org/

# Nikto
https://cirt.net/Nikto2

# OWASP-ZAP
https://www.stationx.net/owasp-zap-tutorial/

# ENCASE
https://www.opentext.com/products/forensic


## Image/Container Based

# Trivy
https://trivy.dev/latest/

# Kube-Bench
https://github.com/aquasecurity/kube-bench

## CISA CSET
https://github.com/cisagov/cset/releases


# Tools list for Penetration Testing
https://online.yu.edu/katz/blog/best-kali-linux-tools-for-hacking-penetration-testing


### Kali Multi-Monitor
First open "Display" and enable [x] Mirror

https://forums.kali.org/archived/showthread.php?26887-SOLVED-Kali-Linux-laptop-lid-close-actions
edit file: `/etc/systemd/logind.conf`
Just uncomment the "HandleLidSwitch=suspend" and change 'suspend' to the most appropriate option (ignore,halt,poweroff,kexec,hibernate,reboot,lock).
restart service: `systemctl restart systemd-logind`


Helpful commands

meterpreter ... search


https://blog.didierstevens.com/2017/08/14/using-metasploit-on-windows/

https://www.youtube.com/watch?v=2ssKmTPxLh0&ab_channel=CloudSecurityTraining%26Consulting







