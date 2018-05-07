#Install Guide - Invite Collaborator
This guide will show how to install the Invite Collaborator workflow into your salesforce account. This guide is assuming you have already installed the Box for Salesforce integration as well as the unmanaged package provided by demo engineering. You will need to have a Box widget embedded in the opportunity page for this to work.

**Workflow Description:**
This workflow will enable you to invite a collaborator into a folder that is associated with an opportunity within Box from a Salesforce page.

**Step One:**
* Login to your salesforce account and bring up the developer console (click your name or the settings icon if you are in Lightning and click Developer Console)
* In the Developer Console, click File -> New -> Apex Trigger
* Name the Trigger getCollaborator and select Opportunity as the sObject
* Copy and paste the code from getCollaborator.apxt into this file and save

**Step Two:**
* In Developer Console, click File -> New -> Apex Class
* Name the class InviteCollaborators and create it
* Copy and paste the code from InviteCollaborators.apxc in the parent folder into this file and save

**Note:** You will see 4 errors in your developer console after creating the trigger and APEX class, these will be resolved after step three

**Step Three:**
* Navigate to your Setup section of your Salesforce account where you can edit visualforce pages
* In the quick search bar on the left, type Opportunities
* Select Fields under the Opportunities dropdown menu
* Scroll down to Opportunity Custom Fields & Relationships and click New
* Select Picklist and click Next
* For Field Label put "Vertical Team Resources"
* For Values select "Enter values with each value separated by a new line"
* Put the names of the teams that you want to have appear in the visual force page to invite to collaborate on a folder each separated by a new line
    * Note: By default, in the InviteCollaborators Apex class there is a Marketing Team and a Legal Team option. Feel free to edit these names or add more team names as you see fit, however you will need to make sure the teams you add in the custom field match exactly to the team names found in the settings.
    * You will also need to get the group ID for each team you want to have the option to invite as a collaborator and put it in the return statement in the getCollaborator method in the InviteCollaborators APEX class
* Click Next
Use the default security settings and click Next
* Click Save
* **Note:** You may get an error in the developer console saying that there is no method handleCollaborator. To fix this, simply make any change in the getCollaborator trigger within the developer console and save it again. For example, creating a new line after the trigger ends and saving will cause it to reinitialize and remove the error

**Testing:**
Create an opportunity or go to an existing one and you should see a field named "Vertical Team Resources"
Click on the "Vertical Team Resources" field and select the team you want to invite to the opportunity folder within Box
Click "Save" at the top of the opportunity page and the group will be imvited
