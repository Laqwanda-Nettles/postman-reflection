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
