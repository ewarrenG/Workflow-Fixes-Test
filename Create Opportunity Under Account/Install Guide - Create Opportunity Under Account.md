This guide will show how to install the Create Opportunity Under Opportunity workflow into your salesforce account. This guide is assuming you have already installed the Box for Salesforce integration as well as the unmanaged package provided by demo engineering. You will need to have a Box widget embedded in the opportunity page for this to work.

You will also need to have the managed package widgets embedded into the Opportunity and Account pages to create the folders that will be used in this workflow. The managed package install guide walks you through how to do this.

Workflow description:
This workflow will allow the user to automatically have a Box folder created and nested inside of the account which the opportunity is associated with. This should help show that it will be easier to keep track of opportunities associated with accounts more easily by using the integration.

Step One:
Login to your salesforce account and bring up the developer console (click your name or the settings icon if you are in Lightning and click Developer Console)
In the Developer Console, click File -> New -> Apex Trigger
Name the Trigger createFolder and select Opportunity as the sObject
Copy and paste the code from createFolder.rtx into this file and save

Step Two:
In Developer Console, click File -> New -> Apex Class
Name the class BoxUtilCreateFolder and create it
Copy and paste the code from BoxUtilCreateFolder.apxc in the parent folder into this file and save

Note: You will see 2 errors in your developer console after creating the trigger and APEX class, these will be resolved after step three

Step Three:
Navigate to your Setup section of your Salesforce account where you can edit visualforce pages
In the quick search bar on the left, type Opportunities
Select Fields under the Opportunities dropdown menu
Scroll down to Opportunity Custom Fields & Relationships and click New
Select Text and click Next
For Field Label put "folderId"
For Length senter 50
Click Next
Click Save

Testing:
Create an account and use the Box managed package to create a folder for the account
Create a new opportunity on the same account page
Save the opportunity and verify that the opportunity folder is now within the account folder
