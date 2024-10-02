# Azure-User-Management

<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1> Preparing active directory infrastructure (Azure)</h1>
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

<h3>Step 3: Create the Domain Controller Virtual Machine (Windows Server 2022) named “DC-1” </h3>
<h4>Click virtual machine</h4>
<img src="https://i.imgur.com/JWxeaKW.png">
<h4>Click create</h4>
<img src="https://i.imgur.com/TqJqYmv.png">
<h4>Name the Domain Controller. Then select the same region as before. For availability options type " No infrastucture redundancy required".Lastly for images click select "Windows Server 2022 Datacenter</h4>
<img src="https://i.imgur.com/bdhTEra.png">
<h4>Scroll down elect a standard size of at least 2 cpu's.Next type in administrator credentials to log on in the future. Make sure RDP is chosen as the inbound port rule.</h4>
<img src="https://i.imgur.com/BMmcBry.png">
<img src"https://i.imgur.com/gwOqLml.png">
<h4>Go to the Networking section and choose the virtual network we created before while also clicking on the subnet created by our virtual network.</h4>
<img src="https://i.imgur.com/KW7tuoX.png">

<h4>Click on review+create , then click create and wait for a successful deployment of our virtual machine.</h4>
<img src="https://i.imgur.com/jOKX3kv.png">
<img src="https://i.imgur.com/Ey9uuAT.png">

<h4>Step 5: Set up Client 1 by simply creating another virtual machine. (All previous steps for our first virtual machine will remain the same. But the virtual machine will be named "Client-1". We will be using Winows 10 Pro and will add new administrator credentials. After all these steps we can simply create the virtual machine as we did previously.</h4>
<h43Name the virtual machine "Client-1" and for images choose "Windows 10 pro"</h3>
<img src="https://i.imgur.com/cA4kOhu.png">
<h4></h4>
<img src="https://i.imgur.com/530it50.png">
<h4></h4>
<img src="https://i.imgur.com/Ih6cSPA.png">

Step 6: <h3>Make the Domain controller Virtual Machine's NIC private IP address to be static (This will allow the IP address not to change)</h3>
<h4>Simply go to virtual setting of the virtual machine</h4>
  <img src="https://i.imgur.com/tT9ANH7.png">
<h4>Click ipconfig1</h4>
  <img src="https://i.imgur.com/6fgDvgC.png">
<h4>Under Private IP address settings change it from Dynamic to Static and click save below.</h4>
  <img src="https://i.imgur.com/mQZyZx9.png">

<h3>Step 7: Log into the Domain controller virtual machine and turn off the firewall.</h3>
<h4> Open up remote desktop connection and enter credentials to log in.</h4>
<img src="https://i.imgur.com/bpBcnxf.png">
<img src="https://i.imgur.com/MTgpU0o.png">
<img src="https://i.imgur.com/rD7Z0oe.png">
<h4>In the virtual machine, right click start click run. To view firewall settings type "wf.msc". In the firewall settings click "Windows Defender Firewall Properties.</h4>
<img src="https://i.imgur.com/mfLydZa.png">
<h4>Once it opens up, for "Domain Profile, Private Profile, Public Profile", click "Firewall State" as off.</h4>
<img src="https://i.imgur.com/Rv44UqO.png">
<img src="https://i.imgur.com/SxC7UaU.png">

<h3>Step 8: Configure DNS settings</h3>
<h4>Go to the Client-1 virtual machine. Then go to network settings and click on Network Interface.</h4>
<img src="https://i.imgur.com/swSFwul.png">
<h4>Click settings and then click DNS. Change DNS server options to custom and type in the domain controllers private IP address 10.0.0.4 Once this is finished click save.</h4>
<img src="https://i.imgur.com/0v62gDY.png">

  <h4>Step 9:Restart Client-1 virtual machine and then log in.</h4>
<img src="https://i.imgur.com/24sj2Gq.png">
<img src="https://i.imgur.com/ateR6tk.png">

<h3>Step 10: Ping to test connectivity between both virtual machines.</h3>
<h4>In powershell simply write "ping 10.0.0.4" the number being the domain controllers private IP address.</h4>
<img src="https://i.imgur.com/YpcSksE.png">

<h2>We can see that we recieve successful replies from the powershell meaning both virtual machines are ready to communicate with each other.</h2>



