<h1>Creating Azure VMs for Labs</h1>
The objective of this project was to use Microsoft Azure to create 3 different virtual machines for upcoming projects. The first VM with OS Ticket installed, the second VM to act as a domain controller for Active Directory, and finally, a client VM to connect to the domain

<h2>Environments and Technologies Used</h2>

- Microsoft Azure
- Virtual Machine 1 (Client-1)
- Virtual Machine 2 (Domain Controller/DNS Server)
- Virtual Machine 3 (OS Ticket)

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)


<h2>Deployment and Configuration Steps</h2>
 
 Step 1
 
 In Microsoft Azure, I first went to the “resource group” tab and created a resource group. I named it “Lab-AD”. I selected Central US for the region and clicked Create.
<p>
<img width="1040" height="674" alt="image" src="https://github.com/user-attachments/assets/772aa23f-ffa4-4623-9106-6e719b8c48b1" />

</p>
<p>
Step 2
 
 Next i needed to make the virtual network so my domain controller and client vms could be on the same network. I first went to the “Virtual networks”  tab, clicked Create, named the network “VNet-AD”, selected the Lab-AD resource group I just created, selected the same Central US region as my resource group, touched no other settings, and clicked Create.
</p>
<br />

<p>
<img width="1184" height="854" alt="image" src="https://github.com/user-attachments/assets/d8c2cb30-2473-4cb1-ad13-5e958950a8c3" />



</p>
<p>
 
Step-3
 
Now it's time to create the first virtual machine. The first one (client) is a normal VM running Windows 10.

 I went into the Virtual machines tab and then clicked Create. I selected the Lab-AD resource group, selected the Central US region, named it Client-1, selected Windows 10 Enterprise as its image, and selected its size as anything with 2vcpus and atleast 8GB ram.
 
<p>
<img width="861" height="811" alt="image" src="https://github.com/user-attachments/assets/aad11227-ad67-4d46-8ae5-b1086aefca73" />


</p>
<p>

I created a username and password for it, then made sure its selected inbound ports were set to RDP so I could use Remote Desktop to access it

I then went into the network tab, selected the VNet-AD network I created earlier, touched no other settings, and clicked Create



</p>
<br />

<p>
<img width="1082" height="597" alt="image" src="https://github.com/user-attachments/assets/b8bfbccc-f9bd-40ae-a68f-5172cb51d82a" />


</p>
<p>
Step 4
 
Now it's time to create the second virtual machine (domain controller) to use for Active Directory. This VM is using Windows Server 2022.

 I went into the Virtual machines tab and then clicked create. I selected the Lab-AD resource group, selected the Central US region, named it DC-1, selected Windows Server 2022 as its image, and selected its size as anything with 2vcpus and atleast 8GB ram.
<p>
<img width="749" height="787" alt="image" src="https://github.com/user-attachments/assets/f981a825-2f87-4a18-ad49-451d1aa75168" />


</p>
<p>
Just like the last one, I created a username and password for it, then made sure its selected inbound ports were set to RDP so I could use Remote Desktop to access it

I then went into the network tab, selected the same VNet-AD network, touched no other setting, and clicked create.


</p>
<br />

<p>
<img width="1082" height="597" alt="image" src="https://github.com/user-attachments/assets/b8bfbccc-f9bd-40ae-a68f-5172cb51d82a" />

</p>
<p>
Step 5
 
Now I have to set DC-1 as the DNS server for Client 1

To do this is went into the Virtual Machines tab, selected DC-1, scrolled until I identified its public and private IP addresses, and wrote them down. I did the same for Client-1.
<p>
<img width="693" height="305" alt="image" src="https://github.com/user-attachments/assets/b229ab17-f76e-449d-8b74-dcc8c26e9ef1" />

</p>
<p>
 
 I then went into Client-1 and  selected the Network settings tab, then the DNS Server tab, and clicked Custom. In the custom DNS server, I typed the private IP address of DC-1, so Client-1 now recognizes it as its DNS server.

</p>
<br />

<p>
<img width="1516" height="701" alt="image" src="https://github.com/user-attachments/assets/be1971a0-23e2-4e28-ada2-f4158f66090e" />

</p>
<p>
Step 6 
 
Now to create the 3rd and final VM to use for OS Ticket. This one will also be a normal computer running Windows 10 

I first created a new resource group, named it osticket”, and deployed it in East US 


</p>
<br />

<p>
<img width="1341" height="668" alt="image" src="https://github.com/user-attachments/assets/aaac2f56-b7dc-4b38-ad46-89c93380e717" />


</p>
<p>
Step 7. 

For the final step, I went into the Virtual machines tab and then clicked Create. I selected the OSticket resource group, selected the East US region, named it “OSVM”, selected Windows 10 Enterprise as its image, and selected its size as anything with 2vcpus and at least 8 GB RAM.

Just like the first two, I created a username and password for it, then made sure its selected inbound ports were set to RDP so I could use Remote Desktop to access it, touched no other setting, and clicked create.
</p>
<br />

<p>
<img width="803" height="718" alt="image" src="https://github.com/user-attachments/assets/bbb1e5a9-c064-4d57-98a7-4d1d60992140" />


<h2>Conclusion</h2>
Using Microsoft Azure, I now have 3 virtual machines to use for upcoming labs and projects. 2 of them are on the same network/domain to practice Active Directory from a client and an administrative perspective, and one is to install OSTicket and practice using a ticketing system.
