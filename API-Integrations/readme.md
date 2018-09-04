## Integrate Your Service with Optimove - Best Practices

- [Pre-scheduled Flow](#pre-flow)
- [Realtime Flow](#rt-flow)
<br/>

### <a id="pre-flow"></a>Pre-Scheduled Flow: 
**Use Case**: You are an Optimove client / third party vendor/partner who is interested in using Optimove to automatically send customer campaigns via your marketing platform, or you wish to integrate an external service with Optimove and act as the middleware.

<p align="center"><img src="https://github.com/optimove-tech/Optimove-APIs/blob/master/API-Integrations/Integrate%20Your%20Service%20-%20Pre-Scheduled%20-%20Client%20Execution%20Flow.png?raw=true"></p>

>**Notes**: 
> -   For API Authentication (#1 above) best practice refer to -   [Login API best practice & use cases](https://github.com/optimoveproductintegration/Optimove-APIs/tree/master/Login-API)
> -   For EventTypes (#2 above) refer to [RegisterEventListener](https://docs.optimove.com/api-usage-guide/#General_Functions_RegisterEventListener)
> -   Please contact the Product Integration Team who will provide your with the exact Channel ID you should register the listener ([RegisterEventListener](https://docs.optimove.com/api-usage-guide/#General_Functions_RegisterEventListener)), in order to synchronize your templates to ([AddChannelTemplates](https://docs.optimove.com/api-usage-guide/#AddChannelTemplates) #3 above)
> -  For more details, please see refer to our [Optimove docs site](https://docs.optimove.com/integrate-your-service-with-optimove/)
<br/>
----------
### <a id="rt-flow"></a>Realtime Flow: 
**Use Case**: You are an Optimove client who is interested in using Optimove to automatically send your customers realtime campaigns based on Optimove [Web](https://github.com/optimove-tech/Web-SDK-Integration-Guide) / [Mobile](https://github.com/optimove-tech/Mobile-SDK-Integration-Guide) SDK trigger via your marketing platform, or you wish to integrate an external service with Optimove and act as the middleware.
<p align="center"><img src="https://github.com/optimove-tech/Optimove-APIs/blob/master/API-Integrations/Integrate%20Your%20Service%20-%20Realtime%20-%20Client%20Execution%20Flow.png?raw=true"></p>

>**Notes**: 
> - This integration flow **supports** Optimove clients who have Optimove's [Track & Trigger](https://docs.optimove.com/track-and-trigger/) add-on product running on their website or mobile native app **only**!
> -   For API Authentication (#1 above) best practice refer to -   [Login API best practice & use cases](https://github.com/optimoveproductintegration/Optimove-APIs/tree/master/Login-API)
> - The API payload you’ll receive in realtime is described in [RegisterEventListener](https://docs.optimove.com/api-usage-guide/#General_Functions_RegisterEventListener) using EventTypeID = 11
> -   Please contact the Product Integration Team who will provide your with the exact Channel ID you should register the realtime listener ([RegisterEventListener](https://docs.optimove.com/api-usage-guide/#General_Functions_RegisterEventListener)), in order to synchronize your templates to ([AddChannelTemplates](https://docs.optimove.com/api-usage-guide/#AddChannelTemplates) #3 above)
> -  For more details, please see refer to our [Optimove docs site](https://docs.optimove.com/integrate-your-service-with-optimove/)
