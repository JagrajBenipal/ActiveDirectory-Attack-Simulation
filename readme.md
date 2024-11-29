# Active Directory and Security Monitoring Lab

## Disclaimer

This project was created in a simulated environment purely for educational purposes. All configurations, credentials, and network setups are fictional and not tied to any real-world systems. Sensitive details such as passwords and usernames have been simulated to ensure safety.

## Objective

I set up this lab to explore how to secure and monitor Active Directory environments. The goal was to create a networked setup with four virtual machines (VMs), simulate a credential-based attack, and analyze the resulting logs using Splunk. This hands-on project gave me insights into Active Directory management, attack detection, and log monitoring.

## Tools Used

- **VirtualBox**: Used to host and manage the virtual machines.
- **Windows Server 2022**: Configured as the Active Directory Domain Controller (VM1).
- **Splunk Server**: Used to collect and analyze event logs (VM2).
- **Kali Linux**: Used to simulate attacks (VM3).
- **Additional Clean VM**: Included for maintaining network integrity during testing (VM4).

## Steps

### Step 1: Setting Up the Virtual Network

The first step was creating a virtual NAT network to connect all four VMs. I configured the network so the Domain Controller, Splunk server, and Kali Linux machine could communicate seamlessly. This ensured a realistic environment for simulating attacks and analyzing logs.

**Screenshot:** `4-vms-within-the-same-network.png`  
![VMS Network](4-vms-within-the-same-network.png)  
_The VirtualBox setup showing the four VMs connected to the "AD-Project" NAT network._

---

### Step 2: Configuring Active Directory

I installed and configured Active Directory on the Domain Controller (VM1). I created a new domain, `myfir.local`, and set up organizational units like HR and IT to mirror a realistic corporate structure. I also added a test user, `jbenipal`, under the HR unit to simulate an employee account.

**Screenshot:** `jagraj-benipal-in-ad.png`  
![AD User Management](jagraj-benipal-in-ad.png)  
_Active Directory Users and Computers showing the user `jbenipal` added to the HR organizational unit._

---

### Step 3: Simulating an RDP Brute-Force Attack

With the environment set up, I used the Kali Linux VM (VM3) to simulate a brute-force attack using the `Crowbar` tool. The attack targeted the Domain Controller and successfully compromised the `jbenipal` account, revealing the password `password123`. This exercise demonstrated how weak credentials can be exploited by attackers.

**Screenshot:** `kali-linux-jbenipal-credentials-hacked.png`  
![RDP Attack Simulation](kali-linux-jbenipal-credentials-hacked.png)  
_The screenshot shows the successful brute-force attack on the `jbenipal` account._

---

### Step 4: Analyzing Logs with Splunk

To understand the attack better, I configured Splunk (VM2) to collect security event logs from the Domain Controller. Using Splunk's powerful search capabilities, I traced the attack and analyzed logon events for the compromised `jbenipal` account. This highlighted the importance of centralized logging and monitoring for detecting suspicious activity.

**Screenshot:** `splunk-shows-search-results.png`  
![Splunk Log Analysis](splunk-shows-search-results.png)  
_Splunk search results showing the security logs for the compromised `jbenipal` account._

---

## Conclusion

This project was a great learning experience. Setting up and managing a multi-VM environment, simulating a credential-based attack, and using Splunk for log analysis helped me better understand how to detect and respond to security incidents. It also reinforced the importance of strong credentials and proactive monitoring in protecting critical systems.
