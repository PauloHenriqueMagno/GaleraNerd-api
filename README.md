<div align="center">
  <img alt="KenzieHub" title="KenzieHub" src="https://kenzie.com.br/images/logoblue.svg" width="100px" />
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
