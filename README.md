# postman-api <img src="https://voyager.postman.com/logo/postman-logo-icon-orange.svg" title="Postman" alt="Postman" width="35" height="35"/>   <img src="https://github.com/devicons/devicon/blob/master/icons/javascript/javascript-original.svg" title="JavaScript" alt="JavaScript" width="35" height="35"/>

## About
This repo contains the Postman collection that I implemented in Postman desktop and exported as .json file to demonstrate my experience in API testing using Postman. The collection can be found [here](https://github.com/anvoqa/postman-api/blob/main/Contact%20List%20API%20Test.postman_collection.json).

The Application Under Test (AUT) is the Contact List App: https://thinking-tester-contact-list.herokuapp.com/

The API documentation can be found here: https://documenter.getpostman.com/view/4012288/TzK2bEa8#intro

In addtion, before actually implementing the tests, I also developed the test plan to list out what tests will be done, the goal of each test, details of implementation and the expeced results. The test plan can be found [here](https://docs.google.com/spreadsheets/d/1zww2tnybj55bBrq6z0RN7tWUhzfckas3QCLJlhOE5gY/edit?usp=sharing).

### End to End Flow
1. Send **POST** request to register an account
2. Send **POST** request to login to the registred account and get the logged in token to be used in later requests
3. Send **GET** request to get user profile
4. Send **PATCH** request to partially update user (e.g. First Name)
5. Send **POST** request to create a new contact
6. Send **GET** request to get the contact list
7. Send **GET** request to get a specific contact
8. Send **PUT** request to update a contact
9. Send **PATCH** request to partially update a contact
10. Send **DELETE** request to delete a contact
11. Send **DELETE** contact to delete the user  

## 📖Knowledge📖
- Use Postman to create **POST, GET, PUT, PATCH, DELETE** requests and write tests to veriy **status code** and **data in body** of responses
- Use **dynamic variables** to generate random test data so that tests can be run many times without conflict and failing
- Use `pm` object to get, set collection variables in Pre-request Script, Body and Tests
- Use `Postman.nextRequest()` to set the order of requests when running collection
- Use **Monitor** to schedule the collection to run once a week on a specific date/time and send email notification when there are failures
- Use **Newman** to run the collection in **CLI**, and **newman html extra report** to generate test report when running test using Newman
- Use **Performance** feature of postman to run the performance of end to end test flow and view the performance metrics

## How to run the collection
### With Postman Desktop App
- Install Postman app
- Download the collection "**Contact List API Test.postman_collection.json**" from this project
- Import the collection to Postman app
- Run the collection

### With Newman using CLI
- Install Newman `npm install -g newman` (remember to install Node.js to use npm)
- Run the collection using the command `newman run "Contact List API Test.postman_collection.json"

### Generate test report with htmlextra
- Install htmlextra reporter: `npm install -g newman-reporter-htmlextra`
- Run the collection using the command `newman run "Contact List API Test.postman_collection.json" --reporters cli,htmlextra`
- The report will be generated in the newman folder which is the same location as postman collection

![image](https://github.com/anvoqa/postman-api/assets/128540316/493e4feb-7438-477c-888f-81b2f4b67bd5)


## Performance testing using Postman
Postman has just introduced Performance Testing recently. It provide ability to run the entire collection by the pre-defined concurrent virtual users within a set period of time.

<img width="668" alt="image" src="https://github.com/anvoqa/postman-api/assets/128540316/9ef9c284-f21f-4853-9a3c-a25a9218219e">

While the tests are running, user can view the real time report showing the trend of the performance as well as the metrics of each individual request

<img width="761" alt="image" src="https://github.com/anvoqa/postman-api/assets/128540316/5ee1fafb-6784-4bbb-aa88-2d2e742ada6b">

User can also check the error rate and when error happens

<img width="761" alt="image" src="https://github.com/anvoqa/postman-api/assets/128540316/dca1b621-e879-4fc7-8c37-ccbab7a03b2b">

