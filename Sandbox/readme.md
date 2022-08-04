
## Sandbox Environment Usage Guide
In the Optimove Sandbox environment, clients and third parties can test and simulate Optimove APIs before going live. It is used to send customer campaigns via external services. <br>
The Sandbox site simulate production site for schedule campaigns and it contains dummy data. 

- [Requesting Access](#request-access)
- [Sandbox Endpoints](#sandbox-url)
- [Postman Examples](#postman-examples)
- [Sandbox general Channel ID list](#channel-list)
- [Sandbox best practices](#best-practices)
- [Links to documentation](#documentation-links)
- [Sandbox Limitation](#sandbox-limitations)
- [Third Party API list](#3p-access)
- [Executing a Test Campaign in the Sandbox UI site](#exec-test-camp)
- [Frequently asked questions (FAQ)](#faq)
<br/>

### <a id="request-access"></a>Requesting Access
To request Sandbox Site and API access, please click one of the links below to fill our the relevant form: 

 - If you are a client: [Optimove Client Sandbox Request Form](https://optimoveww.zendesk.com/hc/en-us/requests/new?ticket_form_id=360000357937) choose "Sandbox API (Optimove Client Access)"
 - If you are a third party vendor / partner: [Partner / Third Party Vendor Sandbox Request Form](https://optimoveww.zendesk.com/hc/en-us/requests/new?ticket_form_id=360000357937) choose "Sandbox API (Third Party Vendor Access)"

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

### <a id="best-practices"></a>Sandbox best practices
When you are working with our Sandbox enviorment we suggest to follow our best practices in order to avoid 

1. Registration of an Event Listener for Event Type 13 with a specific channel will reduce the number of listeners Optimove needs to reach once a campaign has been completed.
2. Do not delete campaigns that you didnt create
3. For promo integration system you don't need to register listener with a specific channel.

<hr>

### <a id="documentation-links"></a> Links to documentation 

Channel integration: https://docs.optimove.com/integrate-your-service-with-optimove/ 
<br>
Promo system integration: https://academy.optimove.com/en/article/promotion-system-integration

<hr>

### <a id="sandbox-limitations"></a> Sandbox limitations
1. Sandbox environment support only schedule campaigns
2. Real time campaigns cannot be test there
3. As it's a shared environment, you can't upload your own data, and you might receive notifications for campaigns that other users have created

<hr>

### <a id="3p-access"></a> Third Party API list
Third parties accessing Optimove API have limited access to the API list. The API list below represents all APIs required to execute a campaign through your channel. Below you will find the allowed API for Third Party Sandbox & Production API access.

| ﻿API Category           | Available APIs                      | Notes                                                                       |
|------------------------|-------------------------------------|-----------------------------------------------------------------------------|
| /current/general/      | Login                               |                                                                             |
| /current/general/      | GetLastDataUpdate                   | Will not work due to lack of daily in Sandbox environment only              |
| /current/general/      | RegisterEventListener               | Only EventType=2 will not work due to lack of daily in Sandbox environment only |
| /current/general/      | UnRegisterEventListener             |                                                                             |
| /current/general/      |GetRegisteredEventListener            |											| 
|/current/actions/       | GetCampaignDetails     |  												|
| /current/actions/      | GetExecutedCampaignChannelDetails   |                                                                             |
| /current/actions/      | GetExecutedCampaignsByChannel       |                                                                             |
| /current/actions/	 | GetCampaignDetails                  |                                                                              |
| /current/customers/    | GetCustomerOneTimeActionsByCampaign | |
| /current/customers/    | GetCustomerAttributeChangers |                                                     					|
| /current/customers/    | GetCustomerSendDetailsByChannel	|                                                                             |
| /current/customers/    | GetCampaignInteractionCustomers     |                                                                             |
| /current/customers/    | GetCustomerChannelInteractions      |                                                                             |
| /current/customers/    | GetCustomerExecutionDetailsByCampaign      |                                                                             |
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
 1.  In Optimove site, go to One-to-One campaign -> Campaign Builder
 2.  Select a random test Target Group - You can duplicate an existing one and rename it)
 3.  In order to be able to create and run multiple campaigns on the same customers, you should always tick the "Include All" section (see below): <p align="center"><img src="https://github.com/optimove-tech/Optimove-APIs/blob/master/images/campaign%20builder.png"></p>
 4.  In the "Scheduling" section choose the current date as a Start date, and a random measurment way.
 5.  In the "Execution Details" section, select a random Action
 6.  When choosing a Channel, choose the exact same one your registered a listener to (see [Integrate Your Service with Optimove - Best Practices](https://github.com/optimove-tech/Optimove-APIs/tree/master/API-Integrations)). 
 7.  Choose one of the templates you have synchronized to this channel 
 8.  For “Time” select your time NOW plus 10 mins (example: Say the time now is 10:00, then choose 10:10). 
 9.  Click “Create campaign” button to schedule the campaign
 10.  Since the sandbox does not run automatically with updated daily data, you need to go to the Mission control and search for your campaign, click on the three dots on Run Today's Occurrence (Play button) in order to send the campaign (see image below): <p align="center"><img src="https://github.com/optimove-tech/Optimove-APIs/blob/master/images/run%20todays%20occurrence.png"></p> 
 11.  After a quick processing, the notification should be sent to your registered listener endpoint
 12.  Now you can retrieve the campaign details
<hr>

### <a id="faq"></a>Frequently asked questions (FAQ)

 1. **Who can provide me access to the sandbox?**
Please see [Requesting Access](#request-access) above. <br/><br/>
 2. **We are not receiving any event in case of scheduled campaigns unless we press 'Run' and ignore the warning. Is this the valid step?**
This is a valid behavior in the Sandbox environment. In your / client's production instance, a daily process will run the pre-scheduled campaigns and fire the event notifications.<br/><br/>
 3. **Where can we see the metrics which we posted using UpdateCampaignMetrics?**
The client will see it the Campaign Analysis inside their production Optimove instance. This cannot be simulated in the Sandbox environment.<br/><br/>
 4. **What Channel ID should we use?**
In the Sandbox environment, you will be able to use the generic channels (email, sms, etc). Please see [Requesting Access](#request-access) above and fill out the relevant form. The Product Integration Team will enable the relevant channel requested.<br/> 
	> **Note**:  Once in production, the Channel ID will be changed to your real designated Channel ID that will be created for you. <br/><br/>
	
 5. **Why am I seeing many templates under my chosen channel?**
Since its a shared environment, other Optimove’ clients, vendors/partners are synchronizing their templates for testing purposes only.
<br/>
 6. **Will I see the templates i have added using AddTemplate function?**
Yes, you can use the [AddTemplate](https://docs.optimove.com/api-usage-guide/#Optimail_Functions_AddTemplate) function in the Sandbox environment.

	> **Note**: Since the Sandbox environment is a shared environment with other users, your template will be visible to them as well. If this is not an issue, it can remain in the Sandbox. If it is an issue, please use the [UpdateTemplate](https://docs.optimove.com/api-usage-guide/#Optimail_Functions_UpdateTemplate) to change the content of the template accordingly.
