# User Api Spec

## Register User API

Endpoint : POST /api/users

Request Body :

```json
{
  "username" : "vs",
  "password" : "secret",
  "name" : "Vergie Sky"
}
```

Response Body Success :

```json
{
  "data": {
    "username" : "vs",
    "name" : "Vergie Sky"
  }
}
```

Response Body Error :

```json
{
  "errors" : "Username already registered"
}
```

## Login User API

Endpoint : POST /api/users/login

Request Body :

```json
{
  "username" : "vs",
  "password" : "secret"
}
```

Response Body Success :

```json
{
  "data" : {
    "token" : "unique-token" 
  }
}
```

Response Body Error :

```json
{
  "errors" : "Username or password is wrong"
  
}
```

## Update User API

Endpoint : PATCH /api/users/current

Headers :
- Authorization : token

Request Body :

```json
{
  "name" : "Vergie Sky", // opsional
  "password" : "new password" // opsional
}
```

Response Body Success :

```json
{
  "data" : {
    "username" : "vs",
    "name" : "Vergie Sky again"
  }
}
```

Response Body Error :

```json
{
  "errors" : "Name length max 100"
}
```

## Get User API

Endpoint : GET /api/users/current

Headers :
- Authorization : token

Response Body Success:

```json
{
  "data": {
    "username": "vs",
    "name" : "Vergie Sky"
  }
}
```

Response Body Error:

```json
{
  "errors" : "Unauthorized"
}
```

## Logout User API

Endpoint : DELETE /api/users/logout

Headers :
- Authorization : token

Response Body Success :

```json
{
  "data" : "OK"
}
```

Response Body Error:

```json
{
  "errors": "Unauthorized"
}
```