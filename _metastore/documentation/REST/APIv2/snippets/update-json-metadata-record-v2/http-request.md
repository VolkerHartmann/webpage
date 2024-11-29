```http
PUT /metastore/api/v2/metadata/d9c917ee-160e-460c-b169-8f952ab505c7?version=1 HTTP/1.1
Content-Type: multipart/form-data; boundary=6o2knFse3p53ty9dmcQvWAIx1zInP11uCfbm
If-Match: "2079736072"
Host: localhost:8040

--6o2knFse3p53ty9dmcQvWAIx1zInP11uCfbm
Content-Disposition: form-data; name=record; filename=metadata-record4json-v2.json
Content-Type: application/json

{"id":"d9c917ee-160e-460c-b169-8f952ab505c7","identifier":{"id":3,"value":"(:tba)","identifierType":"DOI"},"creators":[{"id":3,"familyName":null,"givenName":"SELF","affiliations":[]}],"titles":[{"id":3,"value":"Title of first JSON metadata document","titleType":null,"lang":null}],"publisher":"SELF","publicationYear":"2024","resourceType":{"id":3,"value":"JSON_Metadata","typeGeneral":"MODEL"},"subjects":[],"contributors":[],"dates":[{"id":3,"value":"2024-11-25T13:50:06Z","type":"CREATED"}],"relatedIdentifiers":[{"id":2,"identifierType":"URL","value":"https://repo/anyResourceId","relationType":"IS_METADATA_FOR","scheme":null,"relatedMetadataScheme":null},{"id":3,"identifierType":"URL","value":"http://localhost:8040/metastore/api/v2/schemas/my_first_json?version=2","relationType":"HAS_METADATA","scheme":null,"relatedMetadataScheme":null}],"descriptions":[],"geoLocations":[],"language":null,"alternateIdentifiers":[{"id":3,"value":"d9c917ee-160e-460c-b169-8f952ab505c7","identifierType":"INTERNAL"}],"sizes":[],"formats":[],"version":"1","rights":[],"fundingReferences":[],"lastUpdate":"2024-11-25T13:50:06.577Z","state":"VOLATILE","embargoDate":null,"acls":[{"id":null,"sid":"guest","permission":"READ"},{"id":4,"sid":"SELF","permission":"ADMINISTRATE"}]}
--6o2knFse3p53ty9dmcQvWAIx1zInP11uCfbm
Content-Disposition: form-data; name=document; filename=metadata-v2.json
Content-Type: application/xml

{
"title": "My second JSON document",
"date": "2018-07-02"
}
--6o2knFse3p53ty9dmcQvWAIx1zInP11uCfbm--
```