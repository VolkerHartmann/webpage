```bash
$ curl 'http://localhost:8040/metastore/api/v2/metadata/d9c917ee-160e-460c-b169-8f952ab505c7?version=1' -i -X PUT \
    -H 'Content-Type: multipart/form-data' \
    -H 'If-Match: "2079736072"' \
    -F 'record=@metadata-record4json-v2.json;type=application/json' \
    -F 'document=@metadata-v2.json;type=application/json'
```