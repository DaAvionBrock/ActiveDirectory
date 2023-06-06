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
<div>
  <h3>Set up the Azure environment:</h3>
  <ol>
    <li>Sign in to the Azure portal at <a href="https://portal.azure.com">portal.azure.com</a>.</li>
    <li>Create a new resource group for your virtual network and virtual machines.</li>
    <li>Create a new virtual network and subnet to host your virtual machines.</li>
  </ol>
</div>
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<div>
  <h3>Create the Active Directory domain controller virtual machine:</h3>
  <ol>
    <li>Select "Create a resource" from the Azure portal's left-hand menu.</li>
    <li>Search for "Windows Server" and choose the appropriate version.</li>
    <li>Configure the virtual machine settings, such as name, resource group, size, and region.</li>
    <li>Specify the virtual network and subnet you created in step 1.</li>
    <li>Choose a username and password for the domain controller's administrator account.</li>
    <li>Configure additional settings like disk type, networking, and management options.</li>
    <li>Review and create the virtual machine.</li>
  </ol>
</div>
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<div>
  <h3>Connect to the domain controller virtual machine:</h3>
  <ol>
    <li>Once the virtual machine is created, select it from the Azure portal.</li>
    <li>Click on "Connect" to download the RDP file.</li>
    <li>Use the RDP file to connect to the virtual machine using a remote desktop client.</li>
  </ol>
</div>
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<div>
  <h3>Configure the domain controller:</h3>
  <ol>
    <li>On the domain controller virtual machine, open the Server Manager.</li>
    <li>Select "Add roles and features" and proceed through the wizard.</li>
    <li>Choose the "Active Directory Domain Services" role and install it.</li>
    <li>After installation, promote the server to a domain controller.</li>
    <li>Specify the desired Active Directory domain name and set the domain controller options.</li>
    <li>Set the Directory Services Restore Mode (DSRM) password.</li>
    <li>Complete the wizard and let the server restart.</li>
  </ol>
</div>
</p>
<br />

>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<div>
  <h3>Create an Admin & Normal User Account in AD: <h3/>
<ol>
  <li>In Active Directory Users and Computers (ADUC), create an Organizational Unit (OU) called "_EMPLOYEES"</li>
  <li>Create a new OU named "_ADMINS"</li>
  <li>Create a new employee named "Jane Doe" (same password) with the username of "jane_admin"</li>
  <li>Add jane_admin to the "Domain Admins" Security Group</li>
  <li>Log out/close the Remote Desktop connection to DC-1 and log back in as "mydomain.com\jane_admin"</li>
  <li>Use jane_admin as your admin account from now on</li>
</ol>
</div>
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<div>
  <h3>Join additional virtual machines to the domain:</h3>
  <ol>
    <li>Create additional virtual machines that will be part of the Active Directory domain.</li>
    <li>Connect to each virtual machine using RDP.</li>
    <li>Open the System properties, go to the "Computer Name" tab, and click on "Change".</li>
    <li>Select "Domain" and enter the Active Directory domain name configured in step 4.</li>
    <li>Provide the credentials of an account with sufficient permissions to join the domain.</li>
    <li>Restart the virtual machine after joining the domain.</li>
  </ol>
</div>
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<div>
  <h3>Test the Active Directory environment:</h3>
  <ol>
    <li>Log in to the domain-joined virtual machines using domain user accounts.</li>
    <li>Verify that the domain users can authenticate successfully.</li>
    <li>Test Active Directory services like Group Policy, user authentication, and directory access.</li>
  </ol>
</div>
</p>
<br />