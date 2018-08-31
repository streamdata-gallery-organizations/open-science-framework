{
  "info": {
    "name": "Open Science Framework List all affiliated nodes",
    "_postman_id": "fcfcb843-a189-437b-85ba-7298fa9f1d7d",
    "description": "A paginated list of all nodes affiliated with an institution.\n#### Versioning\nAs of version `2.2`, affiliated components (in addition to affiliated top-level projects) are returned from this endpoint.\n#### Returns\nReturns a JSON object containing `data` and `links` keys.\n\nThe `data` key contains an array of 10 nodes. Each resource in the array is a separate nodes object.\n\nThe `links` key contains a dictionary of links that can be used for [pagination](#Introduction_pagination).\n\nIf the request is unsuccessful, an `errors` key containing information about the failure will be returned. Refer to the [list of error codes](#Introduction_error_codes) to understand why this request may have failed.\n#### Filtering\nYou can optionally request that the response only include nodes that match your filters by utilizing the `filter` query parameter, e.g. https://api.osf.io/v2/institutions/cos/nodes?filter[title]=science.\n\nNodes may be filtered by their `id`, `title`, `description`, `public`, `tags`, `category`, `date_created`, `date_modified`, `root`, `parent`, `contributors`, and `preprint`",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "Institutions",
      "item": [
        {
          "id": "c4a3ac49-f99c-41c1-9167-8dd734e8844c",
          "name": "institutions_node_list",
          "request": {
            "url": {
              "protocol": "http",
              "host": "test-api.osf.io",
              "path": [
                "v2",
                "institutions/:institution_id/nodes/"
              ],
              "variable": [
                {
                  "id": "institution_id",
                  "value": "{}",
                  "type": "string"
                }
              ]
            },
            "method": "GET",
            "body": {
              "mode": "raw"
            },
            "description": "A paginated list of all nodes affiliated with an institution.\n#### Versioning\nAs of version `2.2`, affiliated components (in addition to affiliated top-level projects) are returned from this endpoint.\n#### Returns\nReturns a JSON object containing `data` and `links` keys.\n\nThe `data` key contains an array of 10 nodes. Each resource in the array is a separate nodes object.\n\nThe `links` key contains a dictionary of links that can be used for [pagination](#Introduction_pagination).\n\nIf the request is unsuccessful, an `errors` key containing information about the failure will be returned. Refer to the [list of error codes](#Introduction_error_codes) to understand why this request may have failed.\n#### Filtering\nYou can optionally request that the response only include nodes that match your filters by utilizing the `filter` query parameter, e.g. https://api.osf.io/v2/institutions/cos/nodes?filter[title]=science.\n\nNodes may be filtered by their `id`, `title`, `description`, `public`, `tags`, `category`, `date_created`, `date_modified`, `root`, `parent`, `contributors`, and `preprint`"
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "a0f87552-b406-4df6-984b-f8aec704e951"
            }
          ]
        }
      ]
    }
  ]
}