# Network-Analysis-Lab
This will be a lab focusing on analyzing network traffic on both Windows and Linux systems. The lab will be split up into 4 parts for convenience. 

# As a disclaimer, it is highly recomended that this and any other labs, be conducted on a Virtual Machine(both Windows and Linux based) with known good backups!

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
- Linux terminal for utilizng command line tools including nmap and ifconfig.
- Network Miner to extract artifacts and capture network PCAP files.

### Steps Part 1

### This section will be conducted as the root user


1. Open up the Linux VM and initiate the terminal using either the applications tab, or the command control of Ctrl +  Alt + T.
   
2. Type the following command to display the hosts file on your Kali Linux system, "cat /etc/hosts"
   
   ![1 hosts](https://github.com/Lantern76/Network-Analysis-Lab/assets/119342094/8fe4e9ad-d20c-4585-9897-2ed5caffeb95)

3. Type the following command to add yourname to the /etc/hosts file, "yourname >> /etc/hosts
   
   ![1 echo name](https://github.com/Lantern76/Network-Analysis-Lab/assets/119342094/f9fe2d10-ec88-4788-8a33-a479a23fd961)

4. Type the following command to determine the open ports on your system, "nmap yourname"
   
   ![2 nmap Ryan](https://github.com/Lantern76/Network-Analysis-Lab/assets/119342094/4eeab913-b3ff-47eb-8ef0-6032a908195c)

5. Type the following command to start your Apache web server, "service apache2 start"
    
    ![2 apache](https://github.com/Lantern76/Network-Analysis-Lab/assets/119342094/fec3be45-780c-4b56-b87b-6fd5e018f568)

6. Type the following command to determine the open ports on your system, "nmap yourname"
    
    ![2 nmap Ryan](https://github.com/Lantern76/Network-Analysis-Lab/assets/119342094/b41d10fa-9f25-4a99-b19d-5997cf4a512b)

7. Type the following command to update the repo files, "apt-get update"
    
    ![3 apt-get update](https://github.com/Lantern76/Network-Analysis-Lab/assets/119342094/68eb3b8c-658c-4876-a17c-729086d051b8)

8. Type the following command to install vsftpd (Very Secure File Transfer Protocol), "apt install vsftpd"
    
    ![4 vsftpd](https://github.com/Lantern76/Network-Analysis-Lab/assets/119342094/9459f031-17fa-410e-a49b-ccfb2154c153)

9. Type the following command to start the FTP server, "service vsftpd start"
    
    ![5 vsftpd start](https://github.com/Lantern76/Network-Analysis-Lab/assets/119342094/093c520b-4ad2-4567-8109-9d31123ea4ef)

10. Type the following command to determine the open ports on your system, "nmap yourname"
      - Replace yourname with your first name
        
    ![4 ftp nmap](https://github.com/Lantern76/Network-Analysis-Lab/assets/119342094/ff182d2e-5f51-4dcb-adfd-5f8f88561f25)

11. Type the following command to add a user called yournameftp (no spaces), "useradd yournameftp -m"
    
    ![5 add user ryanftp](https://github.com/Lantern76/Network-Analysis-Lab/assets/119342094/49d15679-8a3a-4ae6-b1e4-a301509515f4)

12. Type the following command to give the yournameftp account a password. Type yourname for the password and confirm the password of yourname, "passwd yournameftp"
    
    ![6 passwd](https://github.com/Lantern76/Network-Analysis-Lab/assets/119342094/7c6218ba-c898-4108-8b87-47cc8fad7b5f)

13. Next, we will copy a file to the ftp root for the user account. Type the following command to copy a file to the yournameftp directory, "cp /usr/share/windows-binaries/wget.exe /home/yournameftp/yourname.exe"
    
    ![6 ls ryanftp](https://github.com/Lantern76/Network-Analysis-Lab/assets/119342094/df62da56-4db2-4c43-90a7-7b7600f230ce)

14. Next, we will copy a file to the ftp root for the user account. Type the following command to copy a file to the webroot directory, " cp /usr/share/windows-binaries/wget.exe /var/www/html/yourname.exe"
    
15. Use the following command to view the saved files on the service, " ls /var/www/html"
    
![7 ls html](https://github.com/Lantern76/Network-Analysis-Lab/assets/119342094/1714469b-9409-4f33-9a95-087964db5674)


### Steps Part 2


1. Enter the terminal and use the following command to see the systems IP address, "ifconfig"
   
   ![1 ifconfig](https://github.com/Lantern76/Network-Analysis-Lab/assets/119342094/9cc468f0-7acb-4da0-b308-01db7fc881bb)

3. Type the following command on Linux to launch wireshark, "wireshark"
   
   ![2 wireshark](https://github.com/Lantern76/Network-Analysis-Lab/assets/119342094/8c7d3327-ee7c-4468-a08a-b02929de33ed)

5. Double click on any in the list of interfaces
   
   ![3 any etho](https://github.com/Lantern76/Network-Analysis-Lab/assets/119342094/e4b27464-c60f-440e-87b0-cc67f0633ec2)

7. Switch to the Windows VM and enter the cmd
   
9. Enter the following command using the previously discovered IP of the Linux machine in step 1, "nmap (IP)"
    - You will see the same list of open ports that you saw when you scanned the machine locally
      
   ![4 nmap ](https://github.com/Lantern76/Network-Analysis-Lab/assets/119342094/9f194720-d1ec-41d2-bc99-13e6b3117f73)

11. In Wirshark under the Windows VM, Type tcp.flags.reset == 1 the filter pane and click apply. This shows you a list of closed ports on the Linux system
    
    ![5 tcp wireshark](https://github.com/Lantern76/Network-Analysis-Lab/assets/119342094/ec4556b4-655b-40a3-840a-22447e44c489)

13. Type tcp.flags.syn ==1 && tcp.flags.ack == 1 in the filter pane and click apply. This shows you a list of open ports on the Linux system
    
    ![6 wireshark flags](https://github.com/Lantern76/Network-Analysis-Lab/assets/119342094/364f9919-9b53-4224-aa1b-66dbdbe691a2)

15. Select File in the Wireshark menu and click close to exit Wireshark. Stop and Quit without saving.
    
![7 quit wireshark](https://github.com/Lantern76/Network-Analysis-Lab/assets/119342094/1025ee06-99b8-4477-8c43-5812801e2c6d)


### Steps Part 3


1. In the Start search box, type Wireshark and then select Wireshark
   
   ![1 start wireshark](https://github.com/Lantern76/Network-Analysis-Lab/assets/119342094/793f04a5-49af-4a74-8ef6-bd6048a53402)

3. Double click on Ethernet4
   
   ![2 etho 4](https://github.com/Lantern76/Network-Analysis-Lab/assets/119342094/10e7b8cd-9def-462c-9c9c-f81d3c653d6c)

5. Copy IP address of Linux machine
   
7. Double Click on the WINSCP shortcut
   
   ![winscp](https://github.com/Lantern76/Network-Analysis-Lab/assets/119342094/0ddf6313-27fe-47d6-bfa4-7379210ccae2)

9. In the drop down box, select FTP for the protocol. Paste the IP Address from Linux. If copy/paste does not work, type the 32-bit IPv4 address in manually. Put "yourname"ftp for the username and yourname for the password. Click the Login button
    
    ![4 ftp](https://github.com/Lantern76/Network-Analysis-Lab/assets/119342094/ecd9672b-5390-4646-ab0a-1d4fc81359a1)

11. Drag the yourname.exe file to the left-hand pane
    
    ![5 yournameftp](https://github.com/Lantern76/Network-Analysis-Lab/assets/119342094/477d8271-1fe1-411b-9375-e848c119e7da)

13. Close WinSCP
    
15. Type IE in the search bar and then launch the Internet Explorer app. Click Use Recommended settings
    
    ![6 IE](https://github.com/Lantern76/Network-Analysis-Lab/assets/119342094/86128eec-b105-4073-a43f-38ba47fcf86d)

17. Paste the IP Address from MARS. If copy/paste does not work, type the 32-bit IPv4 address in manually. After that, put /yourname.exe, replacing yourname with your first name
    
    ![7 IE yournmae](https://github.com/Lantern76/Network-Analysis-Lab/assets/119342094/3b373b02-2343-4096-bc0b-da34535cfe05)

19. Choose the Downloads folder and click Save
    
    ![8 downloads folder](https://github.com/Lantern76/Network-Analysis-Lab/assets/119342094/1a926185-213c-4795-85b3-5fda7148476f)

21. Click the stop button to stop the Wireshark capture
    
    ![9 stop wireshark](https://github.com/Lantern76/Network-Analysis-Lab/assets/119342094/943fa23c-728c-4c04-ac4a-07e10a4519bf)

23. In the filter pane type frame contains PASS
    
    ![10 filter frame](https://github.com/Lantern76/Network-Analysis-Lab/assets/119342094/181bf0e2-78d1-433b-ac25-76a97ff67138)

25. Scroll down until you see the name yourname.exe
    
    ![11 yourname exe](https://github.com/Lantern76/Network-Analysis-Lab/assets/119342094/2dc65aa2-61cc-408c-a5ee-4ecfcbd42273)

27. Click Close
    
29. Click File, Save as
    
31. Change the file type to tcpdump (pcap format)
    
    ![12 save as ](https://github.com/Lantern76/Network-Analysis-Lab/assets/119342094/f1d9c61e-652c-4221-9c2c-6e0c509d040e)

33. Click Desktop, and then save the file as UMGC
    
35. Close Wireshark


### Steps Part 4


1. Type Network Miner in the Start Search box and then select Network Miner
   
   ![1 ](https://github.com/Lantern76/Network-Analysis-Lab/assets/119342094/b8919b34-2a40-4949-8899-0830605ddd98)

3. Drag the UMGC file into the NetworkMiner pane
   
   ![2](https://github.com/Lantern76/Network-Analysis-Lab/assets/119342094/83449826-bcdd-439c-aaec-30c7fec830a5)

5. Notice the IP Addresses and host names, as well as the identified operating systems
   
   ![3](https://github.com/Lantern76/Network-Analysis-Lab/assets/119342094/50ea2214-6cc2-4ae0-94f2-b42597cce430)

7. Click the Files tab. Notice the yourname file
   
   ![4](https://github.com/Lantern76/Network-Analysis-Lab/assets/119342094/29454c67-ff90-4736-a286-e91caac7dcca)

9. Expand the Window to maximize NetworkMiner. Click the credentials tab. Notice that under the FTP protocol, that yourname is displayed as the password
    
![5](https://github.com/Lantern76/Network-Analysis-Lab/assets/119342094/ab47c53d-f1f0-4eea-a0d6-448ca7795b19)



### This was an excellent lab to gain hands on experience in capturing network traffic and analyzing the results using both Wireshark and Network Miner! This is a small step into the realm of network monitoring and I plan on messing around with the tools much more to see what other utilities they may offer :)
















