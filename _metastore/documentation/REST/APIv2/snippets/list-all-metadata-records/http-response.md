```http
HTTP/1.1 200 OK
Content-Range: 0-0/1
Content-Type: application/json
Content-Length: 1480

[ {
  "id" : "23dd1d7d-f4fa-40ad-a846-0a2c50b06399",
  "identifier" : {
    "id" : 3,
    "value" : "(:tba)",
    "identifierType" : "DOI"
  },
  "creators" : [ {
    "id" : 3,
    "givenName" : "SELF"
  } ],
  "titles" : [ {
    "id" : 3,
    "value" : "Title of first XML metadata document"
  } ],
  "publisher" : "SELF",
  "publicationYear" : "2024",
  "resourceType" : {
    "id" : 3,
    "value" : "XML_Metadata",
    "typeGeneral" : "MODEL"
  },
  "dates" : [ {
    "id" : 3,
    "value" : "2024-11-25T13:50:12Z",
    "type" : "CREATED"
  } ],
  "relatedIdentifiers" : [ {
    "id" : 2,
    "identifierType" : "URL",
    "value" : "https://repo/anyResourceId",
    "relationType" : "IS_METADATA_FOR"
  }, {
    "id" : 3,
    "identifierType" : "URL",
    "value" : "http://localhost:8040/metastore/api/v2/schemas/my_first_xsd?version=2",
    "relationType" : "HAS_METADATA"
  }, {
    "id" : 4,
    "identifierType" : "URL",
    "value" : "http://localhost:8040/metastore/api/v2/metadata/23dd1d7d-f4fa-40ad-a846-0a2c50b06399?version=1",
    "relationType" : "IS_NEW_VERSION_OF"
  } ],
  "alternateIdentifiers" : [ {
    "id" : 3,
    "value" : "23dd1d7d-f4fa-40ad-a846-0a2c50b06399",
    "identifierType" : "INTERNAL"
  } ],
  "version" : "2",
  "lastUpdate" : "2024-11-25T13:50:12.678Z",
  "state" : "VOLATILE",
  "acls" : [ {
    "id" : 5,
    "sid" : "guest",
    "permission" : "READ"
  }, {
    "id" : 4,
    "sid" : "SELF",
    "permission" : "ADMINISTRATE"
  } ]
} ]
```