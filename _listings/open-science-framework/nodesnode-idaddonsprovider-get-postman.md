{
  "info": {
    "name": "Open Science Framework Retrieve an addon",
    "_postman_id": "6f4fecee-08b4-416d-a16c-80401b9c3673",
    "description": "Retrieve details of an individual addon connected to this node.\n#### Permissions\nNodeSettings that are attached to public nodes will give read-only access to everyone. Private nodes require explicit read permission. Write and admin access are the same for public and private nodes. Administrators on a parent node have implicit read permissions for all child nodes.\nAny users with write or admin access to the node are able to deauthorize an enabled addon, but only the addon authorizer is able to change the configuration (i.e. selected folder) of an already-configured NodeSettings entity.\n#### Returns\nReturns a JSON object with a `data` key containing the details of the requested addon, if the request is successful.\n\nIf the request is unsuccessful, an `errors` key containing information about the failure will be returned. Refer to the [list of error codes](#Introduction_error_codes) to understand why this request may have failed.",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "Addons",
      "item": [
        {
          "id": "0711894b-3661-42d0-b032-3090cec78f92",
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
              "id": "2d9b8cf2-e7a1-4358-bd70-3683138649ac"
            }
          ]
        }
      ]
    },
    {
      "name": "Nodes",
      "item": [
        {
          "id": "77734b61-ea32-40d5-88aa-83297a193b3d",
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
              "id": "9d78f7e7-0b3b-44de-a9ed-a92fceed4399"
            }
          ]
        },
        {
          "id": "cb285baf-5f4e-4064-8776-8a6c517e1901",
          "name": "nodes_addon_read",
          "request": {
            "url": {
              "protocol": "http",
              "host": "test-api.osf.io",
              "path": [
                "v2",
                "nodes/:node_id/addons/:provider/"
              ],
              "variable": [
                {
                  "id": "node_id",
                  "value": "{}",
                  "type": "string"
                },
                {
                  "id": "provider",
                  "value": "{}",
                  "type": "string"
                }
              ]
            },
            "method": "GET",
            "body": {
              "mode": "raw"
            },
            "description": "Retrieve details of an individual addon connected to this node.\n#### Permissions\nNodeSettings that are attached to public nodes will give read-only access to everyone. Private nodes require explicit read permission. Write and admin access are the same for public and private nodes. Administrators on a parent node have implicit read permissions for all child nodes.\nAny users with write or admin access to the node are able to deauthorize an enabled addon, but only the addon authorizer is able to change the configuration (i.e. selected folder) of an already-configured NodeSettings entity.\n#### Returns\nReturns a JSON object with a `data` key containing the details of the requested addon, if the request is successful.\n\nIf the request is unsuccessful, an `errors` key containing information about the failure will be returned. Refer to the [list of error codes](#Introduction_error_codes) to understand why this request may have failed."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "7c4e0658-c9bd-4471-9837-9b3c4cd2d616"
            }
          ]
        }
      ]
    }
  ]
}