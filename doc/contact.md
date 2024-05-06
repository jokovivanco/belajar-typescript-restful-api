# Contact API Spec

## Create Contact

Endpoint: POST /api/contacts

Request Header:

- X-API-TOKEN: token

Request Body:

```json
{
  "first_name": "Joko",
  "last_name": "Purwanto",
  "email": "jokopurwanto@example.com",
  "phone": "6285244651236"
}
```

Response Body (Success):

```json
{
  "data": {
    "id": 1,
    "first_name": "Joko",
    "last_name": "Purwanto",
    "email": "jokopurwanto@example.com",
    "phone": "6285244651236"
  }
}
```

Response Body (Failed):

```json
{
  "errors": "first_name must not blank"
}
```

## Get Contact

Endpoint: GET /api/contacts/:id

Request Header:

- X-API-TOKEN: token

Response Body (Success):

```json
{
  "data": {
    "id": 1,
    "first_name": "Joko",
    "last_name": "Purwanto",
    "email": "jokopurwanto@example.com",
    "phone": "6285244651236"
  }
}
```

Response Body (Failed):

```json
{
  "errors": "Contact is not found"
}
```

## Update Contact

Endpoint: PUT /api/contacts/:id

Request Header:

- X-API-TOKEN: token

Request Body:

```json
{
  "first_name": "Joko", // optional
  "last_name": "Purwanto", // optional
  "email": "jokopurwanto@example.com", // optional
  "phone": "6285244651236" // optional
}
```

Response Body (Success):

```json
{
  "data": {
    "id": 1,
    "first_name": "Joko",
    "last_name": "Purwanto",
    "email": "jokopurwanto@example.com",
    "phone": "6285244651236"
  }
}
```

Response Body (Failed):

```json
{
  "errors": "first_name must not blank"
}
```

## Remove Contact

Endpoint: DELETE /api/contacts/:id

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
  "errors": "Contact is not found"
}
```

## Search Contact

Endpoint: GET /api/contacts

Query Parameter:

- name: string, contact first name or last name, optional
- phone: string, contact phone, optional
- email: string, contact email, optional
- page: number, default 1
- size: number, default 10

Request Header:

- X-API-TOKEN: token

Response Body (Success):

```json
{
  "data": [
    {
      "id": 1,
      "first_name": "Joko",
      "last_name": "Purwanto",
      "email": "jokopurwanto@example.com",
      "phone": "6285244651236"
    },
    {
      "id": 2,
      "first_name": "Zack",
      "last_name": "Hawkins",
      "email": "zackhawkins@example.com",
      "phone": "6285294347377"
    }
  ],
  "paging": {
    "current_page": 1,
    "total_page": 10,
    "size": 10
  }
}
```

Response Body (Failed):

```json
{
  "errors": "Unauthorized"
}
```
