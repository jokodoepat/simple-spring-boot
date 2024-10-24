# Address API Spec

## Create Address

Endpoint : POST /api/contacts/{idContact}/addresses

Request Header :

- X-API-TOKEN : Token (Mandatory)

Request Body :

```json
{
  "street" : "Jalan apa",
  "city" : "Kota",
  "province" : "provinsi",
  "country" : "Negara",
  "postalCode" : "12313"
}
```

Response Body (Success, 200) :

```json
{
  "data" : {
    "id" : "randomstring",
    "street" : "Jalan apa",
    "city" : "Kota",
    "province" : "provinsi",
    "country" : "Negara",
    "postalCode" : "12313"
  }
}
```

Response Body (Failed, 404) :

```json
{
  "errors" : "Contact is not found"
}
```

## Update Address

Endpoint : PUT /api/contacts/{idContact}/addresses/{idAddress}

Request Header :

- X-API-TOKEN : Token (Mandatory)

Request Body :

```json
{
  "street" : "Jalan apa",
  "city" : "Kota",
  "province" : "provinsi",
  "country" : "Negara",
  "postalCode" : "12313"
}
```

Response Body (Success, 200) :

```json
{
  "data" : {
    "id" : "randomstring",
    "street" : "Jalan apa",
    "city" : "Kota",
    "province" : "provinsi",
    "country" : "Negara",
    "postalCode" : "12313"
  }
}
```

Response Body (Failed, 404) :

```json
{
  "errors" : "Address is not found"
}
```

## Get Address

Endpoint : GET /api/contacts/{idContact}/addresses/{idAddress}

Request Header :

- X-API-TOKEN : Token (Mandatory)

Response Body (Success, 200) :

```json
{
  "data" : {
    "id" : "randomstring",
    "street" : "Jalan apa",
    "city" : "Kota",
    "province" : "provinsi",
    "country" : "Negara",
    "postalCode" : "12313"
  }
}
```

Response Body (Failed, 404) :

```json
{
  "errors" : "Address is not found"
}
```

## Remove Address

Endpoint : DELETE /api/contacts/{idContact}/addresses/{idAddress}

Request Header :

- X-API-TOKEN : Token (Mandatory)

Response Body (Success, 200) :

```json
{
  "data" : "OK"
}
```

Response Body (Failed, 404) :

```json
{
  "errors" : "Address is not found"
}
```

## List Address

Endpoint : GET /api/contacts/{idContact}/addresses

Request Header :

- X-API-TOKEN : Token (Mandatory)

Response Body (Success, 200) :

```json
{
  "data": [
    {
      "id": "randomstring",
      "street": "Jalan apa",
      "city": "Kota",
      "province": "provinsi",
      "country": "Negara",
      "postalCode": "12313"
    }
  ]
}
```

Response Body (Failed, 404) :

```json
{
  "errors" : "Contact is not found"
}
```