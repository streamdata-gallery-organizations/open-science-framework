{
  "info": {
    "name": "Open Science Framework Retrieve a view only link",
    "_postman_id": "3f2aed54-c7c1-4d83-aede-03f8924bd9a5",
    "description": "Retrieves the details of a view only link created from this registration.\n####Returns\nReturns a JSON object with a `data` key containing the representation of the requested view only link, if the request is successful.\n\nIf the request is unsuccessful, an `errors` key containing information about the failure will be returned. Refer to the [list of error codes](#Introduction_error_codes) to understand why this request may have failed.\n####Permissions\n\nView only links on a registration, public or private, are readable and writeable only by users that are administrators on the registration.",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "Nodes",
      "item": [
        {
          "id": "59b63ed5-11ce-49c8-a151-2b599297f4a9",
          "name": "nodes_view_only_links_list",
          "request": {
            "url": {
              "protocol": "http",
              "host": "test-api.osf.io",
              "path": [
                "v2",
                "nodes/:node_id/view_only_links/"
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
            "description": "List of view only links on a node.\n####Returns\nReturns a JSON object containing `data` and `links` keys.\n\nThe `data` key contains an array of up to 10 view only links. Each resource in the array is a view only link object.\n\nThe `links` key contains a dictionary of links that can be used for [pagination](#Introduction_pagination).\n\n####Permissions\n\nView only links on a node, public or private, are readable and writeable only by users that are administrators on the node.\n\n####Filtering\n\nYou can optionally request that the response only include view only links that match your filters by utilizing the `filter` query parameter, e.g. https://api.osf.io/v2/nodes/ezcuj/view_only_links/?filter[anonymous]=true.\n\nView Only Links may be filtered based on their `name`, `anonymous` and `date_created` fields. Possible comparison operators include 'gt' (greater than), 'gte'(greater than or equal to), 'lt' (less than) and 'lte' (less than or equal to). The date must be in the format YYYY-MM-DD and the time is optional."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "6a98bd95-f2f3-4242-8919-4645557e1c25"
            }
          ]
        },
        {
          "id": "85128374-8702-4fdf-b5eb-e5b6f8a21521",
          "name": "nodes_view_only_links_read",
          "request": {
            "url": {
              "protocol": "http",
              "host": "test-api.osf.io",
              "path": [
                "v2",
                "nodes/:node_id/view_only_links/:link_id/"
              ],
              "variable": [
                {
                  "id": "link_id",
                  "value": "{}",
                  "type": "string"
                },
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
            "description": "Retrieves the details of a view only link on a node.\n####Returns\nReturns a JSON object with a `data` key containing the representation of the requested view only link, if the request is successful.\n\nIf the request is unsuccessful, an `errors` key containing information about the failure will be returned. Refer to the [list of error codes](#Introduction_error_codes) to understand why this request may have failed.\n####Permissions\n\nView only links on a node, public or private, are readable and writeable only by users that are administrators on the node."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "77978e0b-5544-4835-89b2-0ebb398a10fd"
            }
          ]
        }
      ]
    },
    {
      "name": "Registrations",
      "item": [
        {
          "id": "348aa250-9efc-4e27-91e8-77a7a5747d98",
          "name": "registrations_view_only_links_list",
          "request": {
            "url": {
              "protocol": "http",
              "host": "test-api.osf.io",
              "path": [
                "v2",
                "registrations/:registration_id/view_only_links/"
              ],
              "variable": [
                {
                  "id": "registration_id",
                  "value": "{}",
                  "type": "string"
                }
              ]
            },
            "method": "GET",
            "body": {
              "mode": "raw"
            },
            "description": "A paginated list of view only links created for this registration.\n####Returns\nReturns a JSON object containing `data` and `links` keys.\n\nThe `data` key contains an array of up to 10 view only links. Each resource in the array is a view only link object.\n\nThe `links` key contains a dictionary of links that can be used for [pagination](#Introduction_pagination).\n\n####Permissions\n\nView only links on a registration, public or private, are readable and writeable only by users that are administrators on the registration.\n\n####Filtering\n\nYou can optionally request that the response only include view only links that match your filters by utilizing the `filter` query parameter, e.g. https://api.osf.io/v2/registrations/wu3a4/view_only_links/?filter[anonymous]=true.\n\nView Only Links may be filtered based on their `name`, `anonymous` and `date_created` fields. Possible comparison operators include 'gt' (greater than), 'gte'(greater than or equal to), 'lt' (less than) and 'lte' (less than or equal to). The date must be in the format YYYY-MM-DD and the time is optional."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "985c42bb-96a6-4c56-ba31-472d5fd2813d"
            }
          ]
        },
        {
          "id": "8c0894d3-87a0-4019-9f41-5ee372072dfb",
          "name": "registrations_view_only_links_read",
          "request": {
            "url": {
              "protocol": "http",
              "host": "test-api.osf.io",
              "path": [
                "v2",
                "registrations/:registration_id/view_only_links/:link_id/"
              ],
              "variable": [
                {
                  "id": "link_id",
                  "value": "{}",
                  "type": "string"
                },
                {
                  "id": "registration_id",
                  "value": "{}",
                  "type": "string"
                }
              ]
            },
            "method": "GET",
            "body": {
              "mode": "raw"
            },
            "description": "Retrieves the details of a view only link created from this registration.\n####Returns\nReturns a JSON object with a `data` key containing the representation of the requested view only link, if the request is successful.\n\nIf the request is unsuccessful, an `errors` key containing information about the failure will be returned. Refer to the [list of error codes](#Introduction_error_codes) to understand why this request may have failed.\n####Permissions\n\nView only links on a registration, public or private, are readable and writeable only by users that are administrators on the registration."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "26d8fb2d-e7c5-4dd2-82b8-010a96284671"
            }
          ]
        }
      ]
    }
  ]
}