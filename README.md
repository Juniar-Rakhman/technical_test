# Assignment:
Your task is to create a backend service (REST API) for a trello clone app with domain driven approach. <br/>
Below is an example of a UI for the board page of the app.<br/>

| to do | in progress | review | test  | deploy | done  |
|-------|-------------|--------|-------|--------|-------|
| task1 |             |        | task3 |        |       |
|       | task 2      |        |       |        |       |
|       |             |        |       |        | task4 |

It contains the trello board with multiple columns representing task's statuses.<br/>
The user can add, modify (moving from 1 column to another), or delete task.<br/>
To access the board page, the user have to be authenticated by the system using Oauth2. <br/>

<b>Please fork this repository to your own github account and create a pull request when done.</b>

# Test duration: 1 week (7 days)

# Assessment points
- [x] REST API routing design
- [x] Application modelling and abstraction skill
- [x] Quality assessment with unit testing and functional API test
- [ ] Creation of Web UI (optional)

# Setup

1. Clone the repository
2. Install nodejs
3. Install docker and docker-compose
4. Run `npm install` in node folder (Manual Install)
    
# Running the tests
Please take a look at the integration tests in: node/tests/<br/>
After all the required tools are installed. Run the following command to execute the tests:
```
npm test
```
After running the tests you should see that some tests have passed and some have failed.<br/>
Please fix the failed tests by creating the necessary endpoints and business logic.<br/>
Make sure the tests that was once passed will still pass.<br/>

# Note:
- Even though we are using Java and Spring in this codebase, feel free to use any programming language or framework of your own choice. <br/>
- Feel free to replace existing MongoDB with a database of your own choice. <br/>
- The integration tests are using [testcontainers](https://www.testcontainers.org/) and testcontainers have been forked in multiple programming languages:
  - [go](https://golang.testcontainers.org/)
  - [node](https://github.com/testcontainers/testcontainers-node)
  - [java]([testcontainers](https://www.testcontainers.org/))
  - [rust](https://github.com/testcontainers/testcontainers-rs)

Feel free to rewrite the integration test in any of the above language if you feel it is necessary <br/>
You do not have to follow the existing project structure, feel free to implement your own or rewrite the entire source directory if need to. <br/>

Here are the user stories that need to be fulfilled: <br/>

## User Stories

### In Identity Domain, as a User I :
- can register
  - get ok status with valid payload
  - get error with invalid payload
- can login
  - get new token pair (access & refresh token) with valid payload
  - get error with invalid payload
- can refresh
  - get new token pair with valid refresh token
  - session invalidated when refresh token is invalid (simulate stolen token)
  - not able to refresh after session is invalidated
- can logout
  - session invalidated when logout endpoint is called

### In Board Domain. as a User I :
- can create new board
  - get ok status with valid payload. User becomes the board admin
  - get error with invalid payload
- can load existing board
  - get valid result when fetching existing board
  - get empty result when fetching non-existing board
- can update existing board (rename, update description, etc)
  - get ok status when updating board with valid payload
  - get error when updating with invalid payload
- can delete existing board
  - get ok status when deleting existing board
  - get error when deleting non-existing board
- can share with other user
  - get ok status when sharing board with existing user
  - get error when sharing board with non-existing user

### In Column domain, as a User I :
- Can create new column
  - get ok status with valid payload.
  - get error with invalid payload.
- can update existing column (rename, change position)
  - get ok status with valid payload.
  - get error with invalid payload.
- can remove existing column
  - get ok status with valid columnId
  - get error with invalid columnId

### In Task Domain, as a User I :
- can create new task
  - get ok status with valid payload
  - get error with invalid payload
- can update task
  - get ok status with valid payload
  - get error with invalid payload
- can delete task
  - get ok status with valid Id
  - get error with invalid Id
