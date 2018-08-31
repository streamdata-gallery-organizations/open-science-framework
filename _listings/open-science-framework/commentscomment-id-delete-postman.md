{
  "info": {
    "name": "Open Science Framework Delete a comment",
    "_postman_id": "c63a360d-c01d-4c96-8e49-94f13ad99f8f",
    "description": "Deletes a comment. This action can be undone by setting deleted to False in a comment update request.\n#### Returns\nIf the request is successful, no content is returned.\n\nIf the request is unsuccessful, a JSON object with an `errors` key containing information about the failure will be returned. Refer to the [list of error codes](#Introduction_error_codes) to understand why this request may have failed.",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "Comments",
      "item": [
        {
          "id": "cfcd4858-8a7c-4a07-9241-6ea37af8d4e2",
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
              "id": "8cd7748d-b9d0-414f-ae94-73e3b8ac3f4d"
            }
          ]
        }
      ]
    }
  ]
}