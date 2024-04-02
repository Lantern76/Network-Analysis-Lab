# Network-Analysis-Lab
This will be a lab focusing on analyzing network traffic on both Windows and Linux systems. The lab will be split up into 2 parts for convenience. 

# As a disclaimer, it is highly recomended that this and any other labs, be conducted on a Virtual Machine(both Windows and Linux based) with known good backups as we will be stopping certain startup tasks and utilizing the command prompt!

# Network-Traffic-Analysis-Lab 

## Objective

The Network Traffic lab is designed for individuals to become more familiar with the basics of analyzing network traffic coming from their local machine. Analyzing network traffic plays a large role in many careers including SOC analyst, Incident Response, and Blue Team roles. This lab will use a variety of tools in both Windows and Linux systems. These tools can be considered some of the most common ones that will be used in the field and as always I recomend you play around with them to discover all their uses and become familiar with how they are used. 

### Skills Learned

- Basic understanding of Network analysis concepts and practical application.
- Proficiency in analyzing and interpreting network traffic logs.
- Ability to utilize the GUI of the Wireshark Tool.
- Enhanced knowledge of network traffic and understanding of how to read/understand their logs.
- Development of critical thinking and problem-solving skills in cybersecurity.

### Tools Used


- WireShark for capturing and analyzing network traffic on Windows/Linux systems. 
- Linux terminal for utilizng command line tools including nmap and ifconfig, 

### Steps Part 1

### This section will be conducted as the root user


1. Open up the Linux VM and initiate the terminal using either the applications tab, or the command control of Ctrl +  Alt + T.
2. Type the following command to display the hosts file on your Kali Linux system, "cat /etc/hosts"
3. Type the following command to add yourname to the /etc/hosts file, "yourname >> /etc/hosts
4. Type the following command to determine the open ports on your system, "nmap yourname"
5. Type the following command to start your Apache web server, "service apache2 start"
6. Type the following command to determine the open ports on your system, "nmap yourname"
7. Type the following command to update the repo files, "apt-get update"
8. Type the following command to install vsftpd (Very Secure File Transfer Protocol), "apt install vsftpd"
9. Type the following command to start the FTP server, "service vsftpd start"
10. Type the following command to determine the open ports on your system, "nmap yourname"
      - Replace yourname with your first name
12. Type the following command to add a user called yournameftp (no spaces), "useradd yournameftp -m"
13. Type the following command to give the yournameftp account a password. Type yourname for the password
      and confirm the password of yourname, "passwd yournameftp"
14. Next, we will copy a file to the ftp root for the user account. Type the following command to copy a file to the
      yournameftp directory, "cp /usr/share/windows-binaries/wget.exe /home/yournameftp/yourname.exe"
15. Next, we will copy a file to the ftp root for the user account. Type the following command to copy a file to the
      webroot directory, " cp /usr/share/windows-binaries/wget.exe /var/www/html/yourname.exe"
16. Use the following command to view the saved files on the service, " ls /var/www/html"


### Steps Part 2


1. Enter the terminal and use the following command to see the systems IP address, "ifconfig"
2. Type the following command on Linux to launch wireshark, "wireshark"
3. Double click on any in the list of interfaces
4. Switch to the Windows VM and enter the cmd
5. Enter the following command using the previously discovered IP of the Linux machine in step 1, "nmap (IP)"
    - You will see the same list of open ports that you saw when you scanned the machine locally
7. In Wirshark under the Windows VM, Type tcp.flags.reset == 1 the filter pane and click apply. This shows you a list of closed ports on the Linux system
8. Type tcp.flags.syn ==1 && tcp.flags.ack == 1 in the filter pane and click apply. This shows you a list of open ports on the Linux system
9. Select File in the Wireshark menu and click close to exit Wireshark. Stop and Quit without saving.

















