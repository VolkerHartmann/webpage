```http
POST /metastore/api/v2/metadata/ HTTP/1.1
Content-Type: multipart/form-data; boundary=6o2knFse3p53ty9dmcQvWAIx1zInP11uCfbm
Host: localhost:8040

--6o2knFse3p53ty9dmcQvWAIx1zInP11uCfbm
Content-Disposition: form-data; name=record; filename=metadata-record4json.json
Content-Type: application/json

{"id":null,"identifier":null,"creators":[],"titles":[{"id":null,"value":"Title of first JSON metadata document","titleType":null,"lang":null}],"publisher":null,"publicationYear":null,"resourceType":{"id":null,"value":"JSON_Metadata","typeGeneral":"MODEL"},"subjects":[],"contributors":[],"dates":[],"relatedIdentifiers":[{"id":null,"identifierType":"URL","value":"https://repo/anyResourceId","relationType":"IS_METADATA_FOR","scheme":null,"relatedMetadataScheme":null},{"id":null,"identifierType":"URL","value":"http://localhost:8040/metastore/api/v2/schemas/my_first_json?version=1","relationType":"HAS_METADATA","scheme":null,"relatedMetadataScheme":null}],"descriptions":[],"geoLocations":[],"language":null,"alternateIdentifiers":[],"sizes":[],"formats":[],"version":null,"rights":[],"fundingReferences":[],"lastUpdate":null,"state":null,"embargoDate":null,"acls":[]}
--6o2knFse3p53ty9dmcQvWAIx1zInP11uCfbm
Content-Disposition: form-data; name=document; filename=metadata.json
Content-Type: application/json

{
"title": "My first JSON document"
}
--6o2knFse3p53ty9dmcQvWAIx1zInP11uCfbm--

```