# Getting Started With Lightning
Code from Sara Morgan's Pluralsight course called Getting Started Building SPAs with Lightning Component Framework

Link to Unmanaged package that installs all the final code files, including the required unit tests that were not covered in the course
https://login.salesforce.com/packaging/installPackage.apexp?p0=04t36000000YgMU

NOTE: You will need to add a custom domain and enable it before installing the package or creating the code in your org. You should also enable debug mode in order to see all messages displayed in the console log. 

If you see an error such as the following, it means you did not register your domain.

![alt tag](https://github.com/saramorgan/GettingStartedWithLightning/blob/master/UnManagedPackageError.png)

You can register and enable your domain by doing the following:

1. From Setup, go to My Domain in the Quick Find box
2. Enter a unique domain name and click register.
3. Wait for the email telling you it was sucessfully registered
4. Log back in using the URL they send you in the email
5. Go back to My Domain in order to click Deploy to Users. 

**Important: All of this must be done BEFORE you can sucessfully install this unmanaged RaceTrackerAppOriginal version.**


## Suggested Changes
The following are some changes that were suggested in the course:
Course viewers or anyone learning about Lightning are encouraged to make changes and submit pull requests.

| Change                   | Description
| -------------------------| --------------------
| Order Race Results       | Order results displayed in ListRaces component by date in descending order
| Add link to edit page    | Add a link in the Race component for the first inputText component that contains the race name. This should link to the built-in Salesforce edit page. I will give you a hint that this is done easily by just linking to the ID of the race, which you have access to.  
| Check for permissions    | Check for CRUD/FLS permissions; Check out the following URL for more info: http://sforce.co/1S8cXma 
| Organize Results w/ tabs | Use SLDS tabs to organize the race results within tabs for attended/Did not attend and upcoming races. Also you will need to create an event which moves races to different tabs as the races are entered or marked as attended.

