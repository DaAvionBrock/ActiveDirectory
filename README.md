# ActiveDirectory
<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>On-premises Active Directory Deployed in the Cloud (Azure)</h1>
This tutorial outlines the implementation of on-premises Active Directory within Azure Virtual Machines.<br />


<h2>Video Demonstration</h2>


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)

<h2>High-Level Deployment and Configuration Steps</h2>

- Step 1
- Step 2
- Step 3
- Step 4

<h2>Deployment and Configuration Steps</h2>

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Set up the Azure environment:
   - Sign in to the Azure portal at portal.azure.com.
   - Create a new resource group for your virtual network and virtual machines.
   - Create a new virtual network and subnet to host your virtual machines.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Create the Active Directory domain controller virtual machine:
   - Select "Create a resource" from the Azure portal's left-hand menu.
   - Search for "Windows Server" and choose the appropriate version.
   - Configure the virtual machine settings, such as name, resource group, size, and region.
   - Specify the virtual network and subnet you created in step 1.
   - Choose a username and password for the domain controller's administrator account.
   - Configure additional settings like disk type, networking, and management options.
   - Review and create the virtual machine.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Connect to the domain controller virtual machine:
   - Once the virtual machine is created, select it from the Azure portal.
   - Click on "Connect" to download the RDP file.
   - Use the RDP file to connect to the virtual machine using a remote desktop client.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Configure the domain controller:
   - On the domain controller virtual machine, open the Server Manager.
   - Select "Add roles and features" and proceed through the wizard.
   - Choose the "Active Directory Domain Services" role and install it.
   - After installation, promote the server to a domain controller.
   - Specify the desired Active Directory domain name and set the domain controller options.
   - Set the Directory Services Restore Mode (DSRM) password.
   - Complete the wizard and let the server restart.
</p>
<br />

>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Configure DNS:
   - Once the domain controller is promoted, open the Server Manager.
   - Select "Tools" and then open "DNS Manager".
   - Configure the DNS server by creating the appropriate forward and reverse lookup zones for your domain.
   - Verify that the DNS server is functioning correctly.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Join additional virtual machines to the domain:
   - Create additional virtual machines that will be part of the Active Directory domain.
   - Connect to each virtual machine using RDP.
   - Open the System properties, go to the "Computer Name" tab, and click on "Change".
   - Select "Domain" and enter the Active Directory domain name configured in step 4.
   - Provide the credentials of an account with sufficient permissions to join the domain.
   - Restart the virtual machine after joining the domain.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
7. Test the Active Directory environment:
   - Log in to the domain-joined virtual machines using domain user accounts.
   - Verify that the domain users can authenticate successfully.
   - Test Active Directory services like Group Policy, user authentication, and directory access.
</p>
<br />