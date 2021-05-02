## Unit 18 Homework: Lets go Splunking!

### Step 1: The Need for Speed 

`source="18-SIEMs_Homework_resources_server_speedtest.csv" | eval ratio = 'UPLOAD_MEGABITS' / 'DOWNLOAD_MEGABITS' | table date_mday date_hour IP_ADDRESS DOWNLOAD_MEGABITS UPLOAD_MEGABITS ratio`


![sorted download speed](https://github.com/dmpeppin/BootCamp_Homework/blob/main/HW18Pic1.PNG)

![attack investigation](https://github.com/dmpeppin/BootCamp_Homework/blob/main/HW18Pic2.PNG)

Download speed suppression is used to indicate active attack (image 1). Survey of download speed shows suppressed download speed on the Feb 23. The attack was probably underway by 2pm, persisting through 6pm, and potentially ceased around 8PM (image 2).

 
### Step 2: Are We Vulnerable? 

`source="18-SIEMs_Homework_resources_nessus_logs.csv" severity=critical dest_ip=10.11.36.23 | top severity dest_ip`

![critical vulnerabilities](https://github.com/dmpeppin/BootCamp_Homework/blob/main/HW18Pic4.PNG)


### Step 3: Drawing the (base)line

**Background:**  A Vandaly server is also experiencing brute force attacks into their administrator account. Management would like you to set up monitoring to notify the SOC team if a brute force attack occurs again.


**Task:** Analyze administrator logs that document a brute force attack. Then, create a baseline of the ordinary amount of administrator bad logins and determine a threshold to indicate if a brute force attack is occurring.

1. Upload the administrator login logs.
   - [Admin Logins](resources/Administrator_logs.csv)

2. When did the brute force attack occur?
   - Hints:
     - Look for the `name` field to find failed logins.
     - Note the attack lasted several hours.

      
3. Determine a baseline of normal activity and a threshold that would alert if a brute force attack is occurring.

4. Design an alert to check the threshold every hour and email the SOC team at SOC@vandalay.com if triggered. 

Submit the answers to the questions about the brute force timing, baseline and threshold. Additionally, provide a screenshot as proof that the alert has been created.
 
 
### Your Submission
  
In a word document, provide the following:
  - Answers to all questions where indicated. 
  - Screenshots where indicated.

---

© 2020 Trilogy Education Services, a 2U, Inc. brand. All Rights Reserved.
