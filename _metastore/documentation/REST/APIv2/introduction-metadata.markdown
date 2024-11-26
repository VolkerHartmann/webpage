---
title: Metadata Management (API v2)
breadcrumbs: /metastore/documentation/REST/APIv2/Metadata Management
layout: default
description: A Research Data Repository Service for Managing Metadata Documents based on JSON or XML.
repository_url: https://github.com/kit-data-manager/metastore2
repository_name: kit-data-manager/metastore2
navigation_id: metastore_doc_rest_v2
---

# {{ page.title }}

After registration of a schema metadata may be added to MetaStore.
In this section, the handling of metadata resources is explained. 
It all starts with creating your first metadata resource. The model of a datacite record is
similar to the record of the schema document:

``` 
{
  "id" : "...",
  "identifier" : {
    "value" : "(:tba)",
    "identifierType" : "DOI"
  },
  "creators" : [ {
    "givenName" : "..."
  } ],
  "titles" : [ {
    "value" : "..."
  } ],
  "publisher" : "...",
  "publicationYear" : "...",
  "resourceType" : {
    "value" : "...",
    "typeGeneral" : "..."
  },
  "dates" : [ {
    "value" : "...",
    "type" : "..."
  } ],
  "relatedIdentifiers" : [ {
    "value" : "...",
    "identifierType" : "...",
    "relationType" : "..."
  }} ],
  "alternateIdentifiers" : [ {
    "value" : "...",
    "identifierType" : "..."
  } ],
  "version" : "...",
  "rights": [
    {
      "schemeId": "",
      "schemeUri": ""
    }
  ],
  "lastUpdate" : "...",
  "state" : "...",
  "acls" : [ {
    "sid" : "...",
    "permission" : "..."
  } ]
}
``` 
At least the following elements have to be provided by the user: 

[point]
- title: Any title for the metadata document
- resourceType: 'XML_Metadata' or 'JSON_Metadata' and type 'MODEL'.
- relatedIdentifier/schema: Link to the related schema. (identifierType: INTERNAL and URL are supported, relationType: HAS_METADATA)
- relatedIdentifier/data: Link to the (data) resource. (identifierType: any, relationType: IS_METADATA_FOR)

In addition, ACL may be useful to make metadata editable by others. (This will be of interest while updating an existing metadata)

<style>
td, th {
   border: none!important;
}
</style>
|[<< PREVIOUS](validate-metadata-document.html)| [NEXT >>](register-metadata.html) |
|:----|----:|
| | |

