```http
POST /metastore/api/v2/schemas/my_first_json/validate?version=1 HTTP/1.1
Content-Type: multipart/form-data; boundary=6o2knFse3p53ty9dmcQvWAIx1zInP11uCfbm
Host: localhost:8040

--6o2knFse3p53ty9dmcQvWAIx1zInP11uCfbm
Content-Disposition: form-data; name=document; filename=metadata-v3.json
Content-Type: application/json

{
"title": "My third JSON document",
"date": "2018-07-02",
}
--6o2knFse3p53ty9dmcQvWAIx1zInP11uCfbm--
```