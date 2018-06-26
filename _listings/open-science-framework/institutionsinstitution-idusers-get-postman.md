{
  "info": {
    "name": "Open Science Framework List all affiliated users",
    "_postman_id": "987aa8d5-3a6d-4a77-bcc1-750383be4d0c",
    "description": "A paginated list of all users affiliated with an institution.\n#### Returns\nReturns a JSON object containing `data` and `links` keys.\n\nThe `data` key contains an array of 10 users. Each resource in the array is a separate users object.\n\nThe `links` key contains a dictionary of links that can be used for [pagination](#Introduction_pagination).\n\nIf the request is unsuccessful, an `errors` key containing information about the failure will be returned. Refer to the [list of error codes](#Introduction_error_codes) to understand why this request may have failed.\n#### Filtering\nYou can optionally request that the response only include users that match your filters by utilizing the `filter` query parameter, e.g. https://api.osf.io/v2/institutions/cos/users?filter[family_name]=Nosek.\n\nUsers may be filtered by their `id`, `full_name`, `given_name`, `middle_names`, and `family_name`",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "Institutions",
      "item": [
        {
          "id": "0bdf3ec4-b807-4ec7-95db-764551d981b4",
          "name": "institutions_users_list",
          "request": {
            "url": {
              "protocol": "http",
              "host": "test-api.osf.io",
              "path": [
                "v2",
                "institutions/:institution_id/users/"
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
            "description": "A paginated list of all users affiliated with an institution.\n#### Returns\nReturns a JSON object containing `data` and `links` keys.\n\nThe `data` key contains an array of 10 users. Each resource in the array is a separate users object.\n\nThe `links` key contains a dictionary of links that can be used for [pagination](#Introduction_pagination).\n\nIf the request is unsuccessful, an `errors` key containing information about the failure will be returned. Refer to the [list of error codes](#Introduction_error_codes) to understand why this request may have failed.\n#### Filtering\nYou can optionally request that the response only include users that match your filters by utilizing the `filter` query parameter, e.g. https://api.osf.io/v2/institutions/cos/users?filter[family_name]=Nosek.\n\nUsers may be filtered by their `id`, `full_name`, `given_name`, `middle_names`, and `family_name`"
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "122bd603-9319-480f-bd40-fb57e4afa61c"
            }
          ]
        }
      ]
    }
  ]
}