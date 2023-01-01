<p align="center">
<img src="https://i.imgur.com/AeiqMDZ.png" alt="Traffic Examination"/>
</p>

<h1>Network-File-Shares-and-Permissions</h1>
In this tutorial, we observe various network traffic to and from Azure Virtual Machines with Wireshark as well as experiment with Network Security Groups. <br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Domain Controller/Client Machine)
- Remote Desktop
- Shared Network Files

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

</p>
<p>
In this lab we will be settingup shared network files & permissions. We will create folders in the DC-1 VM and share them on the network certain files will have certain permissions. Only designated people will be able to view certain files. Lets get started. First go to the c:/ drive on the DC-1 machine and create 4 folders. "read-access" "read/write-access" "no-access" and "accounting".
</p>
<br />

<p>
<img src="https://user-images.githubusercontent.com/121250918/210161527-0f9996ec-38a3-4350-92cb-1d2d1a38cafd.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
After the fodlers have been created what you want to do is share them on the network so that the client-1 machine can view them. We can also set the permissions of the folders in DC-1. Set the folders to the appropriate permissions. "read-access" should be read only for domain users, "read/write access" shuld have read/write permissions for domain users. Lastly "no-access" should have read/write permissions for domain admins only.
</p>
<br />

<p>
<img src="https://user-images.githubusercontent.com/121250918/210161527-0f9996ec-38a3-4350-92cb-1d2d1a38cafd.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<img src="https://user-images.githubusercontent.com/121250918/210161529-5a02da90-0e55-4764-a3e9-68c2d116e157.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<p>
If we login to the client machine with a normal user account we can test out the shared files we just created. As you can see the permissions that we set are working properly.
</p>
<br />
<p>
<img src="https://user-images.githubusercontent.com/121250918/210161530-08b74b00-db7b-49f5-a732-3367cb9ae03e.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<img src="https://user-images.githubusercontent.com/121250918/210161533-5e56c86d-c138-492d-807b-b892008ab84d.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<p>
</p>
Go back to the DC-1 VM. In AD create a security group called "Accountants" the users assigned to this security group will be the only ones allowed to view the "Accountants" folder. We have to share the "Accountants" folder just like we did in the last section, this we will be sharing it to only the accountants group. Normal users will not have access to this folder. If we wanted to give a normal user access to the accounting folder they would have to be a part of the "Accountants" security group.
</p>
<br />
<p>
<img src="https://user-images.githubusercontent.com/121250918/210161535-8859b1d6-d9a8-46ff-b429-4200a8a0005e.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<img src="https://user-images.githubusercontent.com/121250918/210161537-59122a7d-327a-48f4-a260-97fc9feae9f1.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<img src="https://user-images.githubusercontent.com/121250918/210161541-fa0a87fe-e63a-4b74-8815-55f0f2f86a4d.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
