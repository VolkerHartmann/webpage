---
title: Getting a Schema Document (API v2)
breadcrumbs: /metastore/documentation/REST/APIv2/Getting a Schema Document
layout: default
description: A Research Data Repository Service for Managing Metadata Documents based on JSON or XML.
repository_url: https://github.com/kit-data-manager/metastore2
repository_name: kit-data-manager/metastore2
navigation_id: metastore_doc_rest
---

# {{ page.title }}

For obtaining accessible metadata schemas you also have to provide the 'schemaId'.
For accessing schema document you have to provide 'application/xml' as 'Accept' header. 

{% capture my_include %}{% include_relative snippets/get-json-schema-document/curl-request.md %}{% endcapture %}
{{ my_include | markdownify }}

In the actual HTTP request there is nothing special. You just access the path of the resource using the base path and the 'schemaId'.

{% capture my_include %}{% include_relative snippets/get-json-schema-document/http-request.md %}{% endcapture %}
{{ my_include | markdownify }}

As a result, you receive the JSON schema send before. 

{% capture my_include %}{% include_relative snippets/get-json-schema-document/http-response.md %}{% endcapture %}
{{ my_include | markdownify }}

<style>
td, th {
   border: none!important;
}
</style>
|[<< PREVIOUS](get-schema-record.html)| [NEXT >>](update-schema.html) |
|:----|----:|
| | |

