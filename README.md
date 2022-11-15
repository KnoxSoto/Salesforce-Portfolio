# KnoxNethanSalesforce
This is my portfolio for Salesforce &amp; nCino

# Salesforce 
## Certifications & Trailhead (Salesforce)


---

**Achievements:**

- [Trailhead](https://trailblazer.me/id/ksoto4)
    
    *Salesforce Certified Administrator*
    
    *Salesforce Certified Platform App Builder*
    
    *Security Specialist SuperBadge*
    
    *Ranger Status*

![image](https://user-images.githubusercontent.com/117833554/201966203-cb4739b7-af3c-4bef-86ea-175df322e793.png)

---
## Flows Automations
  *FLOW Automation/Validation Rules/Others
#Screen Flows:
*Reasoning -

*Create a quick contact on the account object with validation rules for phone numbers / tieing to the account object without having to assigned it. The *flow will display error messages and let the user go to the previous page to edit it.
*Very simple flow to allow the user to create a contact and if the user input the incorrect data it will display the faultmessage
![image](https://user-images.githubusercontent.com/117833554/201966890-b5433c94-7184-4b91-a70d-ce9206808af6.png)

*Reasoning -
*Created a quick contact/opportunity and automated created Opportunity Contact Role with Multi-Screens.
*Ulitize - Get Record to retrieve account records so the contact object can use those fields for address. Created two screens with Contact/Opportunity *(Picklists for Opportunity as well) On the Opportunity screen you can search for accounts as well. After going through the whole process using recordId I *was able to create an Opportunity Contact Role automatically without using an screen. Each screen support a Fault error message
![image](https://user-images.githubusercontent.com/117833554/201966970-d77946cc-0203-46bc-92ec-2c84c1b5513d.png)

*Record Trigger Flows:
*Reasoning -

*Created a custom object called "Tickets" its used to allow users to open tickets in regards to nCino related issues/erorrs/etc. Need a way to alert the *user's when they were assigned a ticket and display the description of the ticket in outlook.
*When does this flow launched? When the record is created or update because the field "Assigned_to" need to be update with a user. When a user opened a *ticket they should not assigned it to anyone first because the administrator team need to decide where to direct the ticket to get it solved. Using the *Element Action email we can get a custom notification when a user is assigned a ticket.
![image](https://user-images.githubusercontent.com/117833554/201967094-27f2ce66-a8f2-4845-abe2-8cc1941df0ee.png)

---

## nCino
![image](https://user-images.githubusercontent.com/117833554/201967348-6faac0f5-d250-4281-b556-27111eb87a6f.png)
Feedback
*“Knox was amazing and very professional! He went over and beyond by calling me and zooming with me to get down to the matter” - Stalk-holder

*“Thank you for your partnership with the Commercial Power Hours. You are instrumental in the process, updates and making nCino efficient for all associates. You tiresly work behind the scenes to make nCino work! Excited to see what you can do in 2022!” - Banking Learner Instructor”



*“Knox Joined the bank 10/28 of this year. He immediately demonstrated a passion for learning and for supporting our customers. From his very first day, Knox took the initiative to research training materials and resources for resolving nCino tickets. With his background in IT, Knox applies discipline and consistency to how he tackles problems.” - Current Manager



*"Congratulations on achieving your nCino 301 Commercial Banking Configuration Certification! That took several training sessions and then a closed-book exam. Great Job in achieving the first official nCino Certification for the bank."





#Certifications (nCino)
*Achievements:
*Courses/ Certification
*  301 Commercial Banking Functional Certification Completed
*  201 Commercial Banking Functional Course Completed
* 301 Commercial Banking Functional Course Completed
* Attend nCino Insight 2022
![image](https://user-images.githubusercontent.com/117833554/201967615-89ef99a7-133c-4020-828d-af36419a80ef.png)

*Support and Resolving over 2,305 tickets over the past six months -
*Reason -
*Necessary to have a ticketing system to get User feedback and error fixed. Using an custom object "Tickets" it allows the end-user to open tickets to solve error message, new ideas, requests, new users etc..
*Successful -
*Tickets being response to and redirected is crucial to the nCino platform. Being able to solve those business problems is necessary for the workflow to *continue running smoothly. Saving time and Impacted for the customer if these are not fixed in a timely manner the customer might opt for another *business. Using tickets and gathering feedback from the user's. We are able to work on enhancement to improve workflow all around the platform in which *improve the user input and efficiency.
*Utilizing nCino Support -
*Reason -
*Over 50 Cases closed with nCino Support, it important to reach out to nCino support to get problem solved that are timely manner.
*Successful -
*Ulitize nCino support to solve those time-sensetive issues. Such as Credit Reports, Loan not flowing correctly, Covenant Mgmt, Daily Data load to the *core. Being able to quickly open cases is necessary if something is interupting the flow of business it needs to be resolved as soon as possible.

*User Stories  Covenant Compliance Data-
*As a nCino user we are currently seeing covenant compliance pass the effective date due to the automation of the daily batch we want to eliminate the *Covenant compliance that were generated pass 2022
*Created a report to identify the covenant with covenant compliance that are showing multiple covenant compliance past 2022 (Currently showing covenant *compliance past 2022 over 25,000 records)
*When dealing with data it's important to make sure we don't delete any information that needs to be there. So by working on the report plus the SOQL *query we can filter out what we want as for this instance we needed  evaluated by to equal "null" so we don't delete the covenant compliance that have *been evaluated by a end-user.
*Testing always done in an sandbox environment and ulitizing Salesforce inspector we can delete these records by using salesforce import.
*After creating the SOQL this for example -

'SELECT LLC_BI__Covenant__c, name, LLC_BI__Evaluated_By__c, LLC_BI__Approved_By__c, LLC_BI__Status__c, LLC_BI__Effective_Date__c'
'FROM LLC_BI__Covenant_Compliance2__c'
'WHERE LLC_BI__Status__c = 'Pending' AND LLC_BI__Evaluated_By__c =null AND LLC_BI__Effective_Date__c >= 2024-01-01' 
'ORDER BY LLC_BI__Evaluated_By__c'
*I was able to filter out what the report was stating and matching them.
*In conclusion we were able to delete the Multiple covenant compliance showing past 2022.  - Cleaning up data
*User Stories Duplicate Relationship's -
*As core is working on transfer data from the branches there are duplicate coming through the core due to not validation rule created and duplicate system *to alert user's. As a end-user we are experiencing a high rate of duplicate relationship's is there any system to prevent this.

*First thing to identify what is causing this issues is to figure what fields are causing duplicate or invalid data. After investigating figuring out that *the Tax ID field can not have dashes in it. From that perspective we know we can ulitizes Salesforce (Validation rules) on the relationship field
*After creating the validation rule on the relationship object (LEN(LLC_BI_Tax_Identification_Number__C) > 10 this formula will prevent dashes in the tax *Identify field.
*Creating matching rules with duplicate rules will alert the user's based on  if the relationship have matching Tax ID that will alert the user's that *there are duplicate records there.
*Administrator will now be able to merge the records from the record itself instead of switching to Salesforce classic to merge records.
*In conclusion - This has eliminate duplicate by high percentage and saving time when creating households.

*Flow for Custom Object notifications -
*Reason -
*When assigning tickets to an user a notification needs to be sent the user and show the description of the ticket as well as the ticket number.
*Successful -
*Utilizing the record-trigger flow automation I was able to create the notification by using the action "Send an email" and was successful in alerting the *user's when they are assigned a ticket.





*Salesforce Inspector Delete  -
*Reason -
*Daily batcher in covenant compliance created evaluation date past 1/1/2023 - 1/1/2033 that needs to be deleted it created over 6,255
*Successful -
*Created a reported to see what data we need to see and do testing in sandbox as well to delete those records successful. I was able to successful to *delete the 6,255 covenant compliance without the evalute by status filled out by a user.

*Youtube Video: nCino Document Manager how to configuration & add Placeholder -






