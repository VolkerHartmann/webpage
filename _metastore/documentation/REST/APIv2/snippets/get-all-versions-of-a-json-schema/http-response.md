```http
HTTP/1.1 200 OK
Content-Range: 0-1/2
Content-Type: application/json
Content-Length: 1829

[ {
  "id" : "my_first_json",
  "identifier" : {
    "id" : 1,
    "value" : "(:tba)",
    "identifierType" : "DOI"
  },
  "creators" : [ {
    "id" : 1,
    "givenName" : "SELF"
  } ],
  "titles" : [ {
    "id" : 1,
    "value" : "Title for my_first_json"
  } ],
  "publisher" : "SELF",
  "publicationYear" : "2024",
  "resourceType" : {
    "id" : 1,
    "value" : "JSON_Schema",
    "typeGeneral" : "MODEL"
  },
  "dates" : [ {
    "id" : 1,
    "value" : "2024-11-25T13:50:05Z",
    "type" : "CREATED"
  } ],
  "relatedIdentifiers" : [ {
    "id" : 1,
    "identifierType" : "URL",
    "value" : "http://localhost:8040/metastore/api/v2/metadata/my_first_json?version=1",
    "relationType" : "IS_NEW_VERSION_OF"
  } ],
  "alternateIdentifiers" : [ {
    "id" : 1,
    "value" : "my_first_json",
    "identifierType" : "INTERNAL"
  } ],
  "version" : "2",
  "lastUpdate" : "2024-11-25T13:50:05.941Z",
  "state" : "VOLATILE",
  "acls" : [ {
    "id" : 1,
    "sid" : "SELF",
    "permission" : "ADMINISTRATE"
  } ]
}, {
  "id" : "my_first_json",
  "identifier" : {
    "id" : 1,
    "value" : "(:tba)",
    "identifierType" : "DOI"
  },
  "creators" : [ {
    "id" : 1,
    "givenName" : "SELF"
  } ],
  "titles" : [ {
    "id" : 1,
    "value" : "Title for my_first_json"
  } ],
  "publisher" : "SELF",
  "publicationYear" : "2024",
  "resourceType" : {
    "id" : 1,
    "value" : "JSON_Schema",
    "typeGeneral" : "MODEL"
  },
  "dates" : [ {
    "id" : 1,
    "value" : "2024-11-25T13:50:05Z",
    "type" : "CREATED"
  } ],
  "alternateIdentifiers" : [ {
    "id" : 1,
    "value" : "my_first_json",
    "identifierType" : "INTERNAL"
  } ],
  "version" : "1",
  "lastUpdate" : "2024-11-25T13:50:05.753Z",
  "state" : "VOLATILE",
  "acls" : [ {
    "id" : 1,
    "sid" : "SELF",
    "permission" : "ADMINISTRATE"
  } ]
} ]
```