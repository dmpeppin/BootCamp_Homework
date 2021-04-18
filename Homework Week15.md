# Daniel Peppin Homework Week 15


## Unit 15 Submission File: Web Vulnerabilities and Hardening


### Part 1: Q&A

#### The URL Cruise Missile

| Protocol         | Host Name                 | Path                   | Parameters               |
| ---------------- | :-----------------------: | ---------------------- | ------------------------ |
| **http://**      | **`www.buyitnow.tv`**     | **/add.asp**           | **?item=price#1999**     |


1. Which part of the URL can be manipulated by an attacker to exploit a vulnerable back-end database system? 

Answer: `everything after the ? generally is data sent to process, so in this case I would try to change the code to day "item=price#1" which is part of the 'parameters'`

2. Which part of the URL can be manipulated by an attacker to cause a vulnerable web server to dump the `/etc/passwd` file? Also, name the attack used to exploit this vulnerability.

Answer: `With "Directory Traversal" I would replace everything after "www.buyitnow.tv/" for example www.buyitnow.tv/../../../ which is part of the 'path'`
   
3. Name three threat agents that can pose a risk to your organization.

Answer: `criminals, state actors, hactivists`

4. What kinds of sources can act as an attack vector for injection attacks?

Answer: `web forms, sqlmap`

5. Injection attacks exploit which part of the CIA triad?

Answer: `confidentiality if they are able to retrieve private and sensitive data, integrity if they are able to modify contents, availability if they are able to corrupt data`

6. Which two mitigation methods can be used to thwart injection attacks?

Answer: `output encoding, data input filters1`

____

#### Web Server Infrastructure

Use the graphic below to answer the following questions:

| Stage 1        | Stage 2             | Stage 3                 | Stage 4              | Stage 5          |
| :------------: | :-----------------: | :---------------------: | :------------------: | :--------------: |
| **Client**     | **Firewall**        | **Web Server**          | **Web Application**  | **Database**     |
   
   
1. What stage is the most inner part of the web architecture where data such as, customer names, addresses, account numbers, and credit card info, is stored?

Answer: `database`

2. Which stage includes online forms, word processors, shopping carts, video and photo editing, spreadsheets, file scanning, file conversion, and email programs such as Gmail, Yahoo and AOL.

Answer: `web application`

3. What stage is the component that stores files (e.g. HTML documents, images, CSS stylesheets, and JavaScript files) that's connected to the Internet and provides support for physical data interactions between other devices connected to the web?

Answer: `web server`

4. What stage is where the end user interacts with the World Wide Web through the use of a web browser?

Answer: `client`

5. Which stage is designed to prevent unauthorized access to and from protected web server resources?

Answer: `firewall`

----


#### Server Side Attacks

1. What is the process called that cleans and scrubs user input in order to prevent it from exploiting security holes by proactively modifying user input.

Answer: `input sanitation`

2. Name the process that tests user and application-supplied input. The process is designed to prevent malformed data from entering a data information system by verifying user input meets a specific set of criteria (i.e. a string that does not contain standalone single quotation marks).

Answer: `input validation`

3. **Secure SDLC** is the process of ensuring security is built into web applications throughout the entire software development life cycle. Name three reasons why organization might fail at producing secure web applications.

Answer: `expensive, time consuming, not obvious flaws (applications works, no more work is done on it), not in scope (firewalls will do all the protection we need)`

4. How might an attacker exploit the `robots.txt` file on a web server?

Answer: `the robots.txt often shows pages that are not meant to be indexed and thus not interacted with, putting a target on them`

5. What steps can an organization take to obscure or obfuscate their contact information on domain registry web sites?

Answer: `WHOIS privacy where the contact info is removed from the actual organization`
   
6. True or False: As a network defender, `Client-Side` validation is preferred over `Server-Side` validation because it's easier to defend against attacks.

   - Explain why you chose the answer that you did.

Answer: `I will say false since client side software can be more easily bypassed with proxy tools like web scarab where it is possible to change content *after* it passes through client protection code`

____

#### Web Application Firewalls

1. Which layer of the OSI model do WAFs operate at?

Answer: `The application layer, or what we call layer 7`

2. A WAF helps protect web applications by filtering and monitoring what?

Answer: `SQLi and XSS

3. True or False: A WAF based on the negative security model (Blacklisting) protects against known attacks, and a WAF based on the positive security model (Whitelisting) allows pre-approved traffic to pass.

Answer: `True`
____

#### Authentication and Access Controls

Security enhancements designed to require users to present two or more pieces of evidence or credentials when logging into an account is called multi-factor authentication.

- Legislation and regulations such as The Payment Card Industry (PCI) Data Security Standard requires the use of MFAs for all network access to a Card Data Environment (CDE).

- Security administrators should have a comprehensive understanding of the basic underlying principles of how MFA works.

1. Define all four factors of multifactor authentication and give examples of each:

   - Factor 1: `something known: standard login ie password, PIN`

   
   - Factor 2: `something owned: phsyical keys ie smart card`
   
   
   - Factor 3: `something owned: biometrics ie fingerprint, iris scan`

   
   - Factor 4: `location: landline access, GPS detection`

   
2. True or False: A password and pin is an example of 2-factor authentication.

Answer: `I would say False, they are both something known and nothing owned`
   
3. True or False: A password and `google authenticator app` is an example of 2-factor authentication.

Answer: `True, something known (password) and something owned (authenticator app)`
   
4. What is a constrained user interface? 

Answer: `Limited visibility based on autheticated privileges`

----
____

### Part 2: The Challenge 

In this activity, you will assume the role of a pen tester hired by a bank to test the security of the bank’s authentication scheme, sensitive financial data, and website interface.

#### Challenge #1

![hidden javascript](https://github.com/dmpeppin/BootCamp_Homework/blob/main/HW15%20Ch1.PNG)



#### Challenge #2

![credit cards](https://github.com/dmpeppin/BootCamp_Homework/blob/main/HW15%20Ch2.PNG)


#### Challenge #3

Present Working Directory `tcp && pwd && whoami`

![pwd](https://github.com/dmpeppin/BootCamp_Homework/blob/main/HW15%20Ch3.PNG)

Locate webpage `tcp && cd / && find . -iname webgoat_challenge_guest.jsp`

![page locator](https://github.com/dmpeppin/BootCamp_Homework/blob/main/HW15%20Ch3.PNG)

Deface `tcp && echo "Haxed by DP" > webgoat_challenge_guest.jsp` note the overwrite rather than the append

![defaced](https://github.com/dmpeppin/BootCamp_Homework/blob/main/HW15%20Ch3.PNG)
