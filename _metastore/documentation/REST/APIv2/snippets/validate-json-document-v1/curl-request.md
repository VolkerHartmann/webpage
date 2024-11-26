```bash
 $ curl 'http://localhost:8040/metastore/api/v2/schemas/my_first_json/validate?version=1' -i -X POST \
    -H 'Content-Type: multipart/form-data' \
    -F 'document=@metadata-v2.json;type=application/json'

```