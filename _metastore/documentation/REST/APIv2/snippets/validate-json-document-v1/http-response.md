```http
HTTP/1.1 422 Unprocessable Entity
Content-Type: application/problem+json
Content-Length: 322

{
  "type" : "about:blank",
  "title" : "Unprocessable Entity",
  "status" : 422,
  "detail" : "400 BAD_REQUEST \"Error validating json!\n$: Eigenschaft 'date' ist im Schema nicht definiert und das Schema lässt keine zusätzlichen Eigenschaften zu\"",
  "instance" : "/metastore/api/v2/schemas/my_first_json/validate"
}

```