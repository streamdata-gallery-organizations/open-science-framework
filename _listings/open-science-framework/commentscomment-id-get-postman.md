{
  "info": {
    "name": "Open Science Framework Retrieve a comment",
    "_postman_id": "b1993307-6075-4829-94db-3b486e3f1dbd",
    "description": "Retrieves the details of a comment\n####Returns\nReturns a JSON object with a `data` key containing the representation of the requested comment, if the request was successful.\n\nIf the request is unsuccessful, an `errors` key containing information about the failure will be returned. Refer to the [list of error codes](#Introduction_error_codes) to understand why this request may have failed.",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "Comments",
      "item": [
        {
          "id": "b8c624ba-aff8-40b5-9055-d866a843e7de",
          "name": "comments_read",
          "request": {
            "url": {
              "protocol": "http",
              "host": "test-api.osf.io",
              "path": [
                "v2",
                "comments/:comment_id/"
              ],
              "variable": [
                {
                  "id": "comment_id",
                  "value": "{}",
                  "type": "string"
                }
              ]
            },
            "method": "GET",
            "body": {
              "mode": "raw"
            },
            "description": "Retrieves the details of a comment\n####Returns\nReturns a JSON object with a `data` key containing the representation of the requested comment, if the request was successful.\n\nIf the request is unsuccessful, an `errors` key containing information about the failure will be returned. Refer to the [list of error codes](#Introduction_error_codes) to understand why this request may have failed."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "cac50fae-acb5-4822-bc43-92494ed8a96f"
            }
          ]
        },
        {
          "id": "4d207eb4-82e1-4c66-8579-bf75dd3fffa3",
          "name": "comments_delete",
          "request": {
            "url": {
              "protocol": "http",
              "host": "test-api.osf.io",
              "path": [
                "v2",
                "comments/:comment_id/"
              ],
              "variable": [
                {
                  "id": "comment_id",
                  "value": "{}",
                  "type": "string"
                }
              ]
            },
            "method": "DELETE",
            "body": {
              "mode": "raw"
            },
            "description": "Deletes a comment. This action can be undone by setting deleted to False in a comment update request.\n#### Returns\nIf the request is successful, no content is returned.\n\nIf the request is unsuccessful, a JSON object with an `errors` key containing information about the failure will be returned. Refer to the [list of error codes](#Introduction_error_codes) to understand why this request may have failed."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "2eb2835e-25fa-46b4-bb4e-df0798fc485b"
            }
          ]
        }
      ]
    }
  ]
}