
<img src="https://i.imgur.com/Ua7udoS.png" alt="Traffic Examination"/>
</p>

<h1>Network Security Groups (NSGs) and Inspecting Traffic Between Azure Virtual Machines</h1>
In this tutorial, we observe various network traffic to and from Azure Virtual Machines with Wireshark as well as experiment with Network Security Groups. <br />



<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Various Command-Line Tools
- Various Network Protocols (SSH, RDH, DNS, HTTP/S, ICMP)
- Wireshark (Protocol Analyzer)

<h2>Operating Systems Used </h2>

- Windows 10 (21H2)
- Ubuntu Server 20.04

<h2>High-Level Steps</h2>

- Create 2 virtual machines on Azure
- Login to both virtual machines using remote desktop
- Download wireshark on one of the virtual machines
- Use wireshark to observe the traffic between the 2 virtual machines

<h2>Actions and Observations</h2>

<p>
<img src="https://i.imgur.com/LDh40nq.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
The image above depicts two virtual machines created in Azure. These virtual machines were placed on the same virtual network and the same virtual subnet.
</p>
<br />

<p>
<img src="https://i.imgur.com/1NJ6rpa.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
The image above shows us observing the traffic between both virutal machines using wireshark and the command line. On the command line, if you run the command ping (IP address) -t from inside VM-1 (virutal machine 1), you will get a reply from VM-2 because they are on the same virtual network. The next step is to stop ICMP traffic coming from VM-1 into VM-2 and observe the traffic on wireshark. If you run ping (IP address) -t, this command will continuously run.
</p>
<br />

<p>
<img src="https://i.imgur.com/ds0epJW.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
The image aboce is a setting in Azure where we can set and modify inbound rules. This setting denies ICMP traffic from one virtual machine to the other. After you add this setting, you receive a notification on the command line that your request timed out.
</p>
<br />
