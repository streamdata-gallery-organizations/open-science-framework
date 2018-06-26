{
  "info": {
    "name": "Open Science Framework List all nodes",
    "_postman_id": "6e6a55d0-dba4-48bf-a86d-4a8b0b9ee22a",
    "description": "A paginated list of nodes, representing projects and components, on the OSF.\n\nThe returned nodes are those which are public or which the user has access to view.\n\nThe returned nodes are sorted by their `date_modified`, with the most recently updated nodes appearing first.\n\nRegistrations cannot be accessed through this endpoint (use the [registrations](#Registrations_registrations_list) endpoints instead).\n#### Returns\nReturns a JSON object containing `data` and `links` keys.\n\nThe `data` key contains an array of 10 nodes. Each resource in the array is a separate node object and contains the full representation of the node, meaning additional requests to a node's detail view are not necessary.\n\nThe `links` key contains a dictionary of links that can be used for [pagination](#Introduction_pagination).\n\nThis request should never return an error.\n#### Filtering\nYou can optionally request that the response only include nodes that match your filters by utilizing the `filter` query parameter, e.g. https://api.osf.io/v2/nodes/?filter[title]=reproducibility.\n\nNodes may be filtered by their `id`, `title`, `category`, `description`, `public`, `tags`, `date_created`, `date_modified`, `root`, `parent`, `preprint`, and `contributors`.\n\nMost fields are string fields and will be filtered using simple substring matching. Public and preprint are boolean fields, and can be filtered using truthy values, such as **true**, **false**, **0** or **1**. Note that quoting true or false in the query will cause the match to fail.",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "Institutions",
      "item": [
        {
          "id": "85798859-1187-4a36-9ec5-d0b3e66753c6",
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
              "id": "8b84bb66-2cd0-4aec-b904-ad9944daf273"
            }
          ]
        }
      ]
    },
    {
      "name": "Nodes",
      "item": [
        {
          "id": "6d876c68-fba1-49a8-b3e8-efc1a3a65d9f",
          "name": "nodes_list",
          "request": {
            "url": "http://test-api.osf.io/v2/nodes/",
            "method": "GET",
            "body": {
              "mode": "raw"
            },
            "description": "A paginated list of nodes, representing projects and components, on the OSF.\n\nThe returned nodes are those which are public or which the user has access to view.\n\nThe returned nodes are sorted by their `date_modified`, with the most recently updated nodes appearing first.\n\nRegistrations cannot be accessed through this endpoint (use the [registrations](#Registrations_registrations_list) endpoints instead).\n#### Returns\nReturns a JSON object containing `data` and `links` keys.\n\nThe `data` key contains an array of 10 nodes. Each resource in the array is a separate node object and contains the full representation of the node, meaning additional requests to a node's detail view are not necessary.\n\nThe `links` key contains a dictionary of links that can be used for [pagination](#Introduction_pagination).\n\nThis request should never return an error.\n#### Filtering\nYou can optionally request that the response only include nodes that match your filters by utilizing the `filter` query parameter, e.g. https://api.osf.io/v2/nodes/?filter[title]=reproducibility.\n\nNodes may be filtered by their `id`, `title`, `category`, `description`, `public`, `tags`, `date_created`, `date_modified`, `root`, `parent`, `preprint`, and `contributors`.\n\nMost fields are string fields and will be filtered using simple substring matching. Public and preprint are boolean fields, and can be filtered using truthy values, such as **true**, **false**, **0** or **1**. Note that quoting true or false in the query will cause the match to fail."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "167ae68e-03ed-4d33-a2f0-ce81d7344ab8"
            }
          ]
        }
      ]
    }
  ]
}