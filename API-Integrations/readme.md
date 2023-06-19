## Integrate Your Service with Optimove - Best Practices

- [Pre-scheduled Flow](#pre-flow)
- [Realtime Flow](#rt-flow)
- [Bonus Integration Pre-scheduled Flow](#bonus)
- [Conditional Execution Bonus Flow](#ce-flow)
- [Bonus Integration Realtime Flow](#bonusrt)

<br/>

### <a id="pre-flow"></a>Pre-Scheduled Flow: 
**Use Cases**: 

 1. As an Optimove client, you wish to integrate to an external service with Optimove and act as the middle-ware.
 2. As a third party vendor / partner, you are interested in using Optimove to automatically send customer campaigns via your marketing platform.

<p align="center"><img src="https://github.com/optimove-tech/Optimove-APIs/blob/ShayTest/API-Integrations/Pre-Scheduled%20Flow%20-%20Execution%20(1).png?raw=true"></p>

>**Notes**: 
> -   For EventTypes (#1 above) refer to [RegisterEventListener](https://docs.optimove.com/api-usage-guide/#General_Functions_RegisterEventListener)
> -   Please contact the Product Integration Team to provide you with the exact Channel ID you should register the listener ([RegisterEventListener](https://docs.optimove.com/api-usage-guide/#General_Functions_RegisterEventListener)), and synchronize your templates to ([AddChannelTemplates](https://docs.optimove.com/api-usage-guide/#AddChannelTemplates) #2 above)
> -  For more details, please refer to our [Optimove docs site](https://docs.optimove.com/integrate-your-service-with-optimove/)
<br/>

----------
### <a id="rt-flow"></a>Realtime Flow: 
**Use Cases**: 

1. As an Optimove client, you wish to automatically send your customers realtime campaigns based on Optimove's [Track & Trigger](https://docs.optimove.com/track-and-trigger/) add-on product.
 2. As a third party vendor / partner, you are interested in using Optimove to automatically send customer realtime campaigns based on Optimove's [Track & Trigger](https://docs.optimove.com/track-and-trigger/) add-on product enabled in your client's Website / Mobile Application via your marketing platform.

<p align="center"><img src="https://github.com/optimove-tech/Optimove-APIs/blob/ShayTest/API-Integrations/Realtime%20Flow%20-%20Execution.png?raw=true"></p>

>**Notes**: 
> - This integration flow **supports** Optimove clients who have Optimove's [Server Side API](https://github.com/optimove-tech/Reporting-Server-Side-Custom-Events) or[Track & Trigger](https://docs.optimove.com/track-and-trigger/) add-on product running on their website, mobile native app **only**!
> - The API payload you will receive in realtime is described in [RegisterEventListener](https://docs.optimove.com/api-usage-guide/#General_Functions_RegisterEventListener) under EventTypeID = 11
> -   Please contact the Product Integration Team to provide you with the exact Channel ID you should register the realtime listener ([RegisterEventListener](https://docs.optimove.com/api-usage-guide/#General_Functions_RegisterEventListener)), and synchronize your templates to ([AddChannelTemplates](https://docs.optimove.com/api-usage-guide/#AddChannelTemplates) #2 above)
> -  For more details, please refer to our [Optimove docs site](https://docs.optimove.com/integrate-your-service-with-optimove/)
<br/>

----------
### <a id="bonus"></a>Bonus Integration Flow for Scheduled Campaigns: 
**Use Cases**:

1.  As an Optimove client, you wish to integrate Optimove with your promo/bonus system for pre-scheduled campaigns.
2.  As a third party vendor / middle-ware provider, you are interested in integrating a promo/bonus system with Optimove and allow Optimove clients to manage customer campaigns that also automatically grant bonuses, discounts, incentives, etc. to individual customers.
<p align="center"><img src="https://github.com/optimove-tech/Optimove-APIs/blob/ShayTest/API-Integrations/Bonus%20Integration%20Flow%20for%20Scheduled%20Campaigns%20-%20Execution.png?raw=true"></p>

>**Notes**: 
> -   For EventTypes (#1 above) refer to [RegisterEventListener](https://docs.optimove.com/api-usage-guide/#General_Functions_RegisterEventListener)
> -   Please contact the Product Integration Team to provide you with the exact Channel ID(s) you should register the listener ([RegisterEventListener](https://docs.optimove.com/api-usage-guide/#General_Functions_RegisterEventListener)) 
> - In order to have the promotions available for choosing within the campaign creation, please use [Add Promotions](https://docs.optimove.com/api-usage-guide/#External_System_Integration_Functions_AddPromotions)
>  - Once a notification to your listener is received for EventTypeID13,  pull the relevant details of the campaign using **both the CampaignID and ChannelID** received within the notification (#5 and #8 above). ([GetCustomerExecutionDetailsByCampaign](https://docs.optimove.com/api-usage-guide/#GetCustomerExecutionDetailsByCampaign) 
>  - For **multi-channel** campaigns, in order to avoid granting the promotion twice to the same user within the same campaign, filter the users across the different channels (#6 and #9 above).
>  -  For more details, please refer to our [Optimove docs site](https://academy.optimove.com/en/article/promotion-system-integration/)
<br/>

----------
### <a id="ce-flow"></a>Conditional Execution Bonus Flow: 
**Use Cases**: 

1.As an Optimove client, You may want to ensure that your campaign is sent only to customers for whom the promotion was already activated in your promo/bonus system.

2.As an Optimove client, You may want to verify the list of eligible customers for a creation promotion before it will be sent to them widely.

<p align="center"><img src="https://github.com/optimove-tech/Optimove-APIs/blob/ShayTest/API-Integrations/Conditional%20execution%20NEW%20.png?raw=true""> </p>

> **Notes**: 
> - This integration flow **supports only** pre-scheduled campaigns.
> - Event Type 5 should be register without channel id. 
> - The API payload you will receive is described in [RegisterEventListener](https://docs.optimove.com/api-usage-guide/#General_Functions_RegisterEventListener) under EventTypeID = 5
> - For more details, please refer to our [Optimove academy article](https://academy.optimove.com/en/article/promotion-system-integration#promotion-system-integration-for-scheduled-campaigns) under Flow 2
<br/>

----------

### <a id="bonusrt"></a>Bonus Integration Flow for Realtime Campaigns: 
**Use Cases**: 

1.  As an Optimove client, you wish to integrate Optimove with your promo/bonus system for realtime campaigns.
2.  As a third party vendor / middle-ware provider, you are interested in integrating a promo/bonus system with Optimove and allow Optimove clients to manage customer campaigns that also automatically grant bonuses, discounts, incentives, etc. to individual customers.

<p align="center"><img src="https://github.com/optimove-tech/Optimove-APIs/blob/ShayTest/API-Integrations/Bonus%20Integration%20Flow%20for%20Realtime%20Campaigns%20-%20Execution.png?raw=true"></p>

>**Notes**: 
> - This integration flow **supports** Optimove clients who have Optimove's [Server Side API](https://github.com/optimove-tech/Reporting-Server-Side-Custom-Events) or[Track & Trigger](https://docs.optimove.com/track-and-trigger/) add-on product running on their website, mobile native app **only**!
> - The API payload you will receive in realtime is described in [RegisterEventListener](https://docs.optimove.com/api-usage-guide/#General_Functions_RegisterEventListener) under EventTypeID = 11
> -   Please contact the Product Integration Team to provide you with the exact Channel ID you should register the realtime listener ([RegisterEventListener](https://docs.optimove.com/api-usage-guide/#General_Functions_RegisterEventListener))
> - In order to have the promotions available for choosing within the campaign creation, please use [Add Promotions](https://docs.optimove.com/api-usage-guide/#External_System_Integration_Functions_AddPromotions). Please note if the promotions were added under the pre-scheduled campaign flow, there is no need to add the same promotions again, they will already appear in the promotions drop-down for realtime campaigns.
> -  For more details, please refer to our [Optimove docs site](https://docs.optimove.com/integrate-your-service-with-optimove/)
<br/>

----------
