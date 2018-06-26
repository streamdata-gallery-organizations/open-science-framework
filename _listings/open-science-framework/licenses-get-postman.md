{
  "info": {
    "name": "Open Science Framework List all licenses",
    "_postman_id": "af6ea63b-8f03-4f88-b5ed-80bdc1d4595f",
    "description": "A paginated list of licenses. The returned licenses are sorted by their name.\n#### Returns\nReturns a JSON object containing `data` and `links` keys.\nThe `data` key contains an array of 10 licenses. Each resource in the array is a separate license object and contains the full representation of the license, meaning additional requests to a license's detail view are not necessary.\n\nThe `links` key contains a dictionary of links that can be used for [pagination](#Introduction_pagination).\n\nThis request should never return an error.\n#### Filtering\nYou can optionally request that the response only include licenses that match your filters by utilizing the `filter` query parameter, e.g. [https://api.osf.io/v2/licenses/?filter[name]=apache](https://api.osf.io/v2/licenses/?filter[name]=apache).\n\nLicenses may be filtered by their `id`, and `name`.",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "Licenses",
      "item": [
        {
          "id": "0971af48-3365-4bca-b5f6-25c8c94211fb",
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
              "id": "df94eca2-c6d1-4f8f-a0f1-6f9847545d48"
            }
          ]
        }
      ]
    }
  ]
}