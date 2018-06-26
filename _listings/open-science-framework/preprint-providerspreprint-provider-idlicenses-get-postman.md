{
  "info": {
    "name": "Open Science Framework List all licenses",
    "_postman_id": "f2bc9c74-51ef-45fe-b019-9151fe8903c8",
    "description": "A paginated list of the licenses allowed bya preprint provider.\n#### Returns\nReturns a JSON object containing `data` and `links` keys.\n\nThe `data` key contains an array of 10 preprint providers. Each resource in the array is a separate preprint provider object.\n\nThe `links` key contains a dictionary of links that can be used for [pagination](#Introduction_pagination).\n\nIf the request is unsuccessful, an `errors` key containing information about the failure will be returned. Refer to the [list of error codes](#Introduction_error_codes) to understand why this request may have failed.",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "Licenses",
      "item": [
        {
          "id": "4f774d75-428c-4c00-967f-ee8e582551a7",
          "name": "license_list",
          "request": {
            "url": "http://test-api.osf.io/v2/licenses/",
            "method": "GET",
            "body": {
              "mode": "raw"
            },
            "description": "A paginated list of licenses. The returned licenses are sorted by their name.\n#### Returns\nReturns a JSON object containing `data` and `links` keys.\nThe `data` key contains an array of 10 licenses. Each resource in the array is a separate license object and contains the full representation of the license, meaning additional requests to a license's detail view are not necessary.\n\nThe `links` key contains a dictionary of links that can be used for [pagination](#Introduction_pagination).\n\nThis request should never return an error.\n#### Filtering\nYou can optionally request that the response only include licenses that match your filters by utilizing the `filter` query parameter, e.g. [https://api.osf.io/v2/licenses/?filter[name]=apache](https://api.osf.io/v2/licenses/?filter[name]=apache).\n\nLicenses may be filtered by their `id`, and `name`."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "b3ce64c1-047f-48e2-aeb6-d3ad9eabba14"
            }
          ]
        }
      ]
    },
    {
      "name": "Preprint",
      "item": [
        {
          "id": "ac31524b-87c0-4f82-8b50-87094094568d",
          "name": "preprint_provider_licenses_list",
          "request": {
            "url": {
              "protocol": "http",
              "host": "test-api.osf.io",
              "path": [
                "v2",
                "preprint_providers/:preprint_provider_id/licenses/"
              ],
              "variable": [
                {
                  "id": "preprint_provider_id",
                  "value": "{}",
                  "type": "string"
                }
              ]
            },
            "method": "GET",
            "body": {
              "mode": "raw"
            },
            "description": "A paginated list of the licenses allowed bya preprint provider.\n#### Returns\nReturns a JSON object containing `data` and `links` keys.\n\nThe `data` key contains an array of 10 preprint providers. Each resource in the array is a separate preprint provider object.\n\nThe `links` key contains a dictionary of links that can be used for [pagination](#Introduction_pagination).\n\nIf the request is unsuccessful, an `errors` key containing information about the failure will be returned. Refer to the [list of error codes](#Introduction_error_codes) to understand why this request may have failed."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "9fae81ad-3e36-4b18-b086-c21856950b9a"
            }
          ]
        }
      ]
    }
  ]
}