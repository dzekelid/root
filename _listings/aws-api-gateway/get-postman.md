{
  "info": {
    "name": "AWS API Gateway API Root Service",
    "_postman_id": "3afabd21-0c6b-447a-b555-c4236f31f208",
    "description": "Represents the root of the Amazon API Gateway control service.",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "Root",
      "item": [
        {
          "id": "1ff72a2a-0c34-4919-93fd-31895c3d3d38",
          "name": "apiGateway",
          "request": {
            "url": "http://example.com/api/?UnauthorizedException=UnauthorizedException",
            "method": "GET",
            "header": [
              {
                "key": "Authorization",
                "value": "Authorization",
                "description": "",
                "disabled": false
              },
              {
                "key": "Content-Type",
                "value": "Content-Type",
                "description": "",
                "disabled": false
              },
              {
                "key": "Host",
                "value": "Host",
                "description": "",
                "disabled": false
              },
              {
                "key": "X-Amz-Date",
                "value": "X-Amz-Date",
                "description": "",
                "disabled": false
              }
            ],
            "body": {
              "mode": "raw"
            },
            "description": "Represents the root of the Amazon API Gateway control service."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "9502ea27-c693-45b5-883a-3f296f71492e"
            }
          ]
        }
      ]
    }
  ]
}