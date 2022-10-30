# Note:
First of all I apologize because I have zero experiences with JAVA so I change all the repository with my own. <br/>
I used node JS for backend, mongo DB as database, and Angular for Frontend app it can be accesed from my_test folder.<br/>

# Setup
1. Clone the repository
2. Install Node JS (v18.12.0)
3. Install Angular
4. Install mongoDB
    
# Running the tests
There are two folder inside my_test folder Server and Client Please navigate to ecah folder and run the test with:
```sh 
npm install -g typescript (to install typescript)
npm install (to install the package)
npm start ( to run the server and client)
```


# Note:
- I did not made the code from the scracht by myself I took my old project, tutorial, and others sample project especially on frontend side <br/>


## User Stories

### In Identity Domain, as a User I :
- can register
  - get ok status with valid payload :white_check_mark
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
