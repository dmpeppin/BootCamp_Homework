## Unit 18 Homework: Lets go Splunking!

### Step 1: The Need for Speed 

`source="18-SIEMs_Homework_resources_server_speedtest.csv" | eval ratio = 'UPLOAD_MEGABITS' / 'DOWNLOAD_MEGABITS' | table date_mday date_hour IP_ADDRESS DOWNLOAD_MEGABITS UPLOAD_MEGABITS ratio`


![sorted download speed](https://github.com/dmpeppin/BootCamp_Homework/blob/main/HW18Pic1.PNG)

![attack investigation](https://github.com/dmpeppin/BootCamp_Homework/blob/main/HW18Pic2.PNG)

Download speed suppression is used to indicate active attack (image 1). Survey of download speed shows suppressed download speed on the Feb 23. The attack was probably underway by 2pm, persisting through 6pm, and potentially ceased around 8PM (image 2).

 
### Step 2: Are We Vulnerable? 

`source="18-SIEMs_Homework_resources_nessus_logs.csv" severity=critical dest_ip=10.11.36.23 | top severity dest_ip`

![critical vulnerabilities](https://github.com/dmpeppin/BootCamp_Homework/blob/main/HW18Pic4.PNG)

![critical vulnerabilities](https://github.com/dmpeppin/BootCamp_Homework/blob/main/HW18Pic5.PNG)

![critical vulnerabilities](https://github.com/dmpeppin/BootCamp_Homework/blob/main/HW18Pic6.PNG)

Several (49) critical vulnerabilities were found. The search will run daily to report if any (>0) vulnerabilities exist.


### Step 3: Drawing the (base)line

![critical vulnerabilities](https://github.com/dmpeppin/BootCamp_Homework/blob/main/HW18Pic7.PNG)
