## Example 1: 
First time login, saving token in your cache and immediately calling an Optimove API from the cached token
![](https://github.com/optimoveproductintegration/Optimove-APIs/blob/master/Login-API/API%20Auth%20E1.jpg?raw=true)

----------
## Example 2: 
First time login, saving token in your cache and immediately calling an Optimove API from the cached token, then there is an idle for 20m or more which means you will need to re-login again (login + save to cache), followed by calling additional Optimove APIs.
![](https://github.com/optimoveproductintegration/Optimove-APIs/blob/master/Login-API/API%20Auth%20E2.jpg?raw=true)

----------
## Example 3a: 
First time login, saving token in your cache and immediately calling an Optimove API from the cached token, following by calling the login API before the token has been expired. You will get an error (#429) of too many request. Please do not call the login API unless the token has expired.
Please note: only 1 call per sec is allowed, otherwise #429 error will be sent.
![](https://github.com/optimoveproductintegration/Optimove-APIs/blob/master/Login-API/API%20Auth%20E3a.jpg?raw=true)

----------
## Example 3b: 
First time login, saving token in your cache and immediately calling an Optimove API from the cached token, then there is an idle for 20m or more and you try to call another Optimove APIA. You will get an error (#403) of that the token was expired. It means you will have to re-login again (login + save to cache), followed by calling additional Optimove APIs.
![](https://github.com/optimoveproductintegration/Optimove-APIs/blob/master/Login-API/API%20Auth%20E3b.jpg?raw=true)
