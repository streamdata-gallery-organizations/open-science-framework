{
  "info": {
    "name": "Open Science Framework List all nodes",
    "_postman_id": "8a422c09-ec11-4247-a0ed-3b0de0c130bf",
    "description": "The list of nodes which this view only link gives read-only access to.\n#### Permissions\nOnly project administrators may retrieve the nodes of a view only link. Attempting to retrieve a view only link without appropriate permissions will result in a 403 Forbidden response.\n#### Returns\nReturns a JSON object containing `data` and `links` keys.\nThe `data` key contains an array of up to 10 nodes. Each resource in the array is a separate node object and contains the full representation of the node, meaning additional requests to a node's detail view are not necessary.\n\nThe `links` key contains a dictionary of links that can be used for [pagination](#Introduction_pagination).\n\nIf the request is unsuccessful, an `errors` key containing information about the failure will be returned. Refer to the [list of error codes](#Introduction_error_codes) to understand why this request may have failed.",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "Nodes",
      "item": [
        {
          "id": "b7c9d90c-956d-4edf-b479-ff0e595e5901",
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
              "id": "d45dbd3a-c14b-4084-b7cb-a727ed16a639"
            }
          ]
        },
        {
          "id": "7d544106-afd0-4946-8a8c-80c80a136eca",
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
              "id": "0d6c7858-3bf7-44a3-b7f3-fb9788836e1e"
            }
          ]
        }
      ]
    },
    {
      "name": "Registrations",
      "item": [
        {
          "id": "72544e53-69ea-410a-ab8b-4beaf5915489",
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
              "id": "aee30419-0137-4790-866d-cdf0a9335247"
            }
          ]
        },
        {
          "id": "bf9c1e9a-d578-4c62-b96c-78e27d64d187",
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
              "id": "39fb063c-c65f-4159-993e-3d81774ffddb"
            }
          ]
        }
      ]
    },
    {
      "name": "View",
      "item": [
        {
          "id": "b47e204e-c95e-4813-8afe-507d601f6594",
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
              "id": "12e5b27f-be80-4c69-9499-f14edc1d82c5"
            }
          ]
        },
        {
          "id": "8879b3fd-6920-4ee3-a6ee-bf1fb147787a",
          "name": "view_only_links_node_list",
          "request": {
            "url": {
              "protocol": "http",
              "host": "test-api.osf.io",
              "path": [
                "v2",
                "view_only_links/:link_id/nodes/"
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
            "description": "The list of nodes which this view only link gives read-only access to.\n#### Permissions\nOnly project administrators may retrieve the nodes of a view only link. Attempting to retrieve a view only link without appropriate permissions will result in a 403 Forbidden response.\n#### Returns\nReturns a JSON object containing `data` and `links` keys.\nThe `data` key contains an array of up to 10 nodes. Each resource in the array is a separate node object and contains the full representation of the node, meaning additional requests to a node's detail view are not necessary.\n\nThe `links` key contains a dictionary of links that can be used for [pagination](#Introduction_pagination).\n\nIf the request is unsuccessful, an `errors` key containing information about the failure will be returned. Refer to the [list of error codes](#Introduction_error_codes) to understand why this request may have failed."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "9ef53f43-258e-4981-816e-dba063946977"
            }
          ]
        }
      ]
    }
  ]
}