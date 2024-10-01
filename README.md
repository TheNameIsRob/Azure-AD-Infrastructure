# Azure-User-Management

<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1> Preparing and deploying active directory infrastructure (Azure)</h1>
This tutorial outlines how active directory is configured for administrative use.<br />



<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)

<h2>High-Level Deployment and Configuration Steps</h2>

- Creating a virtual network and subnet
- Create domain controller
- Set up an Azure client
- Install Active Directory
  

<h2>Deployment and Configuration Steps</h2>

<h3>Step 1: Locate Azure services and create a resource group.</h3>
<h4>Click resource group -> </h4>
<img src="https://i.imgur.com/oNppYcQ.png" height="80%" width="80%" alt="Resource Group PT 1"/>
<h4>Click create -></h4>
<img src="https://i.imgur.com/U50o3vR.png" height="80%" width="80%" alt="Resource group PT 2"/>
<h4>Choose (US) East US 2 as region (more of our resources will be in the same region when created later on) </h4>
<img src="https://i.imgur.com/xil38OA.png" height="80%" width="80%" alt="Resource group PT 3"/>
<h4>Click create to finish creating resource group</h4>
<img src="https://i.imgur.com/F6yf0Ch.png">
<p></p>


<h3>Step 2: Create virtual network and subnet</h3>
<h4>Click virtual networks</h4>
<img src="https://i.imgur.com/GRXoD6Y.png">
<h4>Click create</h4>
<img src="https://i.imgur.com/wSn12Wh.png">
<h4>Name the the virtual network and select the same region we've chosen prior.</h4>
<img src="https://i.imgur.com/eI7uGMt.png">
<h4>Click create and wait till the virtual network has been deployed. Once it's finished you should get a successful deployment.</h4>
<img src="https://i.imgur.com/DuGPwvn.png">
<img src="https://i.imgur.com/bOr1LVC.png">

<h4></h4>

<h4></h4>
</p>

<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />
