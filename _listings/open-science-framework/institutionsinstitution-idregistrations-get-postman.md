{
  "info": {
    "name": "Open Science Framework List all affiliated registrations",
    "_postman_id": "f637e572-0615-4d14-bfba-415581f87535",
    "description": "A paginated list of all registrations affiliated with an institution.\n#### Returns\nReturns a JSON object containing `data` and `links` keys.\n\nThe `data` key contains an array of 10 registrations. Each resource in the array is a separate users object.\n\nThe `links` key contains a dictionary of links that can be used for [pagination](#Introduction_pagination).\n\nIf the request is unsuccessful, an `errors` key containing information about the failure will be returned. Refer to the [list of error codes](#Introduction_error_codes) to understand why this request may have failed.\n#### Filtering\nYou can optionally request that the response only include registrations that match your filters by utilizing the `filter` query parameter, e.g. https://api.osf.io/v2/institutions/cos/registrations?filter[title]=science.\n\nRegistrations may be filtered by their  `id`, `title`, `description`, `public`, `tags`, `category`, `date_created`, `date_modified`, `root`, `parent`, `contributors`, and `preprint`",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "Institutions",
      "item": [
        {
          "id": "c40e0790-041e-4081-b3d5-d216e7589a62",
          "name": "institutions_registration_list",
          "request": {
            "url": {
              "protocol": "http",
              "host": "test-api.osf.io",
              "path": [
                "v2",
                "institutions/:institution_id/registrations/"
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
            "description": "A paginated list of all registrations affiliated with an institution.\n#### Returns\nReturns a JSON object containing `data` and `links` keys.\n\nThe `data` key contains an array of 10 registrations. Each resource in the array is a separate users object.\n\nThe `links` key contains a dictionary of links that can be used for [pagination](#Introduction_pagination).\n\nIf the request is unsuccessful, an `errors` key containing information about the failure will be returned. Refer to the [list of error codes](#Introduction_error_codes) to understand why this request may have failed.\n#### Filtering\nYou can optionally request that the response only include registrations that match your filters by utilizing the `filter` query parameter, e.g. https://api.osf.io/v2/institutions/cos/registrations?filter[title]=science.\n\nRegistrations may be filtered by their  `id`, `title`, `description`, `public`, `tags`, `category`, `date_created`, `date_modified`, `root`, `parent`, `contributors`, and `preprint`"
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "eecbf796-3dbb-4b69-924c-216468bc9ccd"
            }
          ]
        }
      ]
    }
  ]
}