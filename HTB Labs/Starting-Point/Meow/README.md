# HTB Starting Point - Meow  

This machine is very basic and asks fundmental questions about virtualisation, connecting to HTB and a specific reconnaissance/enumeration tool. This machine is guided mode only. As always, please attempt this machine yourself before looking at the answers.  
  
Quick note about the tasks for this machine. These are very foundational questions, most of these you should be able to answer. If you are new to Cybersecurity, Task 5, 6 and 7 you may need some help with.

## Walkthrough  
##### Task 1 - What does the acronym VM stand for?
<details>
  <summary>Answer</summary>
  
  **Virtual Machine** <br>
  <br>
  You should be using a virtual machine every time you perform hacking activites. This way you will be protecting your own machine in case a mistake occurs. <br>
  
</details>

---

##### Task 2 - What tool do we use to interact with the operating system in order to issue commands via the command line, such as the one to start our VPN connection? It's also known as a console or shell.  
<details>  
  <summary>Answer</summary>
  
  **terminal**<br>
  <br>
  This is your new home. Getting familiar with the terminal is essential because you will **ALWAYS** be using the terminal. Command Line is very powerful if you know what you are doing.
  
</details>

---

##### Task 3 - What service do we use to form our VPN connection into HTB labs?
<details>  
  <summary>Answer</summary>
  
  **openvpn**  

  OpenVPN is how you will always connect to the HTB Labs. If you are unsure how to connect, refer to Setting-Up
</details>

---

##### Task 4 - What tool do we use to test our connection to the target with an ICMP echo request?
<details>  
  <summary> Answer </summary>
  
  **ping**  

  Use ping to check connections are set up properly. It sends packets to the IP Address you specify and receives them back to confirm connections.  
  `ping <IP Address>`  
  Example:  
![ping-example-ezgif com-crop](https://github.com/user-attachments/assets/98668dff-ae37-43e2-b585-8315ca676d00)

  
</details>

---

##### Task 5 - What is the name of the most common tool for finding open ports on a target?  
<details>  
  <summary>Answer</summary>
  
  **nmap**  

  Nmap 'Network Mapper' is very powerful for finding out information with out having anything to go off. It is a Recon tool and can be used as an Enumeration tool as well.
</details>

---
  
##### Task 6 - What service do we identify on port 23/tcp during our scans?  
<details>  
  <summary>Answer</summary>

  
  In order to find the answer, we must use nmap. Open terminal and input `nmap <Target IP>`. For Example, the Meow Machine IP that was given to me was 10.129.1.17, so I would input into terminal `nmap 10.129.1.17`. This will start the scan of the Meow Machines ports with default settings. This should return the following  
  
<img width="570" height="185" alt="image" src="https://github.com/user-attachments/assets/05339c18-739f-4f1e-9a19-5fe01d55cc02" />  
  
So with this, the answer would be: **telnet**
</details>

---

##### Task 7 - What username is able to log into the target over telnet with a blank password?
<details>  
  <summary>Answer</summary>
  
  **root**  

  The hint for this task gives it away, but if you haven't used Linux at all this one might stump you. Think of Root as God, Root can do anything and it will allow you to do anything so long as you ask kindly with "sudo".
</details>

---

## Grabbing the Flag  
  
To successfully pwn Meow, you will need to use the answers from the tasks as clues to point you in the right direction for the flag. You can do this!  
<details>
  <summary>Solution</summary>

We know from using nmap that port 23/tcp had a telnet service open. This is key here to getting onto the machine and getting the flag. We can use the `telnet` tool in order to proceed here, which allows us interaction with another host (Machine) via the TELNET protocol. We also know based on Task 7, that we can access the machine via telnet with the user "root". If we were going to use telnet we need to do two things, 1 - give it the target IP and 2 - specify which user we are logging in with. When we go to execute this command it should look like this: `telnet <Target IP> -l <user>`. -l (L) is used to specify the user. So in this case, we execute `telnet 10.129.1.17 -l root`. This takes a moment to connect but should return with:  

<img width="608" height="668" alt="image" src="https://github.com/user-attachments/assets/99cb0499-dcd5-4c27-ae4a-d5732852591c" /> <br>
Awesome! We are now able to interact with this machine. We are trying to find the flag file, which contains the string of text needed to pwn Meow. From here, we use the `ls` (LS) command to list what is in our current directory.  

<img width="162" height="65" alt="image" src="https://github.com/user-attachments/assets/7c715f2c-21c0-462f-b025-43f2ff3c7c3c" /> <br>
We have found the file. Now all we need to do is extract the data, which we can do via the `cat` command.  

BOOM, you have PWNED Meow. Congratulations!

</details>





Submit the flag!  
Congratulations!  
  
<img width="520" height="540" alt="image" src="https://github.com/user-attachments/assets/6d03d3ed-4a1e-4b97-93ce-af2d077f4a97" />


