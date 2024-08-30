<h1>Digital Forensics with Autopsy Lab</h1>



<h2>Description</h2> 
Text

<br />


<h2>Utilities Used</h2>

- <b>Autopsy</b>

<h2>Environments Used </h2>

- <b>Windows 10 Virtual Machine</b>

<h2>Lab Overview</h2>

The first question and rightfully so as with forensics, it is esential to know you are examing the correct image and it has not been tampered with. So I found the hash of the image by going to data sources, clicking on the disk and under file metadata it shows the hash. <br/>
<img src="https://github.com/user-attachments/assets/adc26d8b-afb9-465d-a6ea-341d6bcdda9c" height="100%" width="100%" alt="Autopsy Lab"/>
<br />
<br />
Now begins putting the pieces togethers and the questions move through important artifacts and data found on the computer such as finding the non-default users and when they last logged in which was the user sivapriya. <br/>
<img src="https://github.com/user-attachments/assets/b842803a-d8bb-4de2-8f6e-c99f610968c2" height="100%" width="100%" alt="Autopsy Lab"/>
<br />
<br />
Next question and important evidence to find is the MAC address any configured network IP address on the computer so it can corroborate with other evidence of network traffic. <br/>
<img src="https://github.com/user-attachments/assets/c0684475-a780-48f5-96a7-97d7f8562e1e" height="100%" width="100%" alt="Autopsy Lab"/>
<br />
<br />
The next question asked for the network card information for the computer which I did not know where that was so I used the keyword search with a regular expression (a long shot because it could be called ethernet or ETH or something like that) the keyword search is great for finding specific strings on the file system if you know what they are or think you know what they are. (if you have the patience or have no other lead becasue they take away depending on the CPU)<br/>
<img src="https://github.com/user-attachments/assets/a72e8f70-e1c6-4aad-ad75-4947e8d2fc38" height="100%" width="100%" alt="Autopsy Lab"/>
<img src="https://github.com/user-attachments/assets/49a466f2-cc24-41d1-a5e3-6759c62b2e81" height="100%" width="100%" alt="Autopsy Lab"/>
<br />
<br />
The next questions and flags now begin having us find specific artifacts on the computer to test out ability to use autopsy and navagate the file system. The next question was to find teh cooridantes of the bookmarked google maps address. Knowing there is a place directory in autopsy that saves bookmarked web pages this was an easy find.<br/>
<img src="https://github.com/user-attachments/assets/cb4e5157-ed5b-465c-b037-0ded0a5c69a0" height="100%" width="100%" alt="Autopsy Lab"/>
<br />
<br />
The next question was that a user has his full name printed on his desktop wallpaper and to find which user has it. My first thoughts that the user must have downloaded it so I went throuhg the users downlaods with the images/videos tab in autopsy which should folders that have images and videos to help narrow down the search and I found that joshwa had it<br/>
<img src="https://github.com/user-attachments/assets/a0732bf5-87b8-4d2d-a417-65176cd1f25d" height="100%" width="100%" alt="Autopsy Lab"/>
<br />
<br />
Now began the capture the flag part of the lab, and the question for the first flag was that a user had a file on her desktop. It had a flag but she changed the flag using PowerShell, what was the first flag? I did not know where to start here and after some research it revealed the file path for the command history. Instead of having to go down each user's file tree to find this, I used the file itself in the keyword search to bring them all up at once for effiecncy. <br/>
<img src="https://github.com/user-attachments/assets/4be3ed56-15e3-4968-942e-43afec986faa" height="100%" width="100%" alt="Autopsy Lab"/>
<img src="https://github.com/user-attachments/assets/5da2db9a-053f-443f-9d9d-d3bbb0de1134" height="100%" width="100%" alt="Autopsy Lab"/>
<br />
<br />
The question for the next flag was that the same user found an exploit to escalate privileges on the computer, what was the message to the device owner? So we the start of the question was a great hint, since wer know that iwas sherya, I decided to investigate her account user account further and found exploit.ps1 on the desktop which has the flag along with what appears to be a script for priv escalation d<br/>
<img src="https://github.com/user-attachments/assets/e2608e7a-428d-4151-b0af-df440deb02fd" height="100%" width="100%" alt="Autopsy Lab"/>
<br />
<br />
The lab switched back to questions and the following question was thattwo hack tools focused on passwords were found in the system. What are the names of these tools? Considering they are hacking tools surely windwos defender would have logged or detected them or were in serioius trouble and luckly in the detection history, the profilic password dumper mimikatz was detected and lazagme <br/>
<img src="https://github.com/user-attachments/assets/e5567f22-6d9b-49ef-a61c-ff59c49b4ec2" height="100%" width="100%" alt="Autopsy Lab"/>
<img src="https://github.com/user-attachments/assets/66892d91-9dd7-41bb-9d63-dc8acd964cdd" height="100%" width="100%" alt="Autopsy Lab"/>
<img src="https://github.com/user-attachments/assets/5ac8c5f8-fc2a-422f-bd9d-4aaa2778d4a9" height="100%" width="100%" alt="Autopsy Lab"/>
<br />
<br />
Down to the second to last question of the lab which was, there is a YARA file on the computer, inspect the file. What is the name of the author? <br />
<img src="https://github.com/user-attachments/assets/4d17d9dd-00e3-4fcc-932d-dea48622a644" height="100%" width="100%" alt="Autopsy Lab"/>
<img src="https://github.com/user-attachments/assets/4189da9b-4ef7-4a0f-90e8-ca89cc1ea2a1" height="100%" width="100%" alt="Autopsy Lab"/>
<br />
<br />
The final question of the lab explains how the privilege escalation technique that was used, one of the users wanted to exploit a domain controller with an MS-NRPC based exploit. What is the filename of the archive that you found? The first thing to do is research was an MS-NPRC exploit is and I discovered it to be tightly related to ZeroLogon. As a shot in the dark, I used keyword searches for both MS-NPRC in autopsy and got a match with ZeroLogon as the user sandhya just downloaded the exploit with its name which included the version making this an easy last question.<br/>
<img src="" height="100%" width="100%" alt="Autopsy Lab"/>
<br />
<br />



<h2>Thoughts</h2>
Text
