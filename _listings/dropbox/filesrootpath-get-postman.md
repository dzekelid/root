{
  "info": {
    "name": "Dropbox Content Downloads a file.",
    "_postman_id": "7a461582-3a5d-4349-b30d-b9d2cb641278",
    "description": "Downloads a file.\n\nThis method also supports [HTTP Range Retrieval Requests](http://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.35.2)\nto allow retrieving partial file contents.",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "Storage",
      "item": [
        {
          "id": "99cb4dca-d2bf-4740-a619-05ef2c30c4eb",
          "name": "downloads-a-filethis-method-also-supports-http-range-retrieval-requestshttpwwww3orgprotocolsrfc2616r",
          "request": {
            "url": {
              "protocol": "http",
              "host": "api-content.dropbox.com",
              "path": [
                "1",
                "files/:root/:path"
              ],
              "query": [
                {
                  "key": "rev",
                  "value": "%7B%7D",
                  "disabled": false
                }
              ],
              "variable": [
                {
                  "id": "path",
                  "value": "{}",
                  "type": "string"
                },
                {
                  "id": "root",
                  "value": "{}",
                  "type": "string"
                }
              ]
            },
            "method": "GET",
            "body": {
              "mode": "raw"
            },
            "description": "Downloads a file.\n\nThis method also supports [HTTP Range Retrieval Requests](http://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.35.2)\nto allow retrieving partial file contents."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "382ce6d9-0fbc-4f9d-b540-41852f7db7c8"
            }
          ]
        }
      ]
    }
  ]
}