{
  "info": {
    "name": "Open Science Framework Retrieve a Wiki",
    "_postman_id": "a03decaa-e732-485b-ad8c-87fdc2e4758f",
    "description": "Retrieves the details about a specific wiki.\nA wiki is a collection of markdown text pages that can be used to describe the project or dataset of contained in the attached node.\n####Returns\nReturns a JSON object with a `data` key containing the representation of the requested wiki, if the request was successful.\n\nIf the request is unsuccessful, an `errors` key containing information about the failure will be returned. Refer to the [list of error codes](#Introduction_error_codes) to understand why this request may have failed.",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "Nodes",
      "item": [
        {
          "id": "4820f72b-00ed-4955-b417-5c4c8c405b87",
          "name": "nodes_wikis_list",
          "request": {
            "url": {
              "protocol": "http",
              "host": "test-api.osf.io",
              "path": [
                "v2",
                "nodes/:node_id/wikis/"
              ],
              "variable": [
                {
                  "id": "node_id",
                  "value": "{}",
                  "type": "string"
                }
              ]
            },
            "method": "GET",
            "body": {
              "mode": "raw"
            },
            "description": "List of wiki pages on a node.\n####Returns\nPaginated list of the node's current wiki page versions ordered by their date_modified. Each resource contains the full representation of the wiki, meaning additional requests to an individual wiki's detail view are not necessary.\n\nNote that if an anonymous view_only key is being used, the user relationship will not be exposed.\n\nIf the request is unsuccessful, a JSON object with an `errors` key containing information about the failure will be returned. Refer to the [list of error codes](#Introduction_error_codes) to understand why this request may have failed.\n#### Filtering\nWiki pages can be filtered based on their `name` and `date_modified` fields.\n+ `filter[name]=<Str>` -- filter wiki pages by name\n+ `filter[date_modified][comparison_operator]=YYYY-MM-DDTH:M:S` -- filter wiki pages based on date modified.\n\nPossible comparison operators include 'gt' (greater than), 'gte'(greater than or equal to), 'lt' (less than) and 'lte' (less than or equal to). The date must be in the format YYYY-MM-DD and the time is optional."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "8cdbb46b-8849-422a-99ed-3befaf5afc00"
            }
          ]
        }
      ]
    },
    {
      "name": "Registrations",
      "item": [
        {
          "id": "f9d9138d-a75e-4b6d-8e00-5ee6ed99f019",
          "name": "registrations_wikis_list",
          "request": {
            "url": {
              "protocol": "http",
              "host": "test-api.osf.io",
              "path": [
                "v2",
                "registrations/:registration_id/wikis/"
              ],
              "variable": [
                {
                  "id": "registration_id",
                  "value": "{}",
                  "type": "string"
                }
              ]
            },
            "method": "GET",
            "body": {
              "mode": "raw"
            },
            "description": "A paginated list of the registration's wiki pages\n####Returns\nA list of all registration's current wiki page versions ordered by their date_modified. Each resource contains the full representation of the wiki, meaning additional requests to an individual wiki's detail view are not necessary.\n\nIf the request is unsuccessful, a JSON object with an `errors` key containing information about the failure will be returned. Refer to the [list of error codes](#Introduction_error_codes) to understand why this request may have failed.\n#### Filtering\nWiki pages can be filtered based on their `name` and `date_modified` fields.\n+ `filter[name]=<Str>` -- filter wiki pages by name\n+ `filter[date_modified][comparison_operator]=YYYY-MM-DDTH:M:S` -- filter wiki pages based on date modified.\n\nPossible comparison operators include 'gt' (greater than), 'gte'(greater than or equal to), 'lt' (less than) and 'lte' (less than or equal to). The date must be in the format YYYY-MM-DD and the time is optional."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "275e6b7c-2f96-4ca2-b210-c6e3309ab5f3"
            }
          ]
        }
      ]
    },
    {
      "name": "Wikis",
      "item": [
        {
          "id": "bfaff46d-1aa0-437f-bbf7-b33358e0eb7c",
          "name": "wiki_read",
          "request": {
            "url": {
              "protocol": "http",
              "host": "test-api.osf.io",
              "path": [
                "v2",
                "wikis/:wiki_id/"
              ],
              "variable": [
                {
                  "id": "wiki_id",
                  "value": "{}",
                  "type": "string"
                }
              ]
            },
            "method": "GET",
            "body": {
              "mode": "raw"
            },
            "description": "Retrieves the details about a specific wiki.\nA wiki is a collection of markdown text pages that can be used to describe the project or dataset of contained in the attached node.\n####Returns\nReturns a JSON object with a `data` key containing the representation of the requested wiki, if the request was successful.\n\nIf the request is unsuccessful, an `errors` key containing information about the failure will be returned. Refer to the [list of error codes](#Introduction_error_codes) to understand why this request may have failed."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "93878758-1bb2-422f-9df2-ee5dab5f9ea2"
            }
          ]
        }
      ]
    }
  ]
}