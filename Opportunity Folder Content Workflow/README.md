#Install Guide - Opportunity Content Folder

This guide will show how to install the Opportunity Folder Content workflow into your salesforce account. This guide is assuming you have already installed the Box for Salesforce integration as well as the unmanaged package provided by demo engineering.

**Workflow Description:**
This workflow will enable the user to copy over folders into an opportunity once the opportunity status has changed. The desired effect is that content can be automatically put into an opportunity once it is at certain stages, making it easy for the opportunity owner to fill out any forms associated with this stage in the opportunity as well as have access to content associated with previous stages.

**Step One:**
* Login to your salesforce account and bring up the developer console (click your name or the settings icon if you are in Lightning and click Developer Console)
* In the Developer Console, click File -> New -> Apex Trigger
* Name the trigger oppUpdate and select Opportunity as the sObject
* Copy and paste the code from oppUpdate.apxt into this file and save

**Step Two:**
* In Developer Console, click File -> New -> Apex Class
* Name the class BoxUtilOpp and create it
* Copy and paste the code from BoxUtilOpp.apxc in the parent folder into this file and save

**Step Three:**
* Create the folders and content you want to be copied over depending on each stage of the opportunity. The folders can be stored anywhere on your Box account that you are using with the Salesforce integration
* In the BoxUtilOpp class, copy and paste the folder ID that you want to associate with each opportunity stage at the bottom of the page in the Id fields. All of the opportunity stages are not in the class by default, feel free to add or remove as many as you would like

**Testing:**
* Create an opportunity or go to an existing one and select an opportunity stage
* Click "Save" at the top of the opportunity page and the folder  associated with the opportunity page you have selected and all of its content will be copied over to the opportunity folder
* Note: When you change opportunity stages the previous opportunity stage folder that was copied into the opportunity folder is not deleted
