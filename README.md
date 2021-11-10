<div align="center">
  <img alt="KenzieHub" title="KenzieHub" src="./imagen/logo.svg" width="100px" />
  <h1>Galera Nerd</h1>
  <p>api created for study purposes at the Kenzie Academy Brazil educational institution</p>
</div>

---
the base url of the api and link.

Routes that require authorization must be informed in the request header the "Authorization" field, like this:

> Authorization: Bearer {token}

## **Endpoints**

## **USERS**

### **New Users**

**POST** /users

name, email, password and dev(true or false) are required in the request body :
```json
{
  "name": "useName",
  "email": "test@ndo.com",
  "password": "bestPassw0rd",
  "dev": true
}
```

The password is encrypted by bcryptjs. The response contains the JWT access token (expiration time of 1 hour) :

`RESPONSE FORMAT - STATUS 201`
```json
{
  "accessToken": "xxx.xxx.xxx",
  "user": {
    "email": "test@ndo.com",
    "name": "useName",
    "dev": true,
    "id": 1
  }
}
```

### **Login**

**POST** /login

email and password are required in the request body :
```json
{
  "email": "test@ndo.com",
  "password": "bestPassw0rd"
}
```

The password is encrypted by bcryptjs. The response contains the JWT access token (expiration time of 1 hour) :

`RESPONSE FORMAT - STATUS 201`
```json
{
  "accessToken": "xxx.xxx.xxx",
  "user": {
    "email": "test@ndo.com",
    "name": "useName",
    "dev": true,
    "id": 1
  }
}
```
### **User Edition**

**PATCH** /users/id

The value to be updated is mandatory in the request body :

_require authorization_
```json
{
  "name": "Tux"
}
```

The response contains the user with the updated values :

`RESPONSE FORMAT - STATUS 201`
```json
{
  "email": "test@ndo.com",
  "name": "Tux",
  "dev": true,
  "id": 1
}
```
### **User Deletion**

**DELETE** /users/id

_require authorization_

```
  A request body is not required.
```
---

## **Dev**

### **New Dev**

to make dev user you must have a user account with `dev: true`

**POST** /dev

userId, bio, contacts(is object), services(is array) and hourValue are required in the request body :

_require authorization_
```json
{
  "userId": 1,
  "bio": "bio",
  "contacts": {"email": "test@ndo.com", "linkedin": "https://link.com", "gitHub": "https://link.com"} ,
  "services": ["web site"],
  "hourValue": 20
}
```

the expected answer :

`RESPONSE FORMAT - STATUS 201`
```json
{
  "userId": 1,
  "bio": "bio",
  "contacts": {"email": "test@ndo.com", "linkedin": "https://link.com", "gitHub": "https://link.com"} ,
  "services": ["web site"],
  "hourValue": 20,
  "id": 1
}
```
### **Dev Edition**

**PATCH** /dev/id

The value to be updated is mandatory in the request body :

_require authorization_
```json
{
  "bio": "newBio"
}
```

The response contains the user with the updated values :

`RESPONSE FORMAT - STATUS 201`
```json
{
  "userId": 1,
  "bio": "newBio",
  "contacts": {"email": "test@ndo.com", "linkedin": "https://link.com", "gitHub": "https://link.com"} ,
  "services": ["services"],
  "hourValue": 20,
  "id": 1
}
```
### **Dev Deletion**

**DELETE** /dev/id

_require authorization_

```
  A request body is not required.
```
---
## **Feedbacks**

### **New Feedbacks**

**POST** /feedbacks

_require authorization_

rating from 0 to 5 in the questions attendance, price, recommendation, services(is array) and hourValue are required in the request body :
```json
{
  "attendance": 5,
  "price": 5,
  "recommendation": 5 ,
  "comment": "very good attendance",
  "devId": 1,
  "userId": 1
}
```

the expected answer :

`RESPONSE FORMAT - STATUS 201`
```json
{
  "attendance": 3,
  "price": 5,
  "recommendation": 5 ,
  "comment": "very good attendance",
  "devId": 1,
  "userId": 1,
  "id": 1
}
```
### **Feedbacks Edition**

**PATCH** /feedbacks/id

The value to be updated is mandatory in the request body :

_require authorization_
```json
{
  "attendance": 5
}
```

The response contains the user with the updated values :

`RESPONSE FORMAT - STATUS 201`
```json
{
  "attendance": 5,
  "price": 5,
  "recommendation": 5 ,
  "comment": "very good attendance",
  "devId": 1,
  "userId": 1,
  "id": 1
}
```
### **Feedbacks Deletion**

**DELETE** /feedbacks/id

_require authorization_

```
  A request body is not required.
```
---
## **Projects**

### **New Projects**

**POST** /projects

_require authorization_

status, budget, requestDescription, devId and userId are required in the request body :
```json
{
  "status": "production",
  "budget": "500.00" ,
  "requestDescription": "I need a clothing store",
  "devId": 1,
  "userId": 1
}
```

the expected answer :

`RESPONSE FORMAT - STATUS 201`
```json
{
  "status": "production",
  "budget": "500.00",
  "requestDescription": "I need a clothing store",
  "devId": 1,
  "userId": 1,
  "id": 1
}
```
### **Projects Edition**

**PATCH** /projects/id

The value to be updated is mandatory in the request body :

_require authorization_
```json
{
  "budget": "1000.00"
}
```

The response contains the user with the updated values :

`RESPONSE FORMAT - STATUS 201`
```json
{
  "status": "production",
  "budget": "1000.00",
  "requestDescription": "I need a clothing store",
  "devId": 1,
  "userId": 1,
  "id": 1
}
```
### **Projects Deletion**

**DELETE** /projects/id

_require authorization_

```
  A request body is not required.
```
---
