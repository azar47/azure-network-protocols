<p align="center">
<img src="https://i.imgur.com/Ua7udoS.png" alt="Traffic Examination"/>
</p>

# Network Security Groups (NSGs) and Inspecting Traffic Between Azure Virtual Machines

## Project Summary
This project demonstrates how network traffic flows between Azure Virtual Machines and how Network Security Groups (NSGs) affect that traffic. Using a Windows 10 VM with Wireshark and an Ubuntu Server VM, I tested different protocols such as ICMP, SSH, DNS, and HTTP/HTTPS. I then modified NSG rules to observe how blocking or allowing certain traffic changes the results.

**Environments Used:** Microsoft Azure Virtual Machines  
**Operating Systems:** Windows 10, Ubuntu Server 20.04  
**Tools / Technologies:** Wireshark, NSGs, Ping, SSH, DNS, HTTP/HTTPS  

The goal of this project was to better understand cloud networking, packet inspection, and how NSGs act like firewalls in Azure.

## Demonstration


<img width="1920" height="1080" alt="NSGscreenshot1" src="https://github.com/user-attachments/assets/39cbb013-5c48-432b-b7d9-d2b0502973c2" />
Screenshot 1: Wireshark running on the Windows VM capturing network traffic.  

<img width="1920" height="1080" alt="NSGscreenshot2" src="https://github.com/user-attachments/assets/850d62fa-a2c1-49a4-b84c-efae887bdf4a" />
Screenshot 2: SSH connection from the Windows VM to the Ubuntu Server.  

<img width="1889" height="788" alt="NSGscreenshot3" src="https://github.com/user-attachments/assets/717cd840-2780-4dd8-964c-7cb4c98301d8" />
Screenshot 3: NSG inbound rules (before and after blocking ICMP).  

<img width="1920" height="1080" alt="NSGscreenshot4" src="https://github.com/user-attachments/assets/2776a8af-7a7f-4346-996f-78b82c0e2a65" />
Screenshot 4: Ping failing after ICMP is blocked in the NSG.  

<img width="1920" height="1080" alt="NSGscreenshot5" src="https://github.com/user-attachments/assets/5eae2f25-a990-41a3-a3b5-642a592f7d9f" />
Screenshot 5: DNS or HTTP/HTTPS packets captured in Wireshark.  

## Demonstration
1. Created two Azure VMs on the same virtual network:  
   - Windows 10 (used for Wireshark and testing)  
   - Ubuntu Server (used for SSH, DNS, and general network testing)

2. Installed Wireshark on the Windows VM and started a live packet capture.

3. Used different protocols to generate traffic between the VMs:  
   - ICMP using 'ping'
   - SSH connection to Ubuntu  
   - DNS lookups with 'nslookup'
   - HTTP/HTTPS traffic using a browser or 'curl'

4. Modified NSG inbound rules to block specific protocols (like ICMP) and observed:  
   - Ping traffic being blocked  
   - No packets appearing in Wireshark when rules denied the traffic  
   - Traffic working again after reenabling the rule  

The project demonstrates how NSGs filter traffic and how to inspect packets in real time using Wireshark.
