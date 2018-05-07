# Install Guide - Smart Content
This guide will show how to install the Smart Content workflow into your salesforce account. This guide is assuming you have already installed the Box for Salesforce integration as well as the unmanaged package provided by demo engineering.

**Workflow Description:**
The functionality of this workflow will copy in a folder based off a Competitor custom filed that the user puts into the opportunities Salesforce page. The desired effect is that it is easier to get relevant competitor content into the box folder associated with new opportunities.

**Step One:**
* Login to your salesforce account and bring up the developer console (click your name or the settings icon if you are in Lightning and click Developer Console)
* In the Developer Console, click File -> New -> Apex Trigger
Name the trigger moveFolder and select Opportunity as the sObject
Copy and paste the code from moveFolder.apxt into this file and save

**Step Two:**
* In Developer Console, click File -> New -> Apex Class
* Name the class BoxUtil and create it
* Copy and paste the code from BoxUtil.apxc in the parent folder into this file and save

**Step Three:**
* Create the competitive folders and content you want to appear in each folder
* Make note of the competitor names and folder ID's associated with these folders because you will need to put them in the BoxUtil Apex class in the next step

**Step Four:**
* Navigate to your Setup section of your Salesforce account where you can edit visualforce pages
* In the quick search bar on the left, type Opportunities
* Select Fields under the Opportunities dropdown menu
* Scroll down to Opportunity Custom Fields & Relationships and click New
* Select Picklist and click Next
* For Field Label put "Competitors"
* For Values select "Enter values with each value separated by a new line"
* Put the names of the items that you want to have appear in the visual force page to invite to collaborate on a folder each separated by a new line
* Note: By default, in the BoxUtil Apex class there is a Microsoft, Dropbox, Amazon, and Egnyte option. Feel free to edit these names or add competitor team names as you see fit, however you will need to make sure the items you add in the custom field match exactly to the item names found in the Apex class.
* You will also need to get the folder ID for each folder you want to have the option to copy into the opportunity folder and put it in the 'id' statement within the competition method inside of the BoxUtil class.
* This is confusing, so here is a picture of what you need to change in the BoxUtil Apex class that you copied into your developer console in Step Two. These folders can be stored anywhere within the Box account and do not have to be within the Salesforce root folder in order to be copied in. Make sure the name of each field is matching the items in your custom list, and the folder ID of the folder you want to be copied in if the user selects each item is below it.

* Field Name should be the same as Field Label and click Next


**Testing:**
* Create an opportunity or go to an existing one and you should see a field named "Competitors"
* Click on the "Competitors" field and select the competitor you want to have content copied over to the opportunity folder within Box
* Click "Save" at the top of the opportunity page and the competitive folder and all of its content will be copied over to the opportunity folder
