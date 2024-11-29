---
title: Updating Datacite Record of a Metadata Document (API v2)
breadcrumbs: /metastore/documentation/REST/APIv2/Updating Datacite Record of a Metadata Document (edit ACL entries)
layout: default
description: A Research Data Repository Service for Managing Metadata Documents based on JSON or XML.
repository_url: https://github.com/kit-data-manager/metastore2
repository_name: kit-data-manager/metastore2
navigation_id: metastore_doc_rest_v2
---

# {{ page.title }}

The following example shows the update of the metadata record. As mentioned before the
ETag is needed:

``` 
metadata-record4json-v2.json:
{
  "id": "d5439ccf-af4c-4727-b45b-1aa8b949d60e",
  [...]
  "relatedIdentifiers": [
    [...]
    {
      "id": 1,
      "identifierType": "URL",
      "value": "http://localhost:8040/metastore/api/v2/schemas/my_first_json?version=2",
      "relationType": "HAS_METADATA"
    }
  ],
  [...]
  "acls": [
    [...]
    {
      "sid": "guest",
      "permission": "READ"
    }
  ]
}
``` 

``` 
metadata-v2.json:
{
"title": "My second JSON document",
"date": "2018-07-02"
}
``` 
{% capture my_include %}{% include_relative snippets/update-json-metadata-record-v2/curl-request.md %}{% endcapture %}
{{ my_include | markdownify }}

You can see, that only the ACL entry for "guest" was added. All other properties are still the same. HTTP-wise the call looks as follows: 

{% capture my_include %}{% include_relative snippets/update-json-metadata-record-v2/http-request.md %}{% endcapture %}
{{ my_include | markdownify }}

You will get the new metadata record with the additional ACL entry. Version number of record was incremented by one and 'lastUpdate' was also modified by the server.
{% capture my_include %}{% include_relative snippets/update-json-metadata-record-v2/http-response.md %}{% endcapture %}
{{ my_include | markdownify }}

You will get the updated datacite record with the following changes:
- new schema (version)
- an additional ACL entry
- 'version' of record was incremented by one
- 'lastUpdate' was also modified by the server.

<style>
td, th {
   border: none!important;
}
</style>
|[<< PREVIOUS](get-metadata-record.html)| [NEXT >>](find-metadata-records.html) |
|:----|----:|
| | |

