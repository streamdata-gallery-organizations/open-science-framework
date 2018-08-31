{
  "info": {
    "name": "Open Science Framework List all addons",
    "_postman_id": "2d551e3d-0b4c-44c1-8349-3fa5b7dc8e0d",
    "description": "A paginated list of addons connected to the given node or project.\n#### Returns\nReturns a JSON object containing `data` and `links` keys.\n\nThe `data` key contains an array of at most 10 addon objects. Each resource in the array is a separate addon object and contains the full representation of the addon, meaning additional requests to a addon's detail view are not necessary.\n\nThe `links` key contains a dictionary of links that can be used for [pagination](#Introduction_pagination).",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "Addons",
      "item": [
        {
          "id": "4c13bb57-a99a-4c47-a647-640a6786a71c",
          "name": "addons_list",
          "request": {
            "url": "http://test-api.osf.io/v2/addons/",
            "method": "GET",
            "body": {
              "mode": "raw"
            },
            "description": "A paginated list of addons configurable with the OSF\n#### Returns\nReturns a JSON object containing `data` and `links` keys.\n\nThe `data` key contains an array of up to 10 addons. Each resource in the array is a separate addon object.\n\nThe `links` key contains a dictionary of links that can be used for [pagination](#Introduction_pagination).\n\nThis request should never return an error."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "4d3fc1c3-83a7-4284-a432-480d80947d96"
            }
          ]
        }
      ]
    },
    {
      "name": "Nodes",
      "item": [
        {
          "id": "905f3eab-f3dd-453c-ae68-049a02e457f9",
          "name": "nodes_addons_list",
          "request": {
            "url": {
              "protocol": "http",
              "host": "test-api.osf.io",
              "path": [
                "v2",
                "nodes/:node_id/addons/"
              ],
              "variable": [
                {
                  "id": "node_id",
                  "value": "{}",
                  "type": "string"
                }
              ]
            },
            "method": "GET",
            "body": {
              "mode": "raw"
            },
            "description": "A paginated list of addons connected to the given node or project.\n#### Returns\nReturns a JSON object containing `data` and `links` keys.\n\nThe `data` key contains an array of at most 10 addon objects. Each resource in the array is a separate addon object and contains the full representation of the addon, meaning additional requests to a addon's detail view are not necessary.\n\nThe `links` key contains a dictionary of links that can be used for [pagination](#Introduction_pagination)."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "7a738fc8-dfaa-451b-8e55-023b76de8063"
            }
          ]
        }
      ]
    }
  ]
}