## Unit 19 Homework: Protecting VSI from Future Attacks

#### Question 1
- Several users were impacted during the attack on March 25th.
- Based on the attack signatures, what mitigations would you recommend to protect each user account? Provide global mitigations that the whole company can use and individual mitigations that are specific to each user.

There are 2 events of interest: around 1:30AM on Mar25, there was a large number of "user account locked out" events, and around 9AM on Mar25, there was a large number of "password reset attempts"

![image](https://github.com/dmpeppin/BootCamp_Homework/blob/main/HW19Pic1.PNG)

Global Mitigation: Brute force attacks are generally mitigated by delays in authentication. The traditional response would be to increase the account lockout timeout time to make it time prohibited to fail to lockout. However this makes us susceptible to DoS attack where the account can potentially be forced to lockout indefinitely. Thus we will not go this route. Instead, I will recommend to introduce a 5 second delay to authentication. 5 seconds is not so long that it is time prohibitive to authorized users, but will slow down brute force attacks. We can also look at options to IP ban offenders. For example, if an IP address triggers, say, 5 lockouts, then ban this IP for, say, 30minutes. This will be a nuisance to authorized users to some extent of course, but much more time prohibitive to brute force attacks.

Additional Tasks: For these users, we can deactive these accounts from login and migrate these users to new accounts.


#### Question 2
- VSI has insider information that JobeCorp attempted to target users by sending "Bad Logins" to lock out every user.
- What sort of mitigation could you use to protect against this?

This sort of Brute Force DoS attack exploits user account lock out timeouts. We will need a different method to mitigate. I propose to include user IP as part of the timeout rule. For example, if an IP address triggers, say, 5 lockouts, then ban this IP for, say, 30minutes. We can also deploy some sort of CAPTCHA that might break many brute force tools. We should prbably make a alert for this behavior. 

  

### Part 2: Apache Webserver Attack:

#### Question 1
- Based on the geographic map, recommend a firewall rule that the networking team should implement.
- Provide a "plain english" description of the rule.
  - For example: "Block all incoming HTTP traffic where the source IP comes from the city of Los Angeles."
- Provide a screen shot of the geographic map that justifies why you created this rule. 

![image](https://github.com/dmpeppin/BootCamp_Homework/blob/main/HW19Pic4.PNG)

![image](https://github.com/dmpeppin/BootCamp_Homework/blob/main/HW19Pic3.PNG)

If we compare the baseline (top image) to the attack (bottom image) we see an emergance of considerable traffic from Ukraine.



![image](https://github.com/dmpeppin/BootCamp_Homework/blob/main/HW19Pic2.PNG)


![image](https://github.com/dmpeppin/BootCamp_Homework/blob/main/HW19Pic5.PNG)

  
#### Question 2

- VSI has insider information that JobeCorp will launch the same webserver attack but use a different IP each time in order to avoid being stopped by the rule you just created.

- What other rules can you create to protect VSI from attacks against your webserver?
  - Conceive of two more rules in "plain english". 
  - Hint: Look for other fields that indicate the attacker.
  


### Guidelines for your Submission:
  
In a word document, provide the following:
- Answers for all questions.
- Screenshots where indicated

Submit your findings in BootCampSpot!
