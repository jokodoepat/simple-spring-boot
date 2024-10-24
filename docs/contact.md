# Contact API Spec

## Create Contact

Endpoint : POST /api/contacts

Request Header :

- X-API-TOKEN : Token (Mandatory)

Request Body :

```json
{
  "firstName" : "Joko",
  "lastName" : "Kuncoro",
  "email" : "jokokuncoro@example.com",
  "phone" : "0899889998"
}
```

Response Body (Success, 200) :

```json
{
  "data": {
    "id" : "random-string",
    "firstName": "Joko",
    "lastName": "Kuncoro",
    "email": "jokokuncoro@example.com",
    "phone": "0899889998"
  }
}
```

Response Body (Unauthorized, 401) :

```json
{
  "errors" : "Unauthorized"
}
```

Response Body (Failed, 400) :

```json
{
  "errors" : "Email format invalid, phone format invalid, ..."
}
```

## Update Contact

Endpoint : PUT /api/contacts/{idContact}

Request Header :

- X-API-TOKEN : Token (Mandatory)

Request Body :

```json
{
  "firstName" : "Joko",
  "lastName" : "Kuncoro",
  "email" : "jokokuncoro@example.com",
  "phone" : "0899889998"
}
```

Response Body (Success, 200) :

```json
{
  "data": {
    "id" : "random-string",
    "firstName": "Joko",
    "lastName": "Kuncoro",
    "email": "jokokuncoro@example.com",
    "phone": "0899889998"
  }
}
```

Response Body (Failed, 400) :

```json
{
  "errors" : "Email format invalid, phone formar invalid, ..."
}
```

Response Body (Unauthorized, 401) :

```json
{
  "errors" : "Unauthorized"
}
```
## Get Contact

Endpoint : GET /api/contacts/{idContact}

Request Header :

- X-API-TOKEN : Token (Mandatory)

Response Body (Success) :

```json
{
  "data": {
    "id" : "random-string",
    "firstName": "Joko",
    "lastName": "Kuncoro",
    "email": "jokokuncoro@example.com",
    "phone": "0899889998"
  }
}
```

Response Body (Failed, 404) :

```json
{
  "errors" : "Contact is not found"
}
```

Response Body (Unauthorized, 401) :

```json
{
  "errors" : "Unauthorized"
}
```
## Search Contact

Endpoint : GET /api/contacts

Query Param :

- name : String, contact first name or last name, using like query, optional
- phone : String, contact phone, using like query, optional
- email : String, contact email, using like query, optional
- page : Integer, start from 0, default 0
- size : Integer, default 10

Request Header :

- X-API-TOKEN : Token (Mandatory)

Response Body (Success, 200) :

```json
{
  "data": [
    {
      "id": "random-string",
      "firstName": "Joko",
      "lastName": "Kuncoro",
      "email": "jokokuncoro@example.com",
      "phone": "0899889998"
    }
  ],
  "paging" : {
    "currentPage" : 0,
    "totalPage" : 10,
    "size" : 10
  }
}
```

Response Body (Failed, 401) :

```json
{
  "errors" : "Unauthorized"
}
```

## Remove Contact

Endpoint : DELETE /api/contacts/{idContact}

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
  "errors" : "Contact is not found"
}
```