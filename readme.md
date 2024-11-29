# Active Directory and Security Monitoring Lab

## Disclaimer

This project was conducted in a simulated environment designed for educational purposes. All configurations, credentials, and network setups are fictional and not tied to any real-world systems. Sensitive details have been redacted or simulated to ensure safety.

## Objective

This lab focused on setting up a virtualized environment with multiple VMs to simulate and analyze security events. The goal was to understand Active Directory management, simulate a brute-force attack, and analyze logs to detect malicious activity. This hands-on approach provided a deeper understanding of security monitoring and event analysis.

## Tools Used

- **VirtualBox**: Hosted and managed the virtual machines.
- **Windows Server 2022**: Configured as an Active Directory Domain Controller (VM1).
- **Splunk Server**: Used for ingesting and analyzing logs (VM2).
- **Kali Linux**: Used to simulate attacks and test security (VM3).
- **Additional Clean VM**: Included to maintain network integrity for testing purposes (VM4).

## Steps

### Step 1: Setting Up the Virtual Network

The lab consisted of four VMs: a Domain Controller (Windows Server 2022), a Splunk server, a Kali Linux machine, and an additional clean VM for testing. All VMs were configured to communicate within the same NAT network, named "AD-Project."

**Screenshot:** `4-vms-within-the-same-network.png`  
![VMS Network](4-vms-within-the-same-network.png)  
_The VirtualBox network setup showing all four VMs connected within the same NAT network._

---

### Step 2: Configuring Active Directory

Active Directory was set up on the Domain Controller (VM1) with a new domain, `myfir.local`. Organizational units like HR and IT were created, and a test user, `jbenipal`, was added under the HR unit to simulate an employee account.

**Screenshot:** `jagraj-benipal-in-ad.png`  
![AD User Management](jagraj-benipal-in-ad.png)  
_Active Directory Users and Computers showing the user `jbenipal` added under the HR unit._

---

### Step 3: Simulating an RDP Brute-Force Attack

Using the Kali Linux VM (VM3), an RDP brute-force attack was simulated with the `Crowbar` tool against the Domain Controller. The attack successfully compromised the `jbenipal` account, revealing the password `password123`. This demonstrated how attackers exploit weak credentials.

**Screenshot:** `kali-linux-jbenipal-credentials-hacked.png`  
![RDP Attack Simulation](kali-linux-jbenipal-credentials-hacked.png)  
_The successful brute-force attack revealing the `jbenipal` credentials._

---

### Step 4: Analyzing Logs with Splunk

Splunk (VM2) was configured to collect security event logs from the Domain Controller. Queries were run to trace the attack, identifying the compromised `jbenipal` account and its associated logon activity. This exercise highlighted the importance of centralized log monitoring for detecting malicious behavior.

**Screenshot:** `splunk-shows-search-results.png`  
![Splunk Log Analysis](splunk-shows-search-results.png)  
_Splunk search results showing security logs for the compromised `jbenipal` account._

---

## Conclusion

This project involved setting up and managing a multi-VM environment, simulating credential-based attacks, and analyzing logs using Splunk. By combining Active Directory management, attack simulation, and log monitoring, the lab provided valuable insights into detecting and responding to security incidents in a networked environment.
