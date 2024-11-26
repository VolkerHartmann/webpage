---
title: Filter Datacite Records of Metadata Documents by Related Resource (API v2)
breadcrumbs: /metastore/documentation/REST/APIv2/Filter Datacite Records of Metadata Documents by Related Resource
layout: default
description: A Research Data Repository Service for Managing Metadata Documents based on JSON or XML.
repository_url: https://github.com/kit-data-manager/metastore2
repository_name: kit-data-manager/metastore2
navigation_id: metastore_doc_rest_v2
---

# {{ page.title }}

If you want to find all records belonging to an external resource. MetaStore may 
hold multiple metadata documents per resource. 

Command line:
{% capture my_include %}{% include_relative snippets/find-json-metadata-record-resource/curl-request.md %}{% endcapture %}
{{ my_include | markdownify }}

HTTP-wise the call looks as follows: 

{% capture my_include %}{% include_relative snippets/find-json-metadata-record-resource/http-request.md %}{% endcapture %}
{{ my_include | markdownify }}

You will get the current version metadata record. 
{% capture my_include %}{% include_relative snippets/find-json-metadata-record-resource/http-response.md %}{% endcapture %}
{{ my_include | markdownify }}

<style>
td, th {
   border: none!important;
}
</style>
|[<< PREVIOUS](filter-metadata-records-by-related-id.html)| [NEXT >>](filter-metadata-records-by-date.html) |
|:----|----:|
| | |

