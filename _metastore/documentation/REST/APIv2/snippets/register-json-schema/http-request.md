```http
POST /metastore/api/v2/schemas/ HTTP/1.1
Content-Type: multipart/form-data; boundary=6o2knFse3p53ty9dmcQvWAIx1zInP11uCfbm
Host: localhost:8040

--6o2knFse3p53ty9dmcQvWAIx1zInP11uCfbm
Content-Disposition: form-data; name=schema; filename=schema.json
Content-Type: application/json

{
    "$schema": "https://json-schema.org/draft/2020-12/schema",
    "$id": "http://www.example.org/schema/json",
    "type": "object",
    "title": "Json schema for tests",
    "default": {},
    "required": [
        "title"
    ],
    "properties": {
        "title": {
            "type": "string",
            "title": "Title",
            "description": "Title of object."
        }
    },
    "additionalProperties": false
}
--6o2knFse3p53ty9dmcQvWAIx1zInP11uCfbm
Content-Disposition: form-data; name=record; filename=schema-record4json.json
Content-Type: application/json

{"id":"my_first_json","identifier":null,"creators":[],"titles":[{"id":null,"value":"Title for my_first_json","titleType":null,"lang":null}],"publisher":null,"publicationYear":null,"resourceType":null,"subjects":[],"contributors":[],"dates":[],"relatedIdentifiers":[],"descriptions":[],"geoLocations":[],"language":null,"alternateIdentifiers":[],"sizes":[],"formats":[],"version":null,"rights":[],"fundingReferences":[],"lastUpdate":null,"state":null,"embargoDate":null,"acls":[]}
--6o2knFse3p53ty9dmcQvWAIx1zInP11uCfbm--
```