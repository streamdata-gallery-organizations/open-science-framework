{
  "info": {
    "name": "Open Science Framework Retrieve a user",
    "_postman_id": "460243c4-40e6-4cad-9167-8179e98d91fa",
    "description": "Retrieves the details of a given users.\n\nThe returned information includes the user's bibliographic information and the date the user was registered.\n\nAdditionally, relationships to the list of institutions with which the user is affiliated, and to the list of nodes which the user contributes to (that the requesting user has permission to see) are returned.\n\nIf `me` is given as the `user_id` in the request path, the record of the currently logged-in user will be returned.\n#### Returns\nReturns a JSON object with a `data` key containing the representation of the requested user, if the request is successful.\n\nIf the request is unsuccessful, an `errors` key containing information about the failure will be returned. Refer to the [list of error codes](#Introduction_error_codes) to understand why this request may have failed.",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "Institutions",
      "item": [
        {
          "id": "3c2189f3-dfa4-4b61-bf76-0de2d6a5c5e7",
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
              "id": "1796ef4e-fd84-4e3c-a362-2a83e2d34129"
            }
          ]
        }
      ]
    },
    {
      "name": "Users",
      "item": [
        {
          "id": "15ceb76b-dae8-4386-a862-06a2a2e412ed",
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
              "id": "82415e58-f5aa-40a6-a844-f2b89a2f27a4"
            }
          ]
        },
        {
          "id": "1d171b3f-9726-4bfe-ad6d-01223792db45",
          "name": "users_read",
          "request": {
            "url": {
              "protocol": "http",
              "host": "test-api.osf.io",
              "path": [
                "v2",
                "users/:user_id/"
              ],
              "variable": [
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
            "description": "Retrieves the details of a given users.\n\nThe returned information includes the user's bibliographic information and the date the user was registered.\n\nAdditionally, relationships to the list of institutions with which the user is affiliated, and to the list of nodes which the user contributes to (that the requesting user has permission to see) are returned.\n\nIf `me` is given as the `user_id` in the request path, the record of the currently logged-in user will be returned.\n#### Returns\nReturns a JSON object with a `data` key containing the representation of the requested user, if the request is successful.\n\nIf the request is unsuccessful, an `errors` key containing information about the failure will be returned. Refer to the [list of error codes](#Introduction_error_codes) to understand why this request may have failed."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "f995f65c-f118-4061-96dc-4d593b5a7f33"
            }
          ]
        }
      ]
    }
  ]
}