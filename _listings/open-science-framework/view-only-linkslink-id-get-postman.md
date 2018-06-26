{
  "info": {
    "name": "Open Science Framework Retrieve a view only link",
    "_postman_id": "367bef09-fe84-46f0-87dd-5aa6a4aa6238",
    "description": "Retrieves details about a specific view only link.\n####Permissions\nOnly project administrators may retrieve the details of a view only link. Attempting to retrieve a view only link without appropriate permissions will result in a 403 Forbidden response.\n#### Returns\nReturns a JSON object with a `data` key containing the representation of the requested view only link, if the request is successful.\nIf the request is unsuccessful, an `errors` key containing information about the failure will be returned. Refer to the [list of error codes](#Introduction_error_codes) to understand why this request may have failed.",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "Nodes",
      "item": [
        {
          "id": "7148cd31-c10f-4a57-8e3d-bfff9c208a77",
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
              "id": "6ef42b3c-5c4f-4bb9-8d3b-30704d100b20"
            }
          ]
        },
        {
          "id": "4ce84f2f-e679-4c59-8701-c6a273cb28d5",
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
              "id": "95df2c0e-15b3-4ecc-b611-769229f065b7"
            }
          ]
        }
      ]
    },
    {
      "name": "Registrations",
      "item": [
        {
          "id": "49ce2140-7070-4699-bb40-fbdfd4a1cb29",
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
              "id": "17a13fb6-43a9-4b4d-91c6-04d77958e166"
            }
          ]
        },
        {
          "id": "80526c7a-71a9-40e0-9b8a-af1c112888b1",
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
              "id": "63a661d6-31ce-4607-8100-b9b23633248d"
            }
          ]
        }
      ]
    },
    {
      "name": "View",
      "item": [
        {
          "id": "4cd5fadd-b945-4ce5-9295-6c3378631296",
          "name": "view_only_links_read",
          "request": {
            "url": {
              "protocol": "http",
              "host": "test-api.osf.io",
              "path": [
                "v2",
                "view_only_links/:link_id/"
              ],
              "variable": [
                {
                  "id": "link_id",
                  "value": "{}",
                  "type": "string"
                }
              ]
            },
            "method": "GET",
            "body": {
              "mode": "raw"
            },
            "description": "Retrieves details about a specific view only link.\n####Permissions\nOnly project administrators may retrieve the details of a view only link. Attempting to retrieve a view only link without appropriate permissions will result in a 403 Forbidden response.\n#### Returns\nReturns a JSON object with a `data` key containing the representation of the requested view only link, if the request is successful.\nIf the request is unsuccessful, an `errors` key containing information about the failure will be returned. Refer to the [list of error codes](#Introduction_error_codes) to understand why this request may have failed."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "a1300076-b62a-4240-891a-2cfc8f5baf73"
            }
          ]
        }
      ]
    }
  ]
}