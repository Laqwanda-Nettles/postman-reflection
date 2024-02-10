# postman-reflection
## Day 1: Introduction to API
### Objective
Utilize Postman to send GET requests to the Pokémon API and understand the response structure. This assignment is designed to strengthen your skills in using Postman for API interaction and response analysis.  
![image](https://github.com/Laqwanda-Nettles/postman-reflection/assets/147118788/b2b11356-b348-44c5-9883-d51bd0824bc9)
![image](https://github.com/Laqwanda-Nettles/postman-reflection/assets/147118788/3123e538-d63f-48a3-a9f6-293705303467)
![image](https://github.com/Laqwanda-Nettles/postman-reflection/assets/147118788/67ed8676-0819-47a5-be31-da6a5959e2a4)
#### Postman
Using Postman, In My Workspace select new or +  to create a new request. Set the request type to GET, then enter the API URL for the Pokemon API followed by the specific endpoint of the data you want to retrieve. Ex.) https://pokeapi.co/api/v2/pokemon/squirtle/. Finally hit 'send' to send request.
#### Response Received
Pokemon Name: Squirtle  
Url Request: https://pokeapi.co/api/v2/pokemon/7 OR https://pokeapi.co/api/v2/pokemon/squirtle/  
The response included various details about Squirtle, such as abilities, base experience, height, weight, and types. This information was received as a JSON object. The object had array properties. For example, the abilities array contains two objects, each having an ability object with the properties name & url, a boolean stating if the ability is hidden, and a slot property with a value of a number.
## Day 2: Exploring the Weather API
### Objective
Gain hands-on experience with the Weather API by sending requests using Postman. Understand the significance of query parameters in API requests and document the process and findings.  
![image](https://github.com/Laqwanda-Nettles/postman-reflection/assets/147118788/b156d6bf-94df-4343-93bb-b7ded8470827)  
I used weatherapi.com, the request URL base: http://api.weatherapi.com/v1, then followed by /current.json to get the current weather or /forecast.json to receive the forcast in json. With the Weather API, the API can be displayed in both JSON and XML, so it's required to specify which format you're using. After the starting query "?", your API key follows.
#### Request Parameters Required
Key: API key  
q: followed by location, e.g., city name, zip, latitude & longitude, etc.  
days: only required if using the forecast API method.  
#### Response
If the required parameters are not in the URL, for example, if q=location is removed, it will throw 400 bad request status and an error message in JSON stating "Parameter q is missing.". If the format is missing—JSON or XML, a 404 not found status will appear.
##### Current Weather
![image](https://github.com/Laqwanda-Nettles/postman-reflection/assets/147118788/a686519a-d141-4d71-bd56-bdebbaaacd1b)  
The response showed a JSON object with two object properties: location & current.
##### Forecast
The response showed a JSON object with three object properties: location, current, and forecast. The forecast had one more required parameter compared to the current weather. The required parameter was days.
#### Query Parameters
Using the correct query parameters is crucial because it can directly affect the response you'll receive. Query parameters enable specific data to be retrieved and are sometimes required. Incorrect parameters may cause errors or undesired behavior.
## Day 3: API Collections
### Objective
Create a collection in Postman specifically for the weather API, and utilize a variable to manage the API key. Send a request to the weather API and document the entire process and the response received.  
![image](https://github.com/Laqwanda-Nettles/postman-reflection/assets/147118788/55de0c7b-1132-4792-a852-f2c33b5c87df)  
#### Creating A Collection
Click the collection tab under 'My Workspace', and when opened, click the + sign to create a new collection and edit the name of the new collection. Once these steps are done, you can click the three dots followed by the name of your collection to add requests. This can also be done by simply right-clicking on the name. On the collection home page, there is a variables tab where you can find your stored variable or create a variable to store.
#### Environment
![image](https://github.com/Laqwanda-Nettles/postman-reflection/assets/147118788/4b95c446-4ecd-4653-b8c0-59b5bb2332a6)  
After selecting the environment tab, click the + sign to create a new environment. Then add a variable name under the variable column and select the type: 'secret' or 'default'. Secret acts like an input with the type password; it will hide value. Whereas default, it will show the value in its entirety. After that, enter the value and save.
#### Sending Request
I created a new request in my Weather API Collection and used the variables I saved, such as baseUrl, which was saved directly in the collection's variables, & weatherApiKey, which was saved in my Weather API Environment. I provided the endpoint and required parameters needed for the request to go through. The benefit of using variables is their reusability and ease of management and updating.  
![image](https://github.com/Laqwanda-Nettles/postman-reflection/assets/147118788/9ddecf6a-31dc-4483-94aa-80a77aaca1c4)  
The response data was the same as the one manually typed. A JSON object containing two object properties: location and current.
## Day 4: Interacting with Github's API
### Objective
Utilize Postman to interact with GitHub's API by retrieving user information and creating a new repository. Document the entire process, including the request setup and the response in your README.md file, accompanied by appropriate screenshots.
#### Retrieving User Information
![image](https://github.com/Laqwanda-Nettles/postman-reflection/assets/147118788/e3706af8-c8e4-470e-bfe4-cf2137beabb5)  
After creating a new collection, I set the base URL to the variable baseUrl in the collection's variables tab. Then I created a new environment and saved my access token to a variable set to secret. I made sure to save it and set the environment to active. In my collection's authorization tab, I selected 'Bearer Token' and used the variable I saved in the environment tab as the token's value. Once all of this was done, I added a request using the baseUrl variable, followed by user. The authorization tab for this request was set to 'Inherit from parent'.
#### Creating a New Repository
![image](https://github.com/Laqwanda-Nettles/postman-reflection/assets/147118788/69122f45-bd56-422b-8a36-a7fb1d401420)  
The foundation was already set to create a new repository: the bearer token, base URL, & user. After creating a new request under the collection, I switch the request method from GET to POST.  
The URL: {{baseUrl}}user/repos.  
The authorization tab was set to 'Inherit from parent'. The only difference between retrieving info and creating a new repo was having to create a JSON object with the required parameters in the request's body tab. Once this was done and the request was sent, I received a 201 created status and the JSON object, which contained the name of the created repo, owner info, URL, description, etc.
## Day 5: Thunder Client
### Objective
The objective of this assignment is to replicate the tasks completed on Day 4, but this time using Thunder Client in VS Code. This will provide hands-on experience with an alternative API testing tool and offer insights into the differences and similarities between Thunder Client and Postman.  
#### Setting Up
Created a collection called Github API & an environment called Github. Saved access token to variable in the environment. In the collections settings, under the options tab, I saved the base URL. In the same settings under the Auth tab, I place the variable for my token. To go a step farther, in the settings environment tab, I attached the Github environment I created to the collection.
#### Retrieving User Information
![image](https://github.com/Laqwanda-Nettles/postman-reflection/assets/147118788/c0cc05b3-8b1d-41fe-bf86-c2866a296a14)  
With the steps above completed, I created a new request in the collection called 'User'. The request method was set to GET, and since the previous steps were taken, all I had to do was type the endpoint 'user' & hit send.  
#### Creating a Repository
![image](https://github.com/Laqwanda-Nettles/postman-reflection/assets/147118788/da8a09a2-72e7-4dca-b53e-87475d8d6d2f)  
Created a new request under the collection, set the request method to POST, and entered the endpoints 'user/repos'. Then I clicked the Body tab and typed the required parameters in JSON format. Once the request was sent, I received a 201 created status.
#### Thoughts on Thunder Client
It's convenient because of the ability to access it directly in VS Code. The steps were very similar to Postman, but the collection settings feature was nice. For example, you could plug in the base URL directly in the collection settings without having to create a variable for it. However, I prefer the auto-complete feature on Postman. In summary, I find both Postman & Thunder Client to be powerful tools for testing APIs.
