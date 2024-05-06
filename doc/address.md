# Address API Spec

## Create Address

Endpoint: POST /api/contacts/:contactId/addresses

Request Header:

- X-API-TOKEN: token

Request Body:

```json
{
  "street": "Jl. Malioboro",
  "city": "Yogyakarta",
  "province": "Jawa Tengah",
  "country": "Indonesia",
  "postal_code": 72233
}
```

Response Body (Success):

```json
{
  "data": {
    "id": 1,
    "street": "Jl. Malioboro",
    "city": "Yogyakarta",
    "province": "Jawa Tengah",
    "country": "Indonesia",
    "postal_code": 72233
  }
}
```

Response Body (Failed):

```json
{
  "errors": "postal_code is required"
}
```

## Get Address

Endpoint: GET /api/contacts/:contactId/addresses/:addressId

Request Header:

- X-API-TOKEN: token

Response Body (Success):

```json
{
  "data": {
    "id": 1,
    "street": "Jl. Malioboro",
    "city": "Yogyakarta",
    "province": "Jawa Tengah",
    "country": "Indonesia",
    "postal_code": 72233
  }
}
```

Response Body (Failed):

```json
{
  "errors": "Address is not found"
}
```

## Update Address

Endpoint: PUT /api/contacts/:contactId/addresses/:addressId

Request Header:

- X-API-TOKEN: token

Request Body:

```json
{
  "street": "Jl. Malioboro", // optional
  "city": "Yogyakarta", // optional
  "province": "Jawa Tengah", // optional
  "country": "Indonesia", // optional
  "postal_code": 72233 // optional
}
```

Response Body (Success):

```json
{
  "data": {
    "id": 1,
    "street": "Jl. Malioboro",
    "city": "Yogyakarta",
    "province": "Jawa Tengah",
    "country": "Indonesia",
    "postal_code": 72233
  }
}
```

Response Body (Failed):

```json
{
  "errors": "postal_code is required"
}
```

## DELETE Address

Endpoint: DELETE /api/contacts/:contactId/addresses/:addressId

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
  "errors": "Address is not found"
}
```

## List Address

Endpoint: GET /api/contacts/:contactId/addresses

Request Header:

- X-API-TOKEN: token

Response Body (Success):

```json
{
  "data": [
    {
      "id": 1,
      "street": "Jl. Malioboro",
      "city": "Yogyakarta",
      "province": "Jawa Tengah",
      "country": "Indonesia",
      "postal_code": 72233
    },
    {
      "id": 2,
      "street": "Jl. Transmigrasi KM. 5",
      "city": "Tanah Bumbu",
      "province": "Kalimantan Selatan",
      "country": "Indonesia",
      "postal_code": 72230
    }
  ]
}
```

Response Body (Failed):

```json
{
  "errors": "Contact is not found"
}
```
