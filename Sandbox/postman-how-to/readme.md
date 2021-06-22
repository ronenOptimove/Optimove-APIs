## Optimove API collection with Postman - How To Guide

### Prerequisite
If you don't already have **Postman** yes, please [download](https://www.getpostman.com/downloads/) one for Windows/Mac/Linux.
<hr>

### How To Video Clip
[![IMAGE ALT TEXT HERE](https://img.youtube.com/vi/9xyKygHlKqg/0.jpg)](https://www.youtube.com/watch?v=9xyKygHlKqg)

<hr>

### Step 1: 

- Note: We have two different collections. One for Optimove clients and the other for third parties. If you are a client, you have access to all our API library. If you are third party, there are limited APIs you can access. Please choose the correct one.
- - API Collection for **Optimove Clients Only**: [![Run in Postman](https://run.pstmn.io/button.svg)](https://god.postman.co/run-collection/3b61190890163aebdce1?action=collection%2Fimport#?env%5BSandbox-api%20endpoint%5D=W3sia2V5IjoiQVBJX1VSTCIsInZhbHVlIjoic2FuZGJveC1hcGkub3B0aW1vdmUubmV0IiwiZW5hYmxlZCI6dHJ1ZX0seyJrZXkiOiJBdXRoVG9rZW4iLCJ2YWx1ZSI6IkZqZGdIMGM3RV9WNlBySzI5VEw3WExiVEw2LTFTY0lHIiwiZW5hYmxlZCI6dHJ1ZX1d)

- -  API Collection for **Third Parties Only**: [![Run in Postman](https://run.pstmn.io/button.svg)](https://app.getpostman.com/run-collection/78828d908da727e45f77#?env%5BSandbox-api%20endpoint%5D=W3siZGVzY3JpcHRpb24iOnsiY29udGVudCI6IiIsInR5cGUiOiJ0ZXh0L3BsYWluIn0sInZhbHVlIjoic2FuZGJveC1hcGkub3B0aW1vdmUubmV0Iiwia2V5IjoiQVBJX1VSTCIsImVuYWJsZWQiOnRydWV9LHsidmFsdWUiOiJGamRnSDBjN0VfVjZQcksyOVRMN1hMYlRMNi0xU2NJRyIsImtleSI6IkF1dGhUb2tlbiIsImVuYWJsZWQiOnRydWV9XQ==)
 - Windows: This will take you to: Choose "Postman for Windows" 
 - This will open your Postman software
<hr>
   
### Step 2: 
You will see the Optimove Postman Collection created for you "(Clients Only) Optimove APIs Postman Examples"
 <p align="left"><img src="https://github.com/optimove-tech/Optimove-APIs/blob/master/Sandbox/postman-how-to/Screenshot_122.jpg?raw=true"></p>  
<hr>

### Step 3: 
 If you open the Login API (or any API from the list), you will see Global Variables in the URL and Headers:
 
 - **API_URL**: This will be the endpoint (sandbox/production ones)
 - **Content-Type**: application/json value will be populated
 - **Accept**: application/json value will be populated

Leave this as they are, we will populate the values in future steps.

 <p align="left"><img src="https://github.com/optimove-tech/Optimove-APIs/blob/master/Sandbox/postman-how-to/Screenshot_1.jpg?raw=true"></p> 
 <hr>

### Step 4: 
If you go to the "Body" section, you will see additional Global Variables:
 
 - **LoginUserName**: This will be replaced with the API username value
 - **LoginPassword**: This will be replaced with the API password value

Leave this as they are, we will populate the values in future steps.

 <p align="left"><img src="https://github.com/optimove-tech/Optimove-APIs/blob/master/Sandbox/postman-how-to/Screenshot_2.jpg?raw=true"></p> 
<hr>

### Step 5: 
This is where you choose the endpoint that will populate "API_URL".

 <p align="left"><img src="https://github.com/optimove-tech/Optimove-APIs/blob/master/Sandbox/postman-how-to/Screenshot_3.jpg?raw=true"></p> 
<hr>

### Step 6: 
Click on the cogwheel at the top right corner. it will take you to the Global Variables section.

 <p align="left"><img src="https://github.com/optimove-tech/Optimove-APIs/blob/master/Sandbox/postman-how-to/Screenshot_4.jpg?raw=true"></p> 
<hr>

### Step 7: 
Let's start populating the Global Variables: LoginUserName, LoginPassword, Content-Type, and Accept.

- **Variables**: Add the names as shown in the image below.
- **Initial Value**: Add the names as shown in the image below.
	- LoginUserName: Put the username you were given by the Product Integration Team
	- LoginPassword: Put the password you were given by the Product Integration Team
	- Content-Type: Add the value as shown in the image below.
	- Accept: Add the value as shown in the image below.
- **Current Value**: Add the names as shown in the image below.
	- Repeat as above "Initial Value"

When done, click on the Save button.

 <p align="left"><img src="https://github.com/optimove-tech/Optimove-APIs/blob/master/Sandbox/postman-how-to/Screenshot_6.jpg?raw=true"></p> 
<hr>

### Step 8: 
To see and edit these values, click on the (eye) button at the top right corner. It should look something like the image below.

The ONLY values you should be changing if requested are:
- LoginUserName Current Value
- LoginPassword Current Value 

Do not change the API_URL or AuthToken at any time. This is populated automatically. Everything else stays the same.

 <p align="left"><img src="https://github.com/optimove-tech/Optimove-APIs/blob/master/Sandbox/postman-how-to/Screenshot_7.jpg?raw=true"></p> 
<hr>

### Step 9: 
As mentioned above, these should not be changed, as they are modified automatically through the postman code.

 <p align="left"><img src="https://github.com/optimove-tech/Optimove-APIs/blob/master/Sandbox/postman-how-to/Screenshot_8.jpg?raw=true"></p> 
<hr>

### Step 10: 
Now go back to the Login API and click on "SEND". 
You only have to SEND Login API every time you go into Postman and use Optimove APIs.

You should be seeing the output with the AuthToken. No need to copy/paste it. If you go back to the (eye) button, you will see the AuthToken value is changed automatically.

Now you are ready to use all other APIs.
