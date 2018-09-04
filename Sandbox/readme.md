## Sandbox Environment Usage Guide
Optimove Sandbox environment is intended for both Optimove clients and third parties to test and simulate Optimove APIs before production usage.

- [Requesting Access](#request-access)
- [Frequently asked questions (FAQ)](#faq)
- [Executing a Test Campaign in the Sandbox site](#exec-test-camp)

<br/>

### <a id="request-access"></a>Requesting Access
To request Sandbox Site and API access, please click one of the links below to fill our the relevant form: 

 - If you are a client: [Optimove Client Sandbox Request Form](http://bit.ly/Optimove_Client_Sandbox_Site_and_API_Request)
 - If you are a third party vendor / partner: [Partner / Third Party Vendor Sandbox Request Form](http://bit.ly/Optimove_Third_Party_Sandbox_Site_and_API_Request)

>**Notes:**
>  - Once you fill in one of the requests form, the Optimove Product Integration team will review you request and create relevant access.
>  - If any of the details in the request form are unclear, the Product Integration Team will contact you, therefore please enter a valid email address.
>  - The Sandbox environment consist of dummy data therefore you are unable to upload real data.
>  The Sandbox environment is a static environment and does not have updated daily data, therefore creating campaign for future date & time is not supported

<br/>

### <a id="faq"></a>Frequently asked questions (FAQ)

 1. **Who can provide me access to the sandbox?**<br/>
Please see [Requesting Access](#request-access) above. <br/><br/>
 2. **Why am I getting error when trying to call the GetRegisteredEventListeners API?**<br/>
This API function is current unavailable in the Sandbox environment. It will  be available in Production. <br/>If you want to verify the URL was indeed registered, please contact the Product Integration Team with the URL and they will confirm.<br/><br/>
 3. **We are not receiving any event in case of scheduled campaigns unless we press 'Run' and ignore the warning. Is this the valid step?**<br/>
This is a valid behavior in the Sandbox environment. In your / client's production instance, a daily process will run the pre-scheduled campaigns and fire the event notifications.<br/><br/>
 4. **Where can we see the metrics which we posted using UpdateCampaignMetrics?**<br/>
The client will see it the Campaign Analysis inside their production Optimove instance. This cannot be simulated in the Sandbox environment.<br/><br/>
 5. **What Channel ID should we use?**<br/>
In the Sandbox environment, you will be able to use the generic channels (email, sms, etc). Please see [Requesting Access](#request-access) above and fill out the relevant form. The Product Integration Team will enable the relevant channel requested.<br/> Note: Once in production, the Channel ID will be changed to your real designated Channel ID that will be created for you. <br/><br/>
 6. **Why am I seeing many templates under my chosen channel?**<br/>
Since its a shared environment, other Optimove’ clients, vendors/partners are synchronizing their templates for testing purposes only.

<br/>

### <a id="exec-test-camp"></a>Executing a Pre-scheduled Test Campaign in the Sandbox site
 1.  In Optimove site, go to One-to-One campaign -> Run Campaign
 2.  Select the current date / today's date - The sandbox is a static environment and does not have updated daily data, therefore creating campaign for future date & time is not supported)
 3.  Select a random test Target Group - You can duplicate an existing one and rename it)
 4.  In order to be able to create and run multiple campaigns on the same customers, you should always untick the "exclusion" section (see below): 
<p align="center"><img src="https://github.com/optimove-tech/Optimove-APIs/blob/master/Sandbox/one-to-one-camp.jpg?raw=true"></p>

 5. Choose a random measurement under "Measure" and click on the "Next" button
 6. In the "action" section, select a random Action
 7. When choosing a Channel, choose the exact same one your registered a listener to (see [Integrate Your Service with Optimove - Best Practices](https://github.com/optimove-tech/Optimove-APIs/tree/master/API-Integrations)). 
 8. Choose one of the templates you have synchronized to this channel 
 9. For “Time of Day” select your time NOW plus 10 mins (example: Say the time now is 10:00, then choose 10:10). 
 10. Click on the "Done" button
 11. Click “Schedule” button to schedule the campaign
 12. Since the sandbox does not run automatically with updated daily data, you need go to the Marketing Plan and click on Run-Now (Play button) in order to send the campaign (see image below):
 <p align="center"><img src="https://github.com/optimove-tech/Optimove-APIs/blob/master/Sandbox/marking-plan-run-camp.jpg?raw=true"></p> 
 
 13.  After a quick processing, the notification should be sent to your registered listener endpoint
 14. Now you can retrieve the campaign details
