#### You can check this API here:
[Heroku jobs-api](https://jobs-api-herokuapp.herokuapp.com/)

#### Setup

1. Setup .env in the root
2. Setup JWT_LIFETIME to your .env, recommended value is 30d (for how long the JWT token will be valid)
3. Setup JWT_SECRET to your .env, recommended value is 256-bit encryption key

#### Database Connection

1. Add MONGO_URI to your .env with correct value


#### Then run that in terminal

```bash
npm install && npm start
```



#### Routers

- auth.js
- jobs.js

#### User Model

Email validation done using that regex

```regex
/^(([^<>()[\]\\.,;:\s@"]+(\.[^<>()[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/
```

#### Register User

- Validate - name, email, password - with Mongoose
- Hash Password (with bcryptjs)
- Save User
- Generate JWT Token
- Send Response with Token

#### Login User

- Validate - email, password - in controller
- If email or password is missing, throw BadRequestError
- Find User
- Compare Passwords
- If no user or password does not match, throw UnauthenticatedError
- If correct, generate Token
- Send Response with Token

#### This Mongoose errors were handled manually:

- Validation Errors
- Duplicate (Email)
- Cast Error

#### Security used

- helmet
- cors
- xss-clean
- express-rate-limit

#### Swagger UI
- Used to create API documentation


