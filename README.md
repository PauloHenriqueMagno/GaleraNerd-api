<div align="center">
  <img alt="KenzieHub" title="KenzieHub" src="https://kenzie.com.br/images/logoblue.svg" width="100px" />
  <h1>Galera Nerd</h1>
  <p>api created for study purposes at the Kenzie Academy Brazil educational institution</p>
</div>

---
## **Endpoints**

the base url of the api and link.

---
### **USERS**

####**New Users**

**POST** /users

email and password are required in the request body :
```json
{
  "name": "useName",
  "email": "test@ndo.com",
  "password": "bestPassw0rd",
  "dev": boolean
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

