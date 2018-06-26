---
swagger: "2.0"
x-collection-name: Open Science Framework
x-complete: 0
info:
  title: Open Science Framework Retrieve a metaschema
  description: |-
    Retrieves the details of a given metaschema.

    Metaschemas describe the supplemental questions that accompany a registration.

    #### Returns
    Returns a JSON object with a `data` key containing the representation of the requested metaschema, if the request is successful.

    If the request is unsuccessful, an `errors` key containing information about the failure will be returned. Refer to the [list of error codes](#Introduction_error_codes) to understand why this request may have failed.
  contact:
    name: OSF
    url: https://osf.io/support
    email: support@osf.io
  version: "2.0"
host: test-api.osf.io
basePath: /v2
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /:
    get:
      summary: Root
      description: |-
        Welcome to the Open Science Framework API. With this API you can access users, projects, components, logs, and files from the [Open Science Framework](https://osf.io/). The Open Science Framework (OSF) is a free, open-source service maintained by the [Center for Open Science](http://cos.io/).

        #### Returns
        A JSON object with `meta` and `links` keys.

        The `meta` key contains information such as a welcome message from the API, the specified version of the request, and the full representation of the current user, if authentication credentials were provided in the request.

        The `links` key contains links to the following entity collections: [addons](), [collections](), [institutions](#Institutions_institutions_list), [licenses](#Licenses_license_list), [metaschemas](), [nodes](#Nodes_nodes_list), [registrations](), [users](#Users_users_list)
      operationId: base_read
      x-api-path-slug: get
      responses:
        200:
          description: OK
      tags:
      - Root
  /actions/:
    get:
      summary: Actions
      description: |-
        A log can have one of many actions. The complete list of loggable actions (in the format {identifier}: {description}) is as follows:
        * `project_created`: A Node is created
        * `project_registered`: A Node is registered
        * `project_deleted`: A Node is deleted
        * `created_from`: A Node is created using an existing Node as a template
        * `pointer_created`: A Pointer is created
        * `pointer_forked`: A Pointer is forked
        * `pointer_removed`: A Pointer is removed
        * `node_removed`: A component is deleted
        * `node_forked`: A Node is forked
        ---
        * `made_public`: A Node is made public
        * `made_private`: A Node is made private
        * `tag_added`: A tag is added to a Node
        * `tag_removed`: A tag is removed from a Node
        * `edit_title`: A Node's title is changed
        * `edit_description`: A Node's description is changed
        * `updated_fields`: One or more of a Node's fields are changed
        * `external_ids_added`: An external identifier is added to a Node (e.g. DOI, ARK)
        * `view_only_link_added`: A view-only link was added to a Node
        * `view_only_link_removed`:  A view-only link was removed from a Node
        ---
        * `contributor_added`: A Contributor is added to a Node
        * `contributor_removed`: A Contributor is removed from a Node
        * `contributors_reordered`: A Contributor's position in a Node's bibliography is changed
        * `permissions_updated`: A Contributor`s permissions on a Node are changed
        * `made_contributor_visible`: A Contributor is made bibliographically visible on a Node
        * `made_contributor_invisible`: A Contributor is made bibliographically invisible on a Node
        ---
        * `wiki_updated`: A Node's wiki is updated
        * `wiki_deleted`: A Node's wiki is deleted
        * `wiki_renamed`: A Node's wiki is renamed
        * `made_wiki_public`: A Node's wiki is made public
        * `made_wiki_private`: A Node's wiki is made private
        ---
        * `addon_added`: An add-on is linked to a Node
        * `addon_removed`: An add-on is unlinked from a Node
        * `addon_file_moved`: A File in a Node's linked add-on is moved
        * `addon_file_copied`: A File in a Node's linked add-on is copied
        * `addon_file_renamed`: A File in a Node's linked add-on is renamed
        * `node_authorized`: An addon is authorized for a project
        * `node_deauthorized`: An addon is deauthorized for a project
        * `folder_created`: A Folder is created in a Node's linked add-on
        * `file_added`: A File is added to a Node's linked add-on
        * `file_updated`: A File is updated on a Node's linked add-on
        * `file_removed`: A File is removed from a Node's linked add-on
        * `file_restored`: A File is restored in a Node's linked add-on
        ---
        * `comment_added`: A Comment is added to some item
        * `comment_removed`: A Comment is removed from some item
        * `comment_updated`: A Comment is updated on some item
        ---
        * `embargo_initiated`: An embargoed Registration is proposed on a Node
        * `embargo_approved`: A proposed Embargo of a Node is approved
        * `embargo_cancelled`: A proposed Embargo of a Node is cancelled
        * `embargo_completed`: A proposed Embargo of a Node is completed
        * `retraction_initiated`: A Withdrawal of a Registration is proposed
        * `retraction_approved`: A Withdrawal of a Registration is approved
        * `retraction_cancelled`: A Withdrawal of a Registration is cancelled
        * `registration_initiated`: A Registration of a Node is proposed
        * `registration_approved`: A proposed Registration is approved
        * `registration_cancelled`: A proposed Registration is cancelled
      operationId: logs_actions
      x-api-path-slug: actions-get
      responses:
        200:
          description: OK
      tags:
      - Actions
  /addons/:
    get:
      summary: List all addons
      description: |-
        A paginated list of addons configurable with the OSF
        #### Returns
        Returns a JSON object containing `data` and `links` keys.

        The `data` key contains an array of up to 10 addons. Each resource in the array is a separate addon object.

        The `links` key contains a dictionary of links that can be used for [pagination](#Introduction_pagination).

        This request should never return an error.
      operationId: addons_list
      x-api-path-slug: addons-get
      responses:
        200:
          description: OK
      tags:
      - Addons
  /citations/styles/:
    get:
      summary: List all citation styles
      description: |-
        A paginated list of all standard citation styles available for rendering citations.
        #### Returns
        Returns a JSON object containing `data` and `links` keys.

        The `data` key contains an array of 10 citation styles. Each resource in the array is a separate citation syle and contains the full representation of the citation style object.

        The `links` key contains a dictionary of links that can be used for [pagination](#Introduction_pagination).

        This request should never return an error.
        #### Filtering
        You can optionally request that the response only include citation styles that match your filters by utilizing the `filter` query parameter, e.g. https://api.osf.io/v2/citations/styles/?filter[title]=open.

        Citation styles may be filtered by their `id`, `title`, `short-title`, and `summary`.
      operationId: citations_styles_list
      x-api-path-slug: citationsstyles-get
      responses:
        200:
          description: OK
      tags:
      - Citations
      - Styles
  /citations/styles/{style_id}/:
    get:
      summary: Retrieve a citation style
      description: |-
        Retrieves the details of a citation style.
        #### Returns
        Returns a JSON object with a `data` key containing the representation of the requested citation style, if the request is successful.

        If the request is unsuccessful, an `errors` key containing information about the failure will be returned. Refer to the [list of error codes](#Introduction_error_codes) to understand why this request may have failed.
      operationId: citations_styles_read
      x-api-path-slug: citationsstylesstyle-id-get
      parameters:
      - in: path
        name: style_id
        description: The unique identifier of the citation style
      responses:
        200:
          description: OK
      tags:
      - Citations
      - Styles
      - Style
  /comments/{comment_id}/:
    delete:
      summary: Delete a comment
      description: |-
        Deletes a comment. This action can be undone by setting deleted to False in a comment update request.
        #### Returns
        If the request is successful, no content is returned.

        If the request is unsuccessful, a JSON object with an `errors` key containing information about the failure will be returned. Refer to the [list of error codes](#Introduction_error_codes) to understand why this request may have failed.
      operationId: comments_delete
      x-api-path-slug: commentscomment-id-delete
      parameters:
      - in: path
        name: comment_id
        description: The unique identifier of the comment you wish to delete
      responses:
        200:
          description: OK
      tags:
      - Comments
      - Comment
    get:
      summary: Retrieve a comment
      description: |-
        Retrieves the details of a comment
        ####Returns
        Returns a JSON object with a `data` key containing the representation of the requested comment, if the request was successful.

        If the request is unsuccessful, an `errors` key containing information about the failure will be returned. Refer to the [list of error codes](#Introduction_error_codes) to understand why this request may have failed.
      operationId: comments_read
      x-api-path-slug: commentscomment-id-get
      parameters:
      - in: path
        name: comment_id
        description: The unique identifier of the comment you wish to retrieve
      responses:
        200:
          description: OK
      tags:
      - Comments
      - Comment
    put:
      summary: Update a comment
      description: |-
        Updates the specified comment by setting the values of the parameters passed. Any parameters not provided will be left unchanged.
        #### Returns
        Returns JSON with a `data` key containing the new representation of the updated comment, if the request is successful.

        If the request is unsuccessful, JSON with an `errors` key containing information about the failure will be returned. Refer to the [list of error codes](#Introduction_error_codes) to understand why this request may have failed.
      operationId: comments_put
      x-api-path-slug: commentscomment-id-put
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: comment_id
        description: The unique identifier of the comment you wish to update
      responses:
        200:
          description: OK
      tags:
      - Comments
      - Comment
  /files/{file_id}/:
    get:
      summary: Retrieve a file
      description: |-
        Retrieves the details of a file (or folder)
        ####Returns
        Returns a JSON object with a `data` key containing the representation of the requested file, if the request was successful.

        If the request is unsuccessful, an `errors` key containing information about the failure will be returned. Refer to the [list of error codes](#Introduction_error_codes) to understand why this request may have failed.
        ###Waterbutler API actions

        Files can be modified through the Waterbutler API routes found in `links` (`new_folder`, `move`, `upload`, `download`, and `delete`).

        #### Download (files)

        To download a file, issue a GET request against the download link. The response will have the Content-Disposition header set, which will will trigger a download in a browser.

        #### Create Subfolder (folders)

        You can create a subfolder of an existing folder by issuing a PUT request against the new_folder link. The ?kind=folder portion of the query parameter is already included in the new_folder link. The name of the new subfolder should be provided in the name query parameter. The response will contain a WaterButler folder entity. If a folder with that name already exists in the parent directory, the server will return a 409 Conflict error response.

        #### Upload New File (folders)


          To upload a file to a folder, issue a PUT request to the folder's upload link with the raw file data in the request body, and the kind and name query parameters set to 'file' and the desired name of the file. The response will contain a WaterButler file entity that describes the new file. If a file with the same name already exists in the folder, the server will return a 409 Conflict error response.


        #### Update Existing File (file)

        To update an existing file, issue a PUT request to the file's upload link with the raw file data in the request body and the kind query parameter set to "file". The update action will create a new version of the file. The response will contain a WaterButler file entity that describes the updated file.

        #### Rename (files, folders)

        To rename a file or folder, issue a POST request to the move link with the action body parameter set to "rename" and the rename body parameter set to the desired name. The response will contain either a folder entity or file entity with the new name.

        #### Move & Copy (files, folders)

        Move and copy actions both use the same request structure, a POST to the move url, but with different values for the action body parameters. The path parameter is also required and should be the OSF path attribute of the folder being written to. The rename and conflict parameters are optional. If you wish to change the name of the file or folder at its destination, set the rename parameter to the new name. The conflict param governs how name clashes are resolved. Possible values are replace and keep. replace is the default and will overwrite the file that already exists in the target folder. keep will attempt to keep both by adding a suffix to the new file's name until it no longer conflicts. The suffix will be ' (x)' where x is a increasing integer starting from 1. This behavior is intended to mimic that of the OS X Finder. The response will contain either a folder entity or file entity with the new name.
        Files and folders can also be moved between nodes and providers. The resource parameter is the id of the node under which the file/folder should be moved. It must agree with the path parameter, that is the path must identify a valid folder under the node identified by resource. Likewise, the provider parameter may be used to move the file/folder to another storage provider, but both the resource and path parameters must belong to a node and folder already extant on that provider. Both resource and provider default to the current node and providers.
        If a moved/copied file is overwriting an existing file, a 200 OK response will be returned. Otherwise, a 201 Created will be returned.

        #### Delete (file, folders)

        To delete a file or folder send a DELETE request to the delete link. Nothing will be returned in the response body.
      operationId: files_detail
      x-api-path-slug: filesfile-id-get
      parameters:
      - in: path
        name: file_id
        description: The unique identifier of the file you wish to retrieve
      responses:
        200:
          description: OK
      tags:
      - Files
      - File
    patch:
      summary: Update a file
      description: |-
        Updates the specified file by setting the values of the parameters passed. Any parameters not provided will be left unchanged.
        #### Returns
        Returns JSON with a `data` key containing the new representation of the updated file, if the request is successful.

        If the request is unsuccessful, JSON with an `errors` key containing information about the failure will be returned. Refer to the [list of error codes](#Introduction_error_codes) to understand why this request may have failed.
      operationId: files_patch
      x-api-path-slug: filesfile-id-patch
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: file_id
        description: The unique identifier of the file you wish to update
      responses:
        200:
          description: OK
      tags:
      - Files
      - File
  /files/{file_id}/versions/:
    get:
      summary: List all file versions
      description: |-
        A paginated list of all file versions.
        #### Returns
        Returns a JSON object containing `data` and `links` keys.

        The `data` key contains an array of 10 file versions. Each resource in the array is a separate file version object.

        The `links` key contains a dictionary of links that can be used for [pagination](#Introduction_pagination).

        If the request is unsuccessful, an `errors` key containing information about the failure will be returned. Refer to the [list of error codes](#Introduction_error_codes) to understand why this request may have failed.
      operationId: files_versions
      x-api-path-slug: filesfile-idversions-get
      parameters:
      - in: path
        name: file_id
        description: The unique identifier of the file from which you want to retrieve
          versions
      responses:
        200:
          description: OK
      tags:
      - Files
      - File
      - Versions
  /files/{file_id}/versions/{version_id}/:
    get:
      summary: Retrieve a file version
      description: |-
        Retrieves the details of a file version
        ####Returns

        Returns a JSON object with a `data` key containing the representation of the requested file, if the request was successful.

        If the request is unsuccessful, an `errors` key containing information about the failure will be returned. Refer to the [list of error codes](#Introduction_error_codes) to understand why this request may have failed.
      operationId: files_version_detail
      x-api-path-slug: filesfile-idversionsversion-id-get
      parameters:
      - in: path
        name: file_id
        description: The unique identifier of the file from which you want to retrieve
          versions
      - in: path
        name: version_id
        description: The file version number you want to retrieve
      responses:
        200:
          description: OK
      tags:
      - Files
      - File
      - Versions
      - Version
  /institutions/:
    get:
      summary: List all institutions
      description: |-
        A paginated list of all verified institutions.
        #### Returns
        Returns a JSON object containing `data` and `links` keys.

        The `data` key contains an array of 10 institutions. Each resource in the array is a separate institution object.

        The `links` key contains a dictionary of links that can be used for [pagination](#Introduction_pagination).

        This request should never return an error.
        #### Filtering
        You can optionally request that the response only include institutions that match your filters by utilizing the `filter` query parameter, e.g. https://api.osf.io/v2/institutions/?filter[id]=cos.

        Institutions may be filtered by their `id`, `name`, and `auth_url`
      operationId: institutions_list
      x-api-path-slug: institutions-get
      responses:
        200:
          description: OK
      tags:
      - Institutions
  /institutions/{institution_id}/:
    get:
      summary: Retrieve an institution
      description: |-
        Retrieves the details of an institution
        ####Returns
        Returns a JSON object with a `data` key containing the representation of the requested institution, if the request was successful.

        If the request is unsuccessful, an `errors` key containing information about the failure will be returned. Refer to the [list of error codes](#Introduction_error_codes) to understand why this request may have failed.
      operationId: institutions_detail
      x-api-path-slug: institutionsinstitution-id-get
      parameters:
      - in: path
        name: institution_id
        description: The unique identifier of the institution you wish to retrieve
      responses:
        200:
          description: OK
      tags:
      - Institutions
      - Institution
  /institutions/{institution_id}/nodes/:
    get:
      summary: List all affiliated nodes
      description: |-
        A paginated list of all nodes affiliated with an institution.
        #### Versioning
        As of version `2.2`, affiliated components (in addition to affiliated top-level projects) are returned from this endpoint.
        #### Returns
        Returns a JSON object containing `data` and `links` keys.

        The `data` key contains an array of 10 nodes. Each resource in the array is a separate nodes object.

        The `links` key contains a dictionary of links that can be used for [pagination](#Introduction_pagination).

        If the request is unsuccessful, an `errors` key containing information about the failure will be returned. Refer to the [list of error codes](#Introduction_error_codes) to understand why this request may have failed.
        #### Filtering
        You can optionally request that the response only include nodes that match your filters by utilizing the `filter` query parameter, e.g. https://api.osf.io/v2/institutions/cos/nodes?filter[title]=science.

        Nodes may be filtered by their `id`, `title`, `description`, `public`, `tags`, `category`, `date_created`, `date_modified`, `root`, `parent`, `contributors`, and `preprint`
      operationId: institutions_node_list
      x-api-path-slug: institutionsinstitution-idnodes-get
      parameters:
      - in: path
        name: institution_id
        description: The unique identifier of the institution you wish to retrieve
      responses:
        200:
          description: OK
      tags:
      - Institutions
      - Institution
      - Nodes
  /institutions/{institution_id}/registrations/:
    get:
      summary: List all affiliated registrations
      description: |-
        A paginated list of all registrations affiliated with an institution.
        #### Returns
        Returns a JSON object containing `data` and `links` keys.

        The `data` key contains an array of 10 registrations. Each resource in the array is a separate users object.

        The `links` key contains a dictionary of links that can be used for [pagination](#Introduction_pagination).

        If the request is unsuccessful, an `errors` key containing information about the failure will be returned. Refer to the [list of error codes](#Introduction_error_codes) to understand why this request may have failed.
        #### Filtering
        You can optionally request that the response only include registrations that match your filters by utilizing the `filter` query parameter, e.g. https://api.osf.io/v2/institutions/cos/registrations?filter[title]=science.

        Registrations may be filtered by their  `id`, `title`, `description`, `public`, `tags`, `category`, `date_created`, `date_modified`, `root`, `parent`, `contributors`, and `preprint`
      operationId: institutions_registration_list
      x-api-path-slug: institutionsinstitution-idregistrations-get
      parameters:
      - in: path
        name: institution_id
        description: The unique identifier of the institution you wish to retrieve
      responses:
        200:
          description: OK
      tags:
      - Institutions
      - Institution
      - Registrations
  /institutions/{institution_id}/users/:
    get:
      summary: List all affiliated users
      description: |-
        A paginated list of all users affiliated with an institution.
        #### Returns
        Returns a JSON object containing `data` and `links` keys.

        The `data` key contains an array of 10 users. Each resource in the array is a separate users object.

        The `links` key contains a dictionary of links that can be used for [pagination](#Introduction_pagination).

        If the request is unsuccessful, an `errors` key containing information about the failure will be returned. Refer to the [list of error codes](#Introduction_error_codes) to understand why this request may have failed.
        #### Filtering
        You can optionally request that the response only include users that match your filters by utilizing the `filter` query parameter, e.g. https://api.osf.io/v2/institutions/cos/users?filter[family_name]=Nosek.

        Users may be filtered by their `id`, `full_name`, `given_name`, `middle_names`, and `family_name`
      operationId: institutions_users_list
      x-api-path-slug: institutionsinstitution-idusers-get
      parameters:
      - in: path
        name: institution_id
        description: The unique identifier of the institution you wish to retrieve
      responses:
        200:
          description: OK
      tags:
      - Institutions
      - Institution
      - Users
  /license/{license_id}/:
    get:
      summary: Retrieve a license
      description: |-
        Retrieves the details of a license.
        #### Returns
        Returns a JSON object with a `data` key containing the representation of the requested license, if the request is successful.

        If the request is unsuccessful, an `errors` key containing information about the failure will be returned. Refer to the [list of error codes](#Introduction_error_codes) to understand why this request may have failed.
      operationId: licenses_read
      x-api-path-slug: licenselicense-id-get
      parameters:
      - in: path
        name: license_id
        description: The unique identifier of the license
      responses:
        200:
          description: OK
      tags:
      - License
      - License
  /licenses/:
    get:
      summary: List all licenses
      description: |-
        A paginated list of licenses. The returned licenses are sorted by their name.
        #### Returns
        Returns a JSON object containing `data` and `links` keys.
        The `data` key contains an array of 10 licenses. Each resource in the array is a separate license object and contains the full representation of the license, meaning additional requests to a license's detail view are not necessary.

        The `links` key contains a dictionary of links that can be used for [pagination](#Introduction_pagination).

        This request should never return an error.
        #### Filtering
        You can optionally request that the response only include licenses that match your filters by utilizing the `filter` query parameter, e.g. [https://api.osf.io/v2/licenses/?filter[name]=apache](https://api.osf.io/v2/licenses/?filter[name]=apache).

        Licenses may be filtered by their `id`, and `name`.
      operationId: license_list
      x-api-path-slug: licenses-get
      responses:
        200:
          description: OK
      tags:
      - Licenses
  /logs/{log_id}/:
    get:
      summary: Retrieve a log
      description: |-
        Retrieves the details of a log.
        A log is permanent immutable record of a node's history. A log is created when a user performs one of many actions. See the [actions](#Logs_logs_actions) section for more details.
        ####Returns
        Returns a JSON object with a `data` key containing the representation of the requested log, if the request was successful.

        If the request is unsuccessful, an `errors` key containing information about the failure will be returned. Refer to the [list of error codes](#Introduction_error_codes) to understand why this request may have failed.
      operationId: logs_read
      x-api-path-slug: logslog-id-get
      parameters:
      - in: path
        name: log_id
        description: The unique identifier of the log you wish to retrieve
      responses:
        200:
          description: OK
      tags:
      - Logs
      - Log
  /metaschemas/:
    get:
      summary: List all metaschemas
      description: |-
        A paginated list of all active metaschemas.
        Metaschemas describe the supplemental questions that accompany a registration.
        #### Returns
        Returns a JSON object containing `data` and `links` keys.

        The `data` key contains an array of 10 metaschemas. Each resource in the array is a separate metaschema object.

        The `links` key contains a dictionary of links that can be used for [pagination](#Introduction_pagination).

        This request should never return an error.
      operationId: metaschemas_list
      x-api-path-slug: metaschemas-get
      responses:
        200:
          description: OK
      tags:
      - Metaschemas
  /metaschemas/{metaschema_id}:
    get:
      summary: Retrieve a metaschema
      description: |-
        Retrieves the details of a given metaschema.

        Metaschemas describe the supplemental questions that accompany a registration.

        #### Returns
        Returns a JSON object with a `data` key containing the representation of the requested metaschema, if the request is successful.

        If the request is unsuccessful, an `errors` key containing information about the failure will be returned. Refer to the [list of error codes](#Introduction_error_codes) to understand why this request may have failed.
      operationId: metaschemas_read
      x-api-path-slug: metaschemasmetaschema-id-get
      parameters:
      - in: path
        name: metaschema_id
        description: The unique identifier of the metaschema
      responses:
        200:
          description: OK
      tags:
      - Metaschemas
      - Metaschema
x-streamrank:
  polling_total_time_average: 0
  polling_size_download_average: 0
  streaming_total_time_average: 0
  streaming_size_download_average: 0
  change_yes: 0
  change_no: 0
  time_percentage: 0
  size_percentage: 0
  change_percentage: 0
  last_run: ""
  days_run: 0
  minute_run: 0
---