{
  "info": {
    "name": "Open Science Framework List all view only links",
    "_postman_id": "91dfe182-fdbf-48ed-a0d3-98cfe930a0c4",
    "description": "A paginated list of view only links created for this registration.\n####Returns\nReturns a JSON object containing `data` and `links` keys.\n\nThe `data` key contains an array of up to 10 view only links. Each resource in the array is a view only link object.\n\nThe `links` key contains a dictionary of links that can be used for [pagination](#Introduction_pagination).\n\n####Permissions\n\nView only links on a registration, public or private, are readable and writeable only by users that are administrators on the registration.\n\n####Filtering\n\nYou can optionally request that the response only include view only links that match your filters by utilizing the `filter` query parameter, e.g. https://api.osf.io/v2/registrations/wu3a4/view_only_links/?filter[anonymous]=true.\n\nView Only Links may be filtered based on their `name`, `anonymous` and `date_created` fields. Possible comparison operators include 'gt' (greater than), 'gte'(greater than or equal to), 'lt' (less than) and 'lte' (less than or equal to). The date must be in the format YYYY-MM-DD and the time is optional.",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "Nodes",
      "item": [
        {
          "id": "ee0f720e-c19c-4607-a714-c647322e224e",
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
              "id": "7d143e77-8cf9-4846-a629-2b4798f705dd"
            }
          ]
        },
        {
          "id": "2fb481d5-79bf-4d5a-b34e-03ae0b9f7e53",
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
              "id": "58321c35-7cba-4e17-acf7-d792782696f5"
            }
          ]
        }
      ]
    },
    {
      "name": "Registrations",
      "item": [
        {
          "id": "d3b237b9-6bbe-49cd-9118-5c9a2f6cc008",
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
              "id": "269e53d3-f7d0-43c8-ad01-3bc95032227c"
            }
          ]
        }
      ]
    }
  ]
}