# HTB Starting Point - Meow  

This machine is a very basic intro and asks fundmental questions about virtualisation, connecting to HTB and enumeration tools. This machine is guided mode only. As always, please attempt this machine yourself before looking at the answers.  
  
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

  You may have heard of Ping before. Use this to check connections are set up properly.  
  `ping <IP Address>`  
  Example:  

  
</details>

---

##### Task 5 - What is the name of the most common tool for finding open ports on a target?  
<details>  
  <summary>Answer</summary>
  
  **nmap**  

  Nmap 'Network Mapper' is very powerful for finding out information with out having anything to go off. It is a Recon tool and can be used as an Enumeration tool as well.
</details>

---
  
Task 6 - What service do we identify on port 23/tcp during our scans?  
<details>  
  <summary> Answer </summary>
In order to find the answer, we must use nmap. Open terminal and input `nmap (IP of Machine)`. For Example, my machines IP is 10.129.1.17 so I would input into terminal `nmap 10.129.1.17`. This will start the scan of the Meow Machines ports with default settings. This should return the following  
  
<img width="570" height="185" alt="image" src="https://github.com/user-attachments/assets/05339c18-739f-4f1e-9a19-5fe01d55cc02" />  
  
So with this, the answer would be: telnet  
</details>  
  
Task 7 - What username is able to log into the target over telnet with a blank password?  
<details>  
  <summary> Answer </summary>
  root  
</details>  

## Grabbing the Flag  
  
To successfully pwn Meow, you will need to use the answers from this as clues to point you in the right direction for the flag. You can do this!  
<details>
  <summary> Answer </summary>  
First we know that using nmap, that port 23/tcp had a telnet service open. This is key here to getting onto the machine and getting the flag.  


</details>





Submit the flag !  
Congratulations!  
  
<img width="520" height="540" alt="image" src="https://github.com/user-attachments/assets/6d03d3ed-4a1e-4b97-93ce-af2d077f4a97" />


