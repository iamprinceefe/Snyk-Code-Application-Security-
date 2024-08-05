<h1>Embedding Security in Development (Snyk Code for Application Security)</h1>



<h2>Description</h2>
This project focuses on improving the security of a chat application using Snyk Code. By integrating Snyk into VSCode, vulnerabilities are identified and fixed directly in the source code. The aim is to shift security left, allowing developers to detect and remediate security issues early in the development lifecycle. Training sessions and workshops are part of the rollout to ensure smooth integration and continuous feedback for refinement.
<br />


<h2>Languages and Utilities Used</h2>

- <b>JavaScript</b> 
- <b>Snyk</b>

<h2>Environments Used </h2>

- <b>Windows 10</b> (21H2)
- <b>Visual Studio Code</b> (21H2)
<h2>Program walk-through:</h2>

<p align="center">
Integrate Snyk with GitHub and add project: <br/>
<img src="https://i.imgur.com/YWOBDuH.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<img src="https://i.imgur.com/OdxhBox.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Project:  <br/>
<img src="https://i.imgur.com/sEi9YSM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<img src="https://i.imgur.com/bg1GNhX.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br /
<br />
Clone Project to GitHub Profile: <br/>
<img src="https://i.imgur.com/u1YrEMo.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Project now on Snyk Dashboard:  <br/>
<img src="https://i.imgur.com/SB4mWgA.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Integrate Project on Visual Studio Code to re-scan and fix:  <br/>
<img src="https://i.imgur.com/w6j5BB7.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Scan Project with Snyk on Visual Studio Code:  <br/>
<img src="https://i.imgur.com/M1HwiwM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
View Vulnerabilities based on Severity (SQL Injection):  <br/>
<img src="https://i.imgur.com/F5QJpEI.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
<img src="https://i.imgur.com/j9BLlJa.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Cross-Site Scripting (XXS):  <br/>
<img src="https://i.imgur.com/qJgCaNJ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
<img src="https://i.imgur.com/wABJ1cz.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
<img src="https://i.imgur.com/wBX6u8R.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />

<h2>SQL Injection Remediation</h2>

<p align="center">
To fix the SQL Injection vulnerability in the chat-controller.js file, the developers must modify the code to use parameterised queries. Parameterised queries ensure that user input is treated strictly as data, not as part of the SQL command, and prevent attackers from altering the SQL statement's logic:  <br/>
<img src="https://i.imgur.com/cy0V4ks.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
This updated code uses parameterised queries with the SQLite database. This approach eliminates the vulnerability by ensuring user input cannot interfere with the query structure. The db.all method is called with ? as a placeholder in the SQL query, and the actual input ( searchterm) is passed as an argument in an array. This ensures the SQLite driver safely handles searchterm, which properly escapes any potentially harmful characters.
The search-feature. js file does not need modifications for the SQL injection fix because the vulnerability and its mitigation are handled within the database interaction logic in chat-controller.js.

<h2>Cross-Site Scripting (XXS) Remediation</h2>

<p align="center">
To prevent XSS attacks, you need to properly sanitize or escape any user input before embedding it into the HTML. One way to do this is by using a library that handles HTML escaping, such as he (HTML entities) in Node.js.
<img src="https://i.imgur.com/LJQoOef.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
The he.encode(message) function is used to convert special characters in the user input (message) to their corresponding HTML entities. This prevents any embedded script tags or other malicious HTML content from being executed by the browser.


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
