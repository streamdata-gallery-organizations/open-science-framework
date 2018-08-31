{
  "info": {
    "name": "Open Science Framework Retrieve a file",
    "_postman_id": "6e9e0de8-b704-42c0-a2b8-eea27ecda429",
    "description": "Retrieves the details of a file (or folder)\n####Returns\nReturns a JSON object with a `data` key containing the representation of the requested file, if the request was successful.\n\nIf the request is unsuccessful, an `errors` key containing information about the failure will be returned. Refer to the [list of error codes](#Introduction_error_codes) to understand why this request may have failed.\n###Waterbutler API actions\n\nFiles can be modified through the Waterbutler API routes found in `links` (`new_folder`, `move`, `upload`, `download`, and `delete`).\n\n#### Download (files)\n\nTo download a file, issue a GET request against the download link. The response will have the Content-Disposition header set, which will will trigger a download in a browser.\n\n#### Create Subfolder (folders)\n\nYou can create a subfolder of an existing folder by issuing a PUT request against the new_folder link. The ?kind=folder portion of the query parameter is already included in the new_folder link. The name of the new subfolder should be provided in the name query parameter. The response will contain a WaterButler folder entity. If a folder with that name already exists in the parent directory, the server will return a 409 Conflict error response.\n\n#### Upload New File (folders)\n\n\n  To upload a file to a folder, issue a PUT request to the folder's upload link with the raw file data in the request body, and the kind and name query parameters set to 'file' and the desired name of the file. The response will contain a WaterButler file entity that describes the new file. If a file with the same name already exists in the folder, the server will return a 409 Conflict error response.\n\n\n#### Update Existing File (file)\n\nTo update an existing file, issue a PUT request to the file's upload link with the raw file data in the request body and the kind query parameter set to \"file\". The update action will create a new version of the file. The response will contain a WaterButler file entity that describes the updated file.\n\n#### Rename (files, folders)\n\nTo rename a file or folder, issue a POST request to the move link with the action body parameter set to \"rename\" and the rename body parameter set to the desired name. The response will contain either a folder entity or file entity with the new name.\n\n#### Move & Copy (files, folders)\n\nMove and copy actions both use the same request structure, a POST to the move url, but with different values for the action body parameters. The path parameter is also required and should be the OSF path attribute of the folder being written to. The rename and conflict parameters are optional. If you wish to change the name of the file or folder at its destination, set the rename parameter to the new name. The conflict param governs how name clashes are resolved. Possible values are replace and keep. replace is the default and will overwrite the file that already exists in the target folder. keep will attempt to keep both by adding a suffix to the new file's name until it no longer conflicts. The suffix will be ' (x)' where x is a increasing integer starting from 1. This behavior is intended to mimic that of the OS X Finder. The response will contain either a folder entity or file entity with the new name.\nFiles and folders can also be moved between nodes and providers. The resource parameter is the id of the node under which the file/folder should be moved. It must agree with the path parameter, that is the path must identify a valid folder under the node identified by resource. Likewise, the provider parameter may be used to move the file/folder to another storage provider, but both the resource and path parameters must belong to a node and folder already extant on that provider. Both resource and provider default to the current node and providers.\nIf a moved/copied file is overwriting an existing file, a 200 OK response will be returned. Otherwise, a 201 Created will be returned.\n\n#### Delete (file, folders)\n\nTo delete a file or folder send a DELETE request to the delete link. Nothing will be returned in the response body.",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "Files",
      "item": [
        {
          "id": "841e6788-567a-491e-8385-f30a7a5eac60",
          "name": "files_detail",
          "request": {
            "url": {
              "protocol": "http",
              "host": "test-api.osf.io",
              "path": [
                "v2",
                "files/:file_id/"
              ],
              "variable": [
                {
                  "id": "file_id",
                  "value": "{}",
                  "type": "string"
                }
              ]
            },
            "method": "GET",
            "body": {
              "mode": "raw"
            },
            "description": "Retrieves the details of a file (or folder)\n####Returns\nReturns a JSON object with a `data` key containing the representation of the requested file, if the request was successful.\n\nIf the request is unsuccessful, an `errors` key containing information about the failure will be returned. Refer to the [list of error codes](#Introduction_error_codes) to understand why this request may have failed.\n###Waterbutler API actions\n\nFiles can be modified through the Waterbutler API routes found in `links` (`new_folder`, `move`, `upload`, `download`, and `delete`).\n\n#### Download (files)\n\nTo download a file, issue a GET request against the download link. The response will have the Content-Disposition header set, which will will trigger a download in a browser.\n\n#### Create Subfolder (folders)\n\nYou can create a subfolder of an existing folder by issuing a PUT request against the new_folder link. The ?kind=folder portion of the query parameter is already included in the new_folder link. The name of the new subfolder should be provided in the name query parameter. The response will contain a WaterButler folder entity. If a folder with that name already exists in the parent directory, the server will return a 409 Conflict error response.\n\n#### Upload New File (folders)\n\n\n  To upload a file to a folder, issue a PUT request to the folder's upload link with the raw file data in the request body, and the kind and name query parameters set to 'file' and the desired name of the file. The response will contain a WaterButler file entity that describes the new file. If a file with the same name already exists in the folder, the server will return a 409 Conflict error response.\n\n\n#### Update Existing File (file)\n\nTo update an existing file, issue a PUT request to the file's upload link with the raw file data in the request body and the kind query parameter set to \"file\". The update action will create a new version of the file. The response will contain a WaterButler file entity that describes the updated file.\n\n#### Rename (files, folders)\n\nTo rename a file or folder, issue a POST request to the move link with the action body parameter set to \"rename\" and the rename body parameter set to the desired name. The response will contain either a folder entity or file entity with the new name.\n\n#### Move & Copy (files, folders)\n\nMove and copy actions both use the same request structure, a POST to the move url, but with different values for the action body parameters. The path parameter is also required and should be the OSF path attribute of the folder being written to. The rename and conflict parameters are optional. If you wish to change the name of the file or folder at its destination, set the rename parameter to the new name. The conflict param governs how name clashes are resolved. Possible values are replace and keep. replace is the default and will overwrite the file that already exists in the target folder. keep will attempt to keep both by adding a suffix to the new file's name until it no longer conflicts. The suffix will be ' (x)' where x is a increasing integer starting from 1. This behavior is intended to mimic that of the OS X Finder. The response will contain either a folder entity or file entity with the new name.\nFiles and folders can also be moved between nodes and providers. The resource parameter is the id of the node under which the file/folder should be moved. It must agree with the path parameter, that is the path must identify a valid folder under the node identified by resource. Likewise, the provider parameter may be used to move the file/folder to another storage provider, but both the resource and path parameters must belong to a node and folder already extant on that provider. Both resource and provider default to the current node and providers.\nIf a moved/copied file is overwriting an existing file, a 200 OK response will be returned. Otherwise, a 201 Created will be returned.\n\n#### Delete (file, folders)\n\nTo delete a file or folder send a DELETE request to the delete link. Nothing will be returned in the response body."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "866e4533-9a60-4a2c-8d8e-5b54dc8e5403"
            }
          ]
        }
      ]
    }
  ]
}