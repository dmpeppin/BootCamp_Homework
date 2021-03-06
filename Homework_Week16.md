# Daniel Peppin Week 16 Homework

## Week 16 Homework Submission File: Penetration Testing 1

#### Step 1: Google Dorking


- Using Google, can you identify who the Chief Executive Officer of Altoro Mutual is:

`Karl Fitzgerald though it was easy enough to find it on their website, i used a google search site:demo.testfire.net executive`

- How can this information be helpful to an attacker:

`a social engineering method would be to send a fake email pretending to be the CEO and ask for confidential information`


#### Step 2: DNS and Domain Discovery

Enter the IP address for `demo.testfire.net` into Domain Dossier and answer the following questions based on the results:

  1. Where is the company located: `likely Sunnyvale CA`

  2. What is the NetRange IP address: `65.61.137.64 - 65.61.137.127`

  3. What is the company they use to store their infrastructure: `Rackspace Backbone Engineering`

  4. What is the IP address of the DNS server: `65.61.137.117`

#### Step 3: Shodan

- What open ports and running services did Shodan find: `80 and 443 running Apache Tomcat/Coyote JSP engine 1.1`

#### Step 4: Recon-ng

Is Altoro Mutual vulnerable to XSS: `seems so`

![xssed on demo.testfire.net](https://github.com/dmpeppin/BootCamp_Homework/blob/main/HW16_St4-1.PNG)

### Step 5: Zenmap

Your client has asked that you help identify any vulnerabilities with their file-sharing server. Using the Metasploitable machine to act as your client's server, complete the following:

- Command for Zenmap to run a service scan against the Metasploitable machine: `nmap -sV 192.168.0.10`
 
- Bonus command to output results into a new text file named zenmapscan.txt: `nmap -sV 192.168.0.10 -o zenmapscan.txt` i prefer nmap

- Zenmap vulnerability script command: `nmap -sC 192.168.0.10 -p 139,445`

- Once you have identified this vulnerability, answer the following questions for your client:
  1. What is the vulnerability: `I cant seem to find a vulnerability`

![script error](https://github.com/dmpeppin/BootCamp_Homework/blob/main/HW16_St5-1.PNG)

  2. Why is it dangerous:

  3. What mitigation strategies can you recommendations for the client to protect their server:

---
