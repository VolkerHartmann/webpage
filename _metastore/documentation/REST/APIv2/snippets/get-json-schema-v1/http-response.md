```http
HTTP/1.1 200 OK
Content-Type: text/plain
Content-Length: 388
Accept-Ranges: bytes

{
  "$schema" : "https://json-schema.org/draft/2020-12/schema",
  "$id" : "http://www.example.org/schema/json",
  "type" : "object",
  "title" : "Json schema for tests",
  "default" : { },
  "required" : [ "title" ],
  "properties" : {
    "title" : {
      "type" : "string",
      "title" : "Title",
      "description" : "Title of object."
    }
  },
  "additionalProperties" : false
}

```