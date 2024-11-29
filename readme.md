# Active Directory and Security Monitoring Lab

## Disclaimer

This project was conducted in a controlled, simulated environment created for educational and demonstration purposes. All data, configurations, and credentials shown are part of a test lab and do not reflect any real-world production systems. Sensitive information such as passwords, usernames, and network configurations have been simulated and do not represent actual systems.

## Objective

This project focused on setting up a virtualized Active Directory environment with Kali Linux and Splunk to simulate attacks, monitor security events, and analyze logs. It aimed to demonstrate Active Directory management, simulate credential-based attacks, and log analysis using Splunk.

## Steps

### Step 1: Setting Up the Virtual Network

Configured multiple virtual machines (Kali Linux, Splunk, and Active Directory Domain Controller) within the same NAT network to facilitate communication.

**Screenshot:** `4-vms-within-the-same-network.png`  
![VMS Network](4-vms-within-the-same-network.png)  
_The network settings for the Kali Linux VM are shown, connected to the "AD-Project" NAT network._

---

### Step 2: Configuring Active Directory

Created and managed users and organizational units in the Active Directory Domain Controller. A user account `jbenipal` was added under the appropriate organizational unit.

**Screenshot:** `jagraj-benipal-in-ad.png`  
![AD User Management](jagraj-benipal-in-ad.png)  
_Active Directory Users and Computers showing the structure and the user `jbenipal` under the HR organizational unit._

---

### Step 3: Simulating an RDP Brute-Force Attack

Using the Kali Linux VM, performed an RDP brute-force attack with the `Crowbar` tool to compromise the `jbenipal` account credentials.

**Screenshot:** `kali-linux-jbenipal-credentials-hacked.png`  
![RDP Attack Simulation](kali-linux-jbenipal-credentials-hacked.png)  
_The successful brute-force attack against the `jbenipal` user account is shown, revealing the password._

---

### Step 4: Analyzing Logs with Splunk

Configured Splunk to ingest security event logs from the Active Directory Domain Controller. Queried the logs to identify the successful brute-force attack and the compromised user account activity.

**Screenshot:** `splunk-shows-search-results.png`  
![Splunk Log Analysis](splunk-shows-search-results.png)  
_Splunk search results displaying security event logs, showing the compromised `jbenipal` account activity._

---

## Tools Used

- **VirtualBox**: For virtualization of the environment.
- **Windows Server 2022**: As the Active Directory Domain Controller.
- **Kali Linux**: For simulating credential attacks.
- **Splunk**: For monitoring and analyzing security event logs.

## Conclusion

This project demonstrated the practical implementation of an Active Directory environment, simulated credential-based attacks, and log analysis using Splunk. It provided hands-on experience in attack detection, user management in Active Directory, and event monitoring in a secure network.
