{
  "info": {
    "name": "Open Science Framework Root",
    "_postman_id": "d64f2984-402b-4ae4-9613-b4682ecbd051",
    "description": "Welcome to the Open Science Framework API. With this API you can access users, projects, components, logs, and files from the [Open Science Framework](https://osf.io/). The Open Science Framework (OSF) is a free, open-source service maintained by the [Center for Open Science](http://cos.io/).\n\n#### Returns\nA JSON object with `meta` and `links` keys.\n\nThe `meta` key contains information such as a welcome message from the API, the specified version of the request, and the full representation of the current user, if authentication credentials were provided in the request.\n\nThe `links` key contains links to the following entity collections: [addons](), [collections](), [institutions](#Institutions_institutions_list), [licenses](#Licenses_license_list), [metaschemas](), [nodes](#Nodes_nodes_list), [registrations](), [users](#Users_users_list)",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "Root",
      "item": [
        {
          "id": "cc05eb32-a5eb-4edf-8d8d-ee10beac1e38",
          "name": "base_read",
          "request": {
            "url": "http://test-api.osf.io/v2/",
            "method": "GET",
            "body": {
              "mode": "raw"
            },
            "description": "Welcome to the Open Science Framework API. With this API you can access users, projects, components, logs, and files from the [Open Science Framework](https://osf.io/). The Open Science Framework (OSF) is a free, open-source service maintained by the [Center for Open Science](http://cos.io/).\n\n#### Returns\nA JSON object with `meta` and `links` keys.\n\nThe `meta` key contains information such as a welcome message from the API, the specified version of the request, and the full representation of the current user, if authentication credentials were provided in the request.\n\nThe `links` key contains links to the following entity collections: [addons](), [collections](), [institutions](#Institutions_institutions_list), [licenses](#Licenses_license_list), [metaschemas](), [nodes](#Nodes_nodes_list), [registrations](), [users](#Users_users_list)"
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "6f93738f-2ad9-4800-9d14-ba2f02b38b14"
            }
          ]
        }
      ]
    }
  ]
}