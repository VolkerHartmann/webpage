```http
HTTP/1.1 201 Created
Location: http://localhost:8040/metastore/api/v2/metadata/d9c917ee-160e-460c-b169-8f952ab505c7?version=1
ETag: "2079736072"
Content-Type: application/json
Content-Length: 1206

{
  "id" : "d9c917ee-160e-460c-b169-8f952ab505c7",
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
    "value" : "Title of first JSON metadata document"
  } ],
  "publisher" : "SELF",
  "publicationYear" : "2024",
  "resourceType" : {
    "id" : 3,
    "value" : "JSON_Metadata",
    "typeGeneral" : "MODEL"
  },
  "dates" : [ {
    "id" : 3,
    "value" : "2024-11-25T13:50:06Z",
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
    "value" : "http://localhost:8040/metastore/api/v2/schemas/my_first_json?version=1",
    "relationType" : "HAS_METADATA"
  } ],
  "alternateIdentifiers" : [ {
    "id" : 3,
    "value" : "d9c917ee-160e-460c-b169-8f952ab505c7",
    "identifierType" : "INTERNAL"
  } ],
  "version" : "1",
  "lastUpdate" : "2024-11-25T13:50:06.577Z",
  "state" : "VOLATILE",
  "acls" : [ {
    "id" : 4,
    "sid" : "SELF",
    "permission" : "ADMINISTRATE"
  } ]
}

```