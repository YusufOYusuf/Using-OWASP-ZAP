<h1>Using OWASP ZAP</h1>


<h2>Description</h2>
In this lab, I learned to use OWASP ZAP. OWASP (open web application security project) ZAP (Zed attack proxy) is a penetration testing tool that is used for finding vulnerabilities in various web applications.
<br />



<h2>Environments Used </h2>

- <b>Kali GNU/Linux Rolling</b> 

<h2>Program walk-through:</h2>

<p align="center">
From the left sidebar click Firefox ESR and in the address bar type in "192.168.122.121/dvwa: <br/>
<img src="https://i.postimg.cc/XvKxRBp0/Screen-Shot-2022-08-30-at-6-15-53-PM.png" height="80%" width="80%" alt="Configuring Advanced Ethernet Options Steps"/>
<br />
  
  
  
<br />
In the DVWA (Damn Vulnerable Web App) login page type in the username and password  <br/>
<img src="https://i.postimg.cc/PqKYbWCN/Screen-Shot-2022-08-30-at-6-17-22-PM.png" height="80%" width="80%" alt="Configuring Advanced Ethernet Options Steps"/>
<br />
  
  
  
  
<br />
In the left pane of the DVWA webpage click DVWA Security <br/>
<img src="https://i.postimg.cc/bY0gdtTD/Screen-Shot-2022-08-30-at-6-21-15-PM.png" height="80%" width="80%" alt="Configuring Advanced Ethernet Options Steps"/>
<br />




<br />
In Script Security select "low" then click submit <br/>
<img src="https://i.postimg.cc/3RDZ7L8V/Screen-Shot-2022-08-30-at-6-26-44-PM.png" height="80%" width="80%" alt="Configuring Advanced Ethernet Options Steps"/>
<br />




<br />
In the left pane select "Brute Force".  <br/>
<img src="https://i.postimg.cc/4d9V9mhS/Screen-Shot-2022-08-30-at-6-29-24-PM.png" height="80%" width="80%" alt="Configuring Advanced Ethernet Options Steps"/>
<br />





<br />
In the browser window  go to the top right corner and select the menu icon then navigate to preferences.  <br/>
<img src="https://i.postimg.cc/1RY0j1yB/Screen-Shot-2022-08-30-at-6-32-44-PM.png" height="80%" width="80%" alt="Configuring Advanced Ethernet Options Steps"/>
<br />




<br />
In the preference window navigate to "Network" using the search bar and then hit the settings button.  <br/>
<img src="https://i.postimg.cc/qvZX9fc4/Screen-Shot-2022-08-30-at-6-36-18-PM.png" height="80%" width="80%" alt="Configuring Advanced Ethernet Options Steps"/>
<br />




<br />
In the Connection settings window select manual proxy labeling it "localhost" with a port of 8080, and select "also use this proxy for FTP and HTTPS" checkbox then click ok.  <br/>
<img src="https://i.postimg.cc/HnXTCC8K/Screen-Shot-2022-08-30-at-6-37-43-PM.png" height="80%" width="80%" alt="Configuring Advanced Ethernet Options Steps"/>
<br />






<br />
From the top task bar select "Applications" and then proceed to 03-Web Application Analysis, and then click ZAP  <br/>
<img src="https://i.postimg.cc/SQv9SL2f/Screen-Shot-2022-08-30-at-6-41-17-PM.png" height="80%" width="80%" alt="Configuring Advanced Ethernet Options Steps"/>
<br />




<br />
In the OWASP ZAP prompt select no then click start.  <br/>
<img src="https://i.postimg.cc/HLkXzTrT/Screen-Shot-2022-08-30-at-6-43-50-PM.png" height="80%" width="80%" alt="Configuring Advanced Ethernet Options Steps"/>
<br />




<br />
Return to the DVWA brute force page and type in username and password (you will observe a username/password incorrect message).  <br/>
<img src="https://i.postimg.cc/CMG5RWK7/Screen-Shot-2022-08-30-at-6-47-12-PM.png" height="80%" width="80%" alt="Configuring Advanced Ethernet Options Steps"/>
<br />




<br />
At the warning page select "Advanced".  <br/>
<img src="https://i.postimg.cc/jjfKG7wc/Screen-Shot-2022-08-30-at-6-48-25-PM.png" height="80%" width="80%" alt="Configuring Advanced Ethernet Options Steps"/>
<br />






<br />
Scroll down and select "Accept the risk and continue".  <br/>
<img src="https://i.postimg.cc/rFYksJ5g/Screen-Shot-2022-08-30-at-6-50-04-PM.png" height="80%" width="80%" alt="Configuring Advanced Ethernet Options Steps"/>
<br />





<br />
In the left pane under Sites tab navigate to Sites>http://198.168.122.121>dvwa>vulnerabilities>brute. Then right click Get...>attack>fuzz  <br/>
<img src="https://i.postimg.cc/q7WYHDV6/Screen-Shot-2022-08-30-at-6-55-16-PM.png" height="80%" width="80%" alt="Configuring Advanced Ethernet Options Steps"/>
<br />




<br />
In the fuzz locations window look for username=admin&password=test. Select test by highlighting it and then click add   <br/>
<img src="https://i.postimg.cc/dVg1gv12/Screen-Shot-2022-08-30-at-7-00-00-PM.png" height="80%" width="80%" alt="Configuring Advanced Ethernet Options Steps"/>
<br />




<br />
In the payloads window click add   <br/>
<img src="https://i.postimg.cc/SN2b39zP/Screen-Shot-2022-08-30-at-7-02-36-PM.png" height="80%" width="80%" alt="Configuring Advanced Ethernet Options Steps"/>
<br />





<br />
In the add payload window select type as "file" and then click select <br/>
<img src="https://i.postimg.cc/qvJS0Ct0/Screen-Shot-2022-08-30-at-7-04-58-PM.png" height="80%" width="80%" alt="Configuring Advanced Ethernet Options Steps"/>
<br />




<br />
In the open dialog box double click Documents and click fuzz_crack.txt. Then click open then add. Then in the payloads window click ok <br/>
<img src="https://i.postimg.cc/NMD23VZQ/Screen-Shot-2022-08-30-at-7-08-48-PM.png" height="80%" width="80%" alt="Configuring Advanced Ethernet Options Steps"/>
<br />





<br />
In the Fuzzer window click start fuzzer <br/>
<img src="https://i.postimg.cc/tTJ9gMYq/Screen-Shot-2022-08-30-at-7-10-41-PM.png" height="80%" width="80%" alt="Configuring Advanced Ethernet Options Steps"/>
<br />






<br />
In the OWASP ZAP - OWASP ZAP 2.10.0 window in the bottom pane under payloads right click password>save raw> request> header <br/>
<img src="https://i.postimg.cc/sg6tf9Zy/Screen-Shot-2022-08-30-at-7-19-49-PM.png" height="80%" width="80%" alt="Configuring Advanced Ethernet Options Steps"/>
<br />





<br />
In the save dialog box double-click Documents then Type a file name you wish and click save to save file   <br/>
<img src="https://i.postimg.cc/5yQtp2dQ/Screen-Shot-2022-08-30-at-7-23-29-PM.png" height="80%" width="80%" alt="Configuring Advanced Ethernet Options Steps"/>
<br />












  
  
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
