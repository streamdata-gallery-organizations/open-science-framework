{
  "info": {
    "name": "Open Science Framework List all users",
    "_postman_id": "d4e18612-cc51-491b-a2f8-01c1c8167fb0",
    "description": "A paginated list of all users registered on the OSF. The returned users are sorted by their `date_registered`, with the most recently registered users appearing first.\n\nThe subroute `/users/me/` is a special endpoint that always points to the currently logged-in user.\n#### Versioning\nAs of version `2.3`, merged users will not be returned from this endpoint.\n#### Returns\nReturns a JSON object containing `data` and `links` keys.\n\nThe `data` key contains an array of 10 users. Each resource in the array is a separate users object and contains the full representation of the user, meaning additional requests to a user's detail view are not necessary.\n\nThe `links` key contains a dictionary of links that can be used for [pagination](#Introduction_pagination).\n\nThis request should never return an error.\n#### Filtering\nYou can optionally request that the response only include nodes that match your filters by utilizing the `filter` query parameter, e.g. https://api.osf.io/v2/users/?filter[family_name]=Nosek.\n\nUsers may be filtered by their `id`, `full_name`, `given_name`, `middle_name`, or `family_name`.",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "Institutions",
      "item": [
        {
          "id": "b4ead0df-fc2e-494f-851e-df9a488bcc96",
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
              "id": "61f911e5-b7d4-4519-87cf-2f7d6b8372a7"
            }
          ]
        }
      ]
    },
    {
      "name": "Users",
      "item": [
        {
          "id": "a7f9ad88-ffce-427a-b9de-9863ed4357ff",
          "name": "users_list",
          "request": {
            "url": "http://test-api.osf.io/v2/users/",
            "method": "GET",
            "body": {
              "mode": "raw"
            },
            "description": "A paginated list of all users registered on the OSF. The returned users are sorted by their `date_registered`, with the most recently registered users appearing first.\n\nThe subroute `/users/me/` is a special endpoint that always points to the currently logged-in user.\n#### Versioning\nAs of version `2.3`, merged users will not be returned from this endpoint.\n#### Returns\nReturns a JSON object containing `data` and `links` keys.\n\nThe `data` key contains an array of 10 users. Each resource in the array is a separate users object and contains the full representation of the user, meaning additional requests to a user's detail view are not necessary.\n\nThe `links` key contains a dictionary of links that can be used for [pagination](#Introduction_pagination).\n\nThis request should never return an error.\n#### Filtering\nYou can optionally request that the response only include nodes that match your filters by utilizing the `filter` query parameter, e.g. https://api.osf.io/v2/users/?filter[family_name]=Nosek.\n\nUsers may be filtered by their `id`, `full_name`, `given_name`, `middle_name`, or `family_name`."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "74e4afa8-985d-48f3-860a-c1fa691bae68"
            }
          ]
        }
      ]
    }
  ]
}