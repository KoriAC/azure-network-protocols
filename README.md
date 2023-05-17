<p align="center">
<img src="https://i.imgur.com/Ua7udoS.png" alt="Traffic Examination"/>
</p>

<h1>Network Security Groups (NSGs) and Inspecting Traffic Between Azure Virtual Machines</h1>
In this tutorial, we observe various network traffic to and from Azure Virtual Machines with Wireshark as well as experiment with Network Security Groups. <br />



<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Various Command-Line Tools
- Network Protocols (SSH,DNS & ICMP)
- Wireshark (Protocol Analyzer)

<h2>Operating Systems Used </h2>

- Windows 10 (21H2)
- Ubuntu Server 20.04

<h2>High-Level Steps</h2>

- Creating Resource Group
- Creating Virtual Machines
- Remote Desktop Connection
- Dowmload Wireshark
- Observe traffic using various protocols

<h2>Actions and Observations</h2>

<p>
<img src="https://i.gyazo.com/c9a5d6ebe7cf0a2828380a82a58ff770.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Here we're going to create a resource group in Microsoft Azure.
</p>
<br />

<p>
<img src="https://i.gyazo.com/896b1a6f2dacaa330d3a76417fb8ade1.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
The resource group has been succesfully created.
</p>
<br />

<p>
<img src="https://i.gyazo.com/9d1cd42e0907d15232160a66a9ef04fb.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Now we will create two virtual machines named "VM1" and "VM2" respectively.
</p>
<br />

<p>
<img src="https://i.gyazo.com/db6d58c9a308bd60db90aaab32a35fe1.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Both of the virtual machines will be added to the resource group that was previously created.
</p>
<br />

<p>
<img src="https://i.gyazo.com/36be391eb4c947d617e14c8dafc5bbf8.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
A username and password are being created for VM1 and these credentials will be used to access the virtual machine via remote desktop connection. In addtion, we will be using a windows operating system for VM1.
</p>
<br />

<p>
<img src="https://i.gyazo.com/c05e7aef428d0b02fda9d6da1e138e4a.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
The same process will be done for VM2. The operating system that VM2 will utilize is Ubuntu Server 20.04.
</p>
<br />

<p>
<img src="https://i.gyazo.com/90cad006d556875112b661d5875e3d01.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Just like VM1, a username and password will be created for VM2.
</p>
<br />

<p>
<img src="https://i.gyazo.com/73b1674c744ecbcda7bdeb29f3a45e9c.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Both virtual machines have been successfully created.
</p>
<br />

<p>
<img src="https://i.gyazo.com/28790d60404fcb0268bc366682f69c42.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
We will access VM1 through the Azure portal. From there, the public IP address will be copied and pasted into remote desktop connection.
</p>
<br />

<p>
<img src="https://i.gyazo.com/2b2a0410a7b100e70483dac289230799.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Enter the credentials that were previously created for VM1.
</p>
<br />

<p>
<img src="https://i.gyazo.com/76795896285026f57242851387bbe945.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
The login for VM1 has been successful.
</p>
<br />

<p>
<img src="https://i.gyazo.com/f2ac33808dbc3df3af1e1a8b3edaf500.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Open any browser within VM1 and download Wireshark.
</p>
<br />

<p>
<img src="https://i.gyazo.com/add50421c6f640cada4738b58520a0c3.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
To start the installation process, simply click "Next".
</p>
<br />

<p>
<img src="https://i.gyazo.com/e38f8fb457aaa75c97d8d11bad1f3b77.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Click "Install"
</p>
<br />

<p>
<img src="https://i.gyazo.com/a7cfff4da7a1140db9bf0bb4dd3fc8c1.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Simply click "Install".
</p>
<br />

<p>
<img src="https://i.gyazo.com/59c0258660ad9445b79eb82bba6a3c8e.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Click "Finish".
</p>
<br />

<p>
<img src="https://i.gyazo.com/d390682dad81ee56752667595008f681.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Click "Finish".
</p>
<br />

<p>
<img src="https://i.gyazo.com/dcf8200f6d35a5914f23689ba3567509.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
As you can see, Wireshark is open and we will be filtering for protocol ICMP (Internet Control Message Protocol).
</p>
<br />

<p>
<img src="https://i.gyazo.com/65a735ac1a7b8ebc05f8fc594918c1f8.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
The above image shows no packets are being captured.
</p>
<br />

<p>
<img src="https://i.gyazo.com/75c0c12f420d88fe8c25124bd847818c.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
We will go back into the Azure portal and access the overview of VM2. The private IP address of VM2 will be copied.
</p>
<br />

<p>
<img src="https://i.gyazo.com/cb84e8571a390ea32584468c595c8e8f.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.gyazo.com/cb84e8571a390ea32584468c595c8e8f.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Open Microsoft PowerShell and perpetually ping VM2. This is achieved by typing "ping -t 10.0.0.5.
</p>
<br />

<p>
<img src="https://i.gyazo.com/76a06aa3701f705f23ab61a5beafef93.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
As you can see, we are getting continuous responses from 10.0.0.5.
</p>
<br />

<p>
<img src="https://i.gyazo.com/6514b12ee54866878572eda44b2025aa.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
When we go back to Wireshark, we can see constant replies and requests from both virtual machines.
</p>
<br />

<p>
<img src="https://i.gyazo.com/49a1800ce6ffacce222bdd1317f85b45.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
To stop the perpetual pings from VM1, we will go back to the Azure portal and select Network Security Groups.
</p>
<br />

<p>
<img src="https://i.gyazo.com/18ac136c8309f71496c75825d6c45f29.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Select VM2
</p>
<br />

<p>
<img src="https://i.gyazo.com/c916d10b5b6227a14b707959ec8e77bf.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Select “Inbound security rules” and click “Add”. We will select the ICMP protocol and choose Deny. We can see the priority for SSH is 300. Therefore, we will set the priority to 200. This will make the process quicker.
</p>
<br />

<p>
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />
