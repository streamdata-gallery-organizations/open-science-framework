{
  "info": {
    "name": "Open Science Framework List all addon accounts",
    "_postman_id": "364ef9d1-7887-41a2-a204-3759a0614dcd",
    "description": "A paginated list of addon accounts authorized by this user.\n\n#### Permissions\n\nAddon accounts are visible only to the user that authorized the account.\n\n#### Returns\nReturns a JSON object containing `data` and `links` keys.\n\nThe `data` key contains an array of at most 10 addon account objects. Each resource in the array is a separate  addon account object and contains the full representation of the addon account.\n\nThe `links` key contains a dictionary of links that can be used for [pagination](#Introduction_pagination).",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "Users",
      "item": [
        {
          "id": "47083fdd-e0c8-4bb7-a858-ded6cd6fa803",
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
              "id": "bb48fce7-718c-4616-acce-2f3c52ca1409"
            }
          ]
        }
      ]
    }
  ]
}