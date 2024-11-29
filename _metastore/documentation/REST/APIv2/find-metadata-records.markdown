---
title: Getting a List of Datacite Records of all Metadata Documents (API v2)
breadcrumbs: /metastore/documentation/REST/APIv2/Getting a List of all Datacite Records of all Metadata Documents
layout: default
description: A Research Data Repository Service for Managing Metadata Documents based on JSON or XML.
repository_url: https://github.com/kit-data-manager/metastore2
repository_name: kit-data-manager/metastore2
navigation_id: metastore_doc_rest_v2
---

# {{ page.title }}

If you want to obtain (current) datacite records of all metadata documents '/api/v2/metadata/' endpoint has to be called. 
Search will find all current datacite records.
There are some filters available which may be combined.
All filters for the datacite records are set via query parameters.
The following filters are allowed:

- id
- resourceId
- from
- until

[NOTE]
The header contains the field 'Content-Range" which displays delivered indices and the maximum number of available schema records. 
If there are more than 20 datacite records registered you have to provide page and/or size as additional query parameters.

- page: Number of the page you want to get **(starting with page 0)**
- size: Number of entries per page.

This may look like this:

{% capture my_include %}{% include_relative snippets/list-all-metadata-records/curl-request.md %}{% endcapture %}
{{ my_include | markdownify }}

HTTP-wise the call looks as follows: 

{% capture my_include %}{% include_relative snippets/list-all-metadata-records/http-request.md %}{% endcapture %}
{{ my_include | markdownify }}

As a result, you receive a list of metadata records.

{% capture my_include %}{% include_relative snippets/list-all-metadata-records/http-response.md %}{% endcapture %}
{{ my_include | markdownify }}

<style>
td, th {
   border: none!important;
}
</style>
|[<< PREVIOUS](update-metadata-record.html)| [NEXT >>](filter-metadata-records-by-id.html) |
|:----|----:|
| | |

