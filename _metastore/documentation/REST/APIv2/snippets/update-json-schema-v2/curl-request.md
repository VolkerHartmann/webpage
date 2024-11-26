```bash
$ curl 'http://localhost:8040/metastore/api/v2/schemas/my_first_json' -i -X PUT \
    -H 'Content-Type: multipart/form-data' \
    -H 'If-Match: "855670887"' \
    -F 'schema=@schema-v2.json;type=application/json'
```