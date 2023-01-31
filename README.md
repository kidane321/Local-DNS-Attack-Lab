<h1> Local DNS Attack Lab</h1>

<h2>Setting Up a Local DNS Server</h2>
 <h4>IP Address </h4>
 
- <b>User Machine:10.0.2.4</b> 
- <b>DNS Server : 10.0.2.7(Ip address changed on last tasks to 10.0.2.10)</b>
- <b>Attacker Machine:10.0.2.8</b>
<br />
![Picture1](https://user-images.githubusercontent.com/99901204/215654126-e248569f-6ea7-4408-a992-ad83303b9183.png)


<h2>Task 1: Configure the User Machine</h2>

- <b>sudo gedit /etc/resolv.conf</b> 
 <h5>running the above command on user machine. Change the Ip address of nameserver to the IP address of the server machine we are using as a Local DNS server. nameserver 10.0.2.10</h5>

<h2>Task 2: Setting up a Local DNS Server </h2>
<h5>To show how attacks work without protection mechanism, we need to turn the protection off. This is done by modifying the "named.conf. options" file: comment out the "dnssec-validation entry " and add a dnssec-enable entry </h5>
- <b>  Using Command: sudo gedit /etc/bind/named.conf.options </b> 

<h2>Starting DNS Server:</h2>
<h4> Every time a modification is made to the DNS configuration, the DNS server needs to be restarted </h4>
- <b>  Using Command: sudo service Bind9 restart </b> 
<p align="center">
Launch the utility: <br/>
<img src="https://i.imgur.com/62TgaWL.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Select the disk:  <br/>
<img src="https://i.imgur.com/tcTyMUE.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Enter the number of passes: <br/>
<img src="https://imgur.com/PoG6LOZ" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Confirm your selection:  <br/>
<img src="https://i.imgur.com/cdFHBiU.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Wait for process to complete (may take some time):  <br/>
<img src="https://i.imgur.com/JL945Ga.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Sanitization complete:  <br/>
<img src="https://i.imgur.com/K71yaM2.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Observe the wiped disk:  <br/>
<img src="https://i.imgur.com/AeZkvFQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
