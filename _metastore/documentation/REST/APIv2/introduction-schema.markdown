---
title: Schema Registration and Management (API v2)
breadcrumbs: /metastore/documentation/REST/APIv2/introduction schema
layout: default
description: A Research Data Repository Service for Managing Metadata Documents based on JSON or XML.
repository_url: https://github.com/kit-data-manager/metastore2
repository_name: kit-data-manager/metastore2
navigation_id: metastore_doc_rest_v2
---

# {{ page.title }}

In this first section, the handling of json schema resources is explained. It all starts with creating your first json schema resource. The model of a datacite record looks like this:
``` json
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
At least the following elements are expected to be provided by the user: 

-   id: A unique label for the schema.
-   title: Any title for the schema.

In addition, ACL may be useful to make schema readable/editable by others. This will be of interest while accessing/updating an existing
schema.(if authorization is enabled)

<style>
td, th {
   border: none!important;
}
</style>
|[<< PREVIOUS](index.html)| [NEXT >>](register-schema.html) |
|:----|----:|
| | |
