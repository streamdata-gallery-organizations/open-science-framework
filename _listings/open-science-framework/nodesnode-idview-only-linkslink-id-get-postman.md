{
  "info": {
    "name": "Open Science Framework Retrieve a view only link",
    "_postman_id": "0fa5dec0-ea4b-4edc-9e22-c76d08b9bd04",
    "description": "Retrieves the details of a view only link on a node.\n####Returns\nReturns a JSON object with a `data` key containing the representation of the requested view only link, if the request is successful.\n\nIf the request is unsuccessful, an `errors` key containing information about the failure will be returned. Refer to the [list of error codes](#Introduction_error_codes) to understand why this request may have failed.\n####Permissions\n\nView only links on a node, public or private, are readable and writeable only by users that are administrators on the node.",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "Nodes",
      "item": [
        {
          "id": "17e22172-9a64-4f97-be55-7c8f7d1cd22a",
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
              "id": "9fcbc349-d3b8-4be0-a887-072350acd873"
            }
          ]
        },
        {
          "id": "544243f6-a89c-4bdb-aa50-ff8fb9a63dcb",
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
              "id": "372ce43b-1c4c-450d-8ecb-e619b0e3ebf4"
            }
          ]
        }
      ]
    }
  ]
}