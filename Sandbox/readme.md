## Sandbox Environment Usage Guide
Optimove Sandbox environment is intended for both Optimove clients and third parties to test and simulate Optimove APIs before production usage.

- [Requesting Access](#request-access)
- [Sandbox Endpoints](#sandbox-url)
- [Sandbox general Channel ID list](#channel-list)
- [Postman Examples](#postman-examples)
- [Third Party API list](#3p-access)
- [Executing a Test Campaign in the Sandbox UI site](#exec-test-camp)
- [Frequently asked questions (FAQ)](#faq)
<br/>

### <a id="request-access"></a>Requesting Access
To request Sandbox Site and API access, please click one of the links below to fill our the relevant form: 

 - If you are a client: [Optimove Client Sandbox Request Form](https://optimoveteams.atlassian.net/servicedesk/customer/portal/1/group/3/create/14)
 - If you are a third party vendor / partner: [Partner / Third Party Vendor Sandbox Request Form](https://optimoveteams.atlassian.net/servicedesk/customer/portal/1/group/3/create/13)

>**Notes:**
>  - Once you fill in one of the requests form, the Optimove Product Integration team will review you request and create relevant access.
>  - If any of the details in the request form are unclear, the Product Integration Team will contact you, therefore please enter a valid email address.
>  - The Sandbox environment consist of dummy data therefore you are unable to upload real data.
>  The Sandbox environment is a static environment and does not have updated daily data, therefore creating campaign for future date & time is not supported

<hr>

### <a id="sandbox-url"></a>Sandbox Endpoints

- Optimove UI: https://sandbox.optimove.net
- Optimove API: https://sandbox-api.optimove.net
<hr>

### <a id="postman-examples"></a>Postman Examples

We have created a Postman collection in order to help you test and use our APIs. Please follow the instructions in our [Postman How To Guide](https://github.com/optimove-tech/Optimove-APIs/blob/master/Sandbox/postman-how-to/readme.md).
<hr>

### <a id="channel-list"></a>Sandbox general Channel ID list
Optimove created pre-defined channel ID for most general channel executions in the Sandbox environment. Please use the below list to test with the relevant Channel ID.

 - Email: 504
 - SMS: 505
 - Call Center: 502
 - Push Notification: 506
 - Web Push: 510
 - In-Platform (in-app): 511

> **Note**:  Once in production, the CSM will provide you with your production Channel ID.  

<hr>

### <a id="3p-access"></a>Third Party API list
Third parties accessing Optimove API have limited access to the API list. The API list below represents all APIs required to execute a campaign through your channel. Below you will find the allowed API for Third Party Sandbox & Production API access.

| ﻿API Category           | Available APIs                      | Notes                                                                       |
|------------------------|-------------------------------------|-----------------------------------------------------------------------------|
| /current/general/      | Login                               |                                                                             |
| /current/general/      | GetLastDataUpdate                   | Will not work due to lack of daily in Sandbox environment only              |
| /current/general/      | RegisterEventListener               | Only EventType=2 will work due to lack of daily in Sandbox environment only |
| /current/general/      | UnRegisterEventListener             |                                                                             |
| /current/general/      | GetRegisterEventListener            |                                                                             |
| /current/actions/      | GetExecutedCampaignChannelDetails   |                                                                             |
| /current/actions/      | GetExecutedCampaignsByChannel       |                                                                             |
| /current/customers/    | GetCustomerOneTimeActionsByCampaign |                                                                             |
| /current/customers/    | GetCustomerSendDetailsByChannel	|                                                                             |
| /current/customers/    | GetCampaignInteractionCustomers     |                                                                             |
| /current/customers/    | GetCustomerChannelInteractions      |                                                                             |
| /current/integrations/ | AddChannelTemplates                 |                                                                             |
| /current/integrations/ | GetChannelTemplates                 |                                                                             |
| /current/integrations/ | GetChannelTemplatesDetails          |                                                                             |
| /current/integrations/ | DeleteChannelTemplates              |                                                                             |
| /current/integrations/ | AddChannelApps                      |                                                                             |
| /current/integrations/ | DeleteChannelApps                   |                                                                             |
| /current/integrations/ | UpdateCampaignMetrics               |                                                                             |
| /current/integrations/ | UpdateCampaignInteractions          |                                                                             |
| /current/integrations/ | SetCustomerChannelPreference        |                                                                             |
|                        |                                     |                                                                             |

<hr>

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
<hr>

### <a id="faq"></a>Frequently asked questions (FAQ)

 1. **Who can provide me access to the sandbox?**
Please see [Requesting Access](#request-access) above. <br/><br/>
 2. **Why am I getting error when trying to call the GetRegisteredEventListeners API?**
This API function is current unavailable in the Sandbox environment. It will  be available in Production. <br/>If you want to verify the URL was indeed registered, please contact the Product Integration Team with the URL and they will confirm.<br/><br/>
 3. **We are not receiving any event in case of scheduled campaigns unless we press 'Run' and ignore the warning. Is this the valid step?**
This is a valid behavior in the Sandbox environment. In your / client's production instance, a daily process will run the pre-scheduled campaigns and fire the event notifications.<br/><br/>
 4. **Where can we see the metrics which we posted using UpdateCampaignMetrics?**
The client will see it the Campaign Analysis inside their production Optimove instance. This cannot be simulated in the Sandbox environment.<br/><br/>
 5. **What Channel ID should we use?**
In the Sandbox environment, you will be able to use the generic channels (email, sms, etc). Please see [Requesting Access](#request-access) above and fill out the relevant form. The Product Integration Team will enable the relevant channel requested.<br/> 
	> **Note**:  Once in production, the Channel ID will be changed to your real designated Channel ID that will be created for you. <br/><br/>
	
 6. **Why am I seeing many templates under my chosen channel?**
Since its a shared environment, other Optimove’ clients, vendors/partners are synchronizing their templates for testing purposes only.
<br/>
 6. **Will I see the templates i have added using AddTemplate function?**
Yes, you can use the [AddTemplate](https://docs.optimove.com/api-usage-guide/#Optimail_Functions_AddTemplate) function in the Sandbox environment.

	> **Note**: Since the Sandbox environment is a shared environment with other users, your template will be visible to them as well. If this is not an issue, it can remain in the Sandbox. If it is an issue, please use the [UpdateTemplate](https://docs.optimove.com/api-usage-guide/#Optimail_Functions_UpdateTemplate) to change the content of the template accordingly.
