{
  "info": {
    "name": "Open Science Framework Retrieve an addon account",
    "_postman_id": "8bbc809d-5d6a-4e83-a106-17ad59435ccc",
    "description": "Retrieves the details of an addon account\n\n#### Permissions\n\nAddon accounts are visible only to the user that authorized the account.\n\n####Returns\nReturns a JSON object with a `data` key containing the representation of the requested addon account, if the request was successful.\n\nIf the request is unsuccessful, an `errors` key containing information about the failure will be returned. Refer to the [list of error codes](#Introduction_error_codes) to understand why this request may have failed.",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "Users",
      "item": [
        {
          "id": "37c4ae1b-f246-4f1c-9283-41c3568cdbe8",
          "name": "Users_addon_accounts_list",
          "request": {
            "url": {
              "protocol": "http",
              "host": "test-api.osf.io",
              "path": [
                "v2",
                "users/:user_id/addons/:provider/accounts/"
              ],
              "variable": [
                {
                  "id": "provider",
                  "value": "{}",
                  "type": "string"
                },
                {
                  "id": "user_id",
                  "value": "{}",
                  "type": "string"
                }
              ]
            },
            "method": "GET",
            "body": {
              "mode": "raw"
            },
            "description": "A paginated list of addon accounts authorized by this user.\n\n#### Permissions\n\nAddon accounts are visible only to the user that authorized the account.\n\n#### Returns\nReturns a JSON object containing `data` and `links` keys.\n\nThe `data` key contains an array of at most 10 addon account objects. Each resource in the array is a separate  addon account object and contains the full representation of the addon account.\n\nThe `links` key contains a dictionary of links that can be used for [pagination](#Introduction_pagination)."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "e9585a54-c32c-446b-b269-fb98619e3931"
            }
          ]
        },
        {
          "id": "4a3dfa47-978c-4c20-9e7b-0a47028df87e",
          "name": "Users_addon_accounts_read",
          "request": {
            "url": {
              "protocol": "http",
              "host": "test-api.osf.io",
              "path": [
                "v2",
                "users/:user_id/addons/:provider/accounts/:account_id/"
              ],
              "variable": [
                {
                  "id": "account_id",
                  "value": "{}",
                  "type": "string"
                },
                {
                  "id": "provider",
                  "value": "{}",
                  "type": "string"
                },
                {
                  "id": "user_id",
                  "value": "{}",
                  "type": "string"
                }
              ]
            },
            "method": "GET",
            "body": {
              "mode": "raw"
            },
            "description": "Retrieves the details of an addon account\n\n#### Permissions\n\nAddon accounts are visible only to the user that authorized the account.\n\n####Returns\nReturns a JSON object with a `data` key containing the representation of the requested addon account, if the request was successful.\n\nIf the request is unsuccessful, an `errors` key containing information about the failure will be returned. Refer to the [list of error codes](#Introduction_error_codes) to understand why this request may have failed."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "776349b7-02c4-4236-b0be-559cbb39724c"
            }
          ]
        }
      ]
    }
  ]
}