{
  "info": {
    "name": "Open Science Framework List all addons",
    "_postman_id": "70f84dee-2283-4c4d-938d-6f7f4914f61a",
    "description": "A paginated list of addons configurable with the OSF\n#### Returns\nReturns a JSON object containing `data` and `links` keys.\n\nThe `data` key contains an array of up to 10 addons. Each resource in the array is a separate addon object.\n\nThe `links` key contains a dictionary of links that can be used for [pagination](#Introduction_pagination).\n\nThis request should never return an error.",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "Addons",
      "item": [
        {
          "id": "7d820f78-18bc-4ff0-b560-eec7c94a18af",
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
              "id": "76b6e70c-3936-4806-86be-dfc2a0d98f45"
            }
          ]
        }
      ]
    }
  ]
}