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
