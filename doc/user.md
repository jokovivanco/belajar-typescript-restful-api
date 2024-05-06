# User API Spec

## Register User

Endpoint: POST /api/users

Request Body:

```json
{
  "username": "jokovic",
  "password": "secretpassword",
  "name": "Joko P"
}
```

Response Body (Success):

```json
{
  "data": {
    "username": "jokovic",
    "name": "Joko P"
  }
}
```

Response Body (Failed):

```json
{
  "errors": "Username must not blank"
}
```

## Login User

Endpoint: POST /api/users/login

Request Body:

```json
{
  "username": "jokovic",
  "password": "secretpassword"
}
```

Response Body (Success):

```json
{
  "data": {
    "username": "jokovic",
    "name": "Joko P",
    "token": "tokengeneratedfromUUID"
  }
}
```

Response Body (Failed):

```json
{
  "errors": "Username or password wrong"
}
```

## Get User

Endpoint: GET /api/users/current

Request Header:

- X-API-TOKEN: token

Request Body (Success):

```json
{
  "data": {
    "username": "jokovic",
    "name": "Joko P"
  }
}
```

Response Body (Failed):

```json
{
  "errors": "Unauthorized"
}
```

## Update User

Endpoint: PATCH /api/users/current

Request Header:

- X-API-TOKEN: token

Request Body:

```json
{
  "password": "secretpassword", // optional
  "name": "Joko P" // optional
}
```

Response Body (Success):

```json
{
  "data": {
    "username": "jokovic",
    "name": "Joko P"
  }
}
```

Response Body (Failed):

```json
{
  "errors": "Unauthorized"
}
```

## Logout User

Endpoint: DELETE /api/users/current

Request Header:

- X-API-TOKEN: token

Response Body (Success):

```json
{
  "data": "ok"
}
```

Response Body (Failed):

```json
{
  "errors": "Unauthorized"
}
```
