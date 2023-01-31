<h1> Local DNS Attack Lab</h1>

<h2>Setting Up a Local DNS Server</h2>
 <h4>IP Address </h4>
 
- <b>User Machine:10.0.2.4</b> 
- <b>DNS Server : 10.0.2.7(Ip address changed on last tasks to 10.0.2.10)</b>
- <b>Attacker Machine:10.0.2.8</b>
<br />

![Picture1](https://user-images.githubusercontent.com/99901204/215654584-3fa12d25-718f-48db-8599-7369ce5a97f3.png)


<h2>Task 1: Configure the User Machine</h2>

- <b>sudo gedit /etc/resolv.conf</b> 
![image](https://user-images.githubusercontent.com/99901204/215654748-f9792523-0808-4450-88bf-78675fbda025.png)

 <h5>running the above command on user machine. Change the Ip address of nameserver to the IP address of the server machine we are using as a Local DNS server. nameserver 10.0.2.10</h5>

<h2>Task 2: Setting up a Local DNS Server </h2>

![image](https://user-images.githubusercontent.com/99901204/215654824-eeef8544-7426-45dc-98d1-b6da90a500d8.png)

- <b>Turning off DNSSEC </b> 
![image](https://user-images.githubusercontent.com/99901204/215654968-55f5edf3-9942-470c-8fed-c66c00a2a067.png)

<h5>To show how attacks work without protection mechanism, we need to turn the protection off. This is done by modifying the "named.conf. options" file: comment out the "dnssec-validation entry " and add a dnssec-enable entry </h5>
- <b>  Using Command: sudo gedit /etc/bind/named.conf.options </b> 

![image](https://user-images.githubusercontent.com/99901204/215655029-e6741bfb-f39d-4f1b-99b0-d8d9ab6d460d.png)

<h2>Starting DNS Server:</h2>


![image](https://user-images.githubusercontent.com/99901204/215656256-826608fe-4def-4c57-bc6c-c14d62f4ee43.png)


<h4> Every time a modification is made to the DNS configuration, the DNS server needs to be restarted </h4>
- <b>  Using Command: sudo service Bind9 restart </b> 
<h2>Creating Zones: </h2>
<h4> To create zone, we added those content to “  /etc/bind/named.conf ” </h4>

![image](https://user-images.githubusercontent.com/99901204/215655484-09125f72-dd76-426b-984b-a14750731ff4.png)

![image](https://user-images.githubusercontent.com/99901204/215655495-2d326b57-0a6d-4240-a617-f6aace9e0e46.png)
<h4> Set up the reverse lookup </h4>

![image](https://user-images.githubusercontent.com/99901204/215655634-09d14a97-f99d-4903-86f0-363dc8e53803.png)
<h4>Setup the forward lookup zone file </h4>

![image](https://user-images.githubusercontent.com/99901204/215655695-913eaf4b-ae5f-4182-be9d-0c360ff3cff5.png)

<h1>Lab Tasks (Part II): Attacks on DNS</h1>

<h2>Task 4 Modifying the host file</h2>

<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
