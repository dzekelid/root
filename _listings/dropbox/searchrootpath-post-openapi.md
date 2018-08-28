---
swagger: "2.0"
x-collection-name: Dropbox
x-complete: 0
info:
  title: Dropbox Core Search for files and folders by name.
  description: |-
    Returns metadata for all files and folders whose filename contains the given search string as a substring.

    Searches are limited to the folder path and its sub-folder hierarchy provided in the call.

    **Note:** Recent changes may not immediately be reflected in search results due to a short delay in indexing.
  termsOfService: https://www.dropbox.com/developers/reference/tos
  contact:
    name: Dropbox
    url: https://www.dropbox.com/developers
  version: 1.0.0
host: api.dropbox.com
basePath: /1
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /files/{root}/{path}:
    get:
      summary: Downloads a file.
      description: |-
        Downloads a file.

        This method also supports [HTTP Range Retrieval Requests](http://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.35.2)
        to allow retrieving partial file contents.
      operationId: downloads-a-filethis-method-also-supports-http-range-retrieval-requestshttpwwww3orgprotocolsrfc2616r
      x-api-path-slug: filesrootpath-get
      parameters:
      - in: path
        name: path
        description: The path to the file you want to retrieve
      - in: query
        name: rev
        description: The revision of the file to retrieve
      - in: path
        name: root
        description: 'Root folder: `auto` - automatically determines the appropriate
          root folder using your apps permissionlevel (recommended); `sandbox` - the
          codename for app folder level; `dropbox` - full dropbox access'
      responses:
        200:
          description: OK
      tags:
      - Storage
      - Documents
      - Files
      - Root
      - Path
  /files_put/{root}/{path}:
    post:
      summary: Uploads a file using PUT semantics.
      description: |-
        Uploads a file using PUT semantics.

        The preferred HTTP method for this call is **PUT**. For compatibility with browser environments, the **POST**
        HTTP method is also recognized.

        **Note:** Providing a `Content-Length` header set to the size of the uploaded file is required so that the
        server can verify that it has received the entire file contents.

        **Note:** `/files_put` has a maximum file size limit of 150 MB and does not support uploads with chunked
        encoding. To upload larger files, use [/chunked_upload](https://www.dropbox.com/developers/core/docs#chunked-upload)
        instead.
      operationId: uploads-a-file-using-put-semanticsthe-preferred-http-method-for-this-call-is-put-for-compatibility-w
      x-api-path-slug: files-putrootpath-post
      parameters:
      - in: query
        name: autorename
        description: This value, either `true` (default) or `false`, determines what
          happens when there is a conflict
      - in: body
        name: file_content
        description: The file contents to be uploaded
        schema:
          $ref: '#/definitions/holder'
      - in: query
        name: locale
        description: The metadata returned on successful upload will have its `size`
          field translated based on the given locale
      - in: query
        name: overwrite
        description: This value, either `true` (default) or `false`, determines whether
          an existing file will be overwrittenby this upload
      - in: query
        name: parent_rev
        description: If present, this parameter specifies the revision of the file
          youre editing
      - in: path
        name: path
        description: The full path to the file you want to write to
      - in: path
        name: root
        description: 'Root folder: `auto` - automatically determines the appropriate
          root folder using your apps permissionlevel (recommended); `sandbox` - the
          codename for app folder level; `dropbox` - full dropbox access'
      responses:
        200:
          description: OK
      tags:
      - Storage
      - Documents
      - Files
      - Put
      - Root
      - Path
    put:
      summary: Uploads a file using PUT semantics.
      description: |-
        Uploads a file using PUT semantics.

        The preferred HTTP method for this call is **PUT**. For compatibility with browser environments, the **POST**
        HTTP method is also recognized.

        **Note:** Providing a `Content-Length` header set to the size of the uploaded file is required so that the
        server can verify that it has received the entire file contents.

        **Note:** `/files_put` has a maximum file size limit of 150 MB and does not support uploads with chunked
        encoding. To upload larger files, use [/chunked_upload](https://www.dropbox.com/developers/core/docs#chunked-upload)
        instead.
      operationId: uploads-a-file-using-put-semanticsthe-preferred-http-method-for-this-call-is-put-for-compatibility-w
      x-api-path-slug: files-putrootpath-put
      parameters:
      - in: query
        name: autorename
        description: This value, either `true` (default) or `false`, determines what
          happens when there is a conflict
      - in: body
        name: file_content
        description: The file contents to be uploaded
        schema:
          $ref: '#/definitions/holder'
      - in: query
        name: locale
        description: The metadata returned on successful upload will have its `size`
          field translated based on the given locale
      - in: query
        name: overwrite
        description: This value, either `true` (default) or `false`, determines whether
          an existing file will be overwrittenby this upload
      - in: query
        name: parent_rev
        description: If present, this parameter specifies the revision of the file
          youre editing
      - in: path
        name: path
        description: The full path to the file you want to write to
      - in: path
        name: root
        description: 'Root folder: `auto` - automatically determines the appropriate
          root folder using your apps permissionlevel (recommended); `sandbox` - the
          codename for app folder level; `dropbox` - full dropbox access'
      responses:
        200:
          description: OK
      tags:
      - Storage
      - Documents
      - Files
      - Put
      - Root
      - Path
  /thumbnails/{root}/{path}:
    get:
      summary: Gets a thumbnail for an image.
      description: |-
        Gets a thumbnail for an image.

        This method currently supports files with the following file extensions: .jpg, .jpeg, .png, .tiff, .tif, .gif, .bmp

        Photos that are larger than 20MB in size won't be converted to a thumbnail.
      operationId: gets-a-thumbnail-for-an-imagethis-method-currently-supports-files-with-the-following-file-extensions
      x-api-path-slug: thumbnailsrootpath-get
      parameters:
      - in: query
        name: format
        description: For images that are photos, `jpeg` (default) should be preferred,
          while `png` is better for screenshots and digital art
      - in: path
        name: path
        description: The path to the image file you want to thumbnail
      - in: path
        name: root
        description: 'Root folder: `auto` - automatically determines the appropriate
          root folder using your apps permissionlevel (recommended); `sandbox` - the
          codename for app folder level; `dropbox` - full dropbox access'
      - in: query
        name: size
        description: Default size is `s`
      responses:
        200:
          description: OK
      tags:
      - Storage
      - Documents
      - Thumbnails
      - Root
      - Path
  /previews/{root}/{path}:
    get:
      summary: Gets a preview for a file.
      description: |-
        Gets a preview for a file.

        Previews are only generated for the files with the following extensions: .doc, .docx, .docm, .ppt, .pps,
        .ppsx, .ppsm, .pptx, .pptm, .xls, .xlsx, .xlsm, .rtf
      operationId: gets-a-preview-for-a-filepreviews-are-only-generated-for-the-files-with-the-following-extensions-doc
      x-api-path-slug: previewsrootpath-get
      parameters:
      - in: path
        name: path
        description: The absolute path to the file you want to preview
      - in: query
        name: rev
        description: The revision of the file to retrieve
      - in: path
        name: root
        description: 'Root folder: `auto` - automatically determines the appropriate
          root folder using your apps permissionlevel (recommended); `sandbox` - the
          codename for app folder level; `dropbox` - full dropbox access'
      responses:
        200:
          description: OK
      tags:
      - Storage
      - Documents
      - Previews
      - Root
      - Path
  /commit_chunked_upload/{root}/{path}:
    post:
      summary: Completes an upload initiated by the chunked upload method.
      description: |-
        Completes an upload initiated by the `/chunked_upload` method. Saves a file uploaded via `/chunked_upload` to
        a user's Dropbox.

        `/commit_chunked_upload` is similar to `/files_put`. The main difference is that while `/files_put` takes the
        file contents in the request body, `/commit_chunked_upload` takes a parameter `upload_id`, which is obtained
        when the file contents are uploaded via `/chunked_upload`.
      operationId: completes-an-upload-initiated-by-the-chunked-upload-method-saves-a-file-uploaded-via-chunked-upload-
      x-api-path-slug: commit-chunked-uploadrootpath-post
      parameters:
      - in: query
        name: autorename
        description: This value, either `true` (default) or `false`, determines what
          happens when there is a conflict
      - in: query
        name: locale
        description: The metadata returned on successful upload will have its `size`
          field translated based on the given locale
      - in: query
        name: overwrite
        description: This value, either `true` (default) or `false`, determines whether
          an existing file will be overwritten bythis upload
      - in: query
        name: parent_rev
        description: If present, this parameter specifies the revision of the file
          youre editing
      - in: path
        name: path
        description: The full path to the file you want to write to
      - in: path
        name: root
        description: 'Root folder: `auto` - automatically determines the appropriate
          root folder using your apps permissionlevel (recommended); `sandbox` - the
          codename for app folder level; `dropbox` - full dropbox access'
      - in: query
        name: upload_id
        description: Used to identify the chunked upload session youd like to commit
      responses:
        200:
          description: OK
      tags:
      - Storage
      - Documents
      - Commit
      - Chunked
      - Upload
      - Root
      - Path
  /metadata/{root}/{path}:
    get:
      summary: Retrieves file and folder metadata.
      description: |-
        Retrieves file and folder metadata.

        **Note:** `modified`, `rev`, and `revision` aren't returned in the metadata for the root/top-level path.
      operationId: retrieves-file-and-folder-metadatanote-modified-rev-and-revision-arent-returned-in-the-metadata-for-
      x-api-path-slug: metadatarootpath-get
      parameters:
      - in: query
        name: file_limit
        description: Default is 10,000 (max is 25,000)
      - in: query
        name: hash
        description: Each call to `/metadata` on a folder will return a `hash` field,
          generated by hashing all of the metadatacontained in that response
      - in: query
        name: include_deleted
        description: Only applicable when `list` is set
      - in: query
        name: include_media_info
        description: If `true`, each file will include a `photo_info` dictionary for
          photos and a `video_info` dictionaryfor videos with additional media info
      - in: query
        name: include_membership
        description: If `true`, metadata for a shared folder will include a list of
          members and a list of groups
      - in: query
        name: list
        description: The strings `true` and `false` are valid values
      - in: query
        name: locale
        description: The metadata returned will have its `size` field translated based
          on the given `locale`
      - in: path
        name: path
        description: The path to the file or folder
      - in: query
        name: rev
        description: If you include a particular revision number, then only the metadata
          for that revision will be returned
      - in: path
        name: root
        description: 'Root folder: `auto` - automatically determines the appropriate
          root folder using your apps permissionlevel (recommended); `sandbox` - the
          codename for app folder level; `dropbox` - full dropbox access'
      responses:
        200:
          description: OK
      tags:
      - Storage
      - Documents
      - Metadata
      - Root
      - Path
  /revisions/{root}/{path}:
    get:
      summary: Obtains metadata for all available revisions of a file, including the
        current revision.
      description: |-
        Obtains metadata for all available revisions of a file, including the current revision.

        Only revisions up to thirty days old are available (or more if the Dropbox user has
        [Extended Version History](https://www.dropbox.com/help/113)). You can use the revision number in conjunction
        with the `/restore` call to revert the file to its previous state.
      operationId: obtains-metadata-for-all-available-revisions-of-a-file-including-the-current-revisiononly-revisions-
      x-api-path-slug: revisionsrootpath-get
      parameters:
      - in: query
        name: locale
        description: The metadata returned will have its `size` field translated based
          on the given `locale`
      - in: path
        name: path
        description: The path to the file
      - in: query
        name: rev_limit
        description: Default is 10
      - in: path
        name: root
        description: 'Root folder: `auto` - automatically determines the appropriate
          root folder using your apps permissionlevel (recommended); `sandbox` - the
          codename for app folder level; `dropbox` - full dropbox access'
      responses:
        200:
          description: OK
      tags:
      - Storage
      - Documents
      - Revisions
      - Root
      - Path
  /restore/{root}/{path}:
    post:
      summary: Restores a file path to a previous revision.
      description: |-
        Restores a file path to a previous revision.

        Unlike downloading a file at a given revision and then re-uploading it, this call is atomic. It also saves
        a bunch of bandwidth.
      operationId: restores-a-file-path-to-a-previous-revisionunlike-downloading-a-file-at-a-given-revision-and-then-re
      x-api-path-slug: restorerootpath-post
      parameters:
      - in: formData
        name: locale
        description: The metadata returned will have its `size` field translated based
          on the given `locale`
      - in: path
        name: path
        description: The path to the file
      - in: formData
        name: rev
        description: The revision of the file to restore
      - in: path
        name: root
        description: 'Root folder: `auto` - automatically determines the appropriate
          root folder using your apps permissionlevel (recommended); `sandbox` - the
          codename for app folder level; `dropbox` - full dropbox access'
      responses:
        200:
          description: OK
      tags:
      - Storage
      - Documents
      - Restore
      - Root
      - Path
  /search/{root}/{path}:
    get:
      summary: Search for files and folders by name.
      description: |-
        Returns metadata for all files and folders whose filename contains the given search string as a substring.

        Searches are limited to the folder path and its sub-folder hierarchy provided in the call.

        **Note:** Recent changes may not immediately be reflected in search results due to a short delay in indexing.
      operationId: returns-metadata-for-all-files-and-folders-whose-filename-contains-the-given-search-string-as-a-subs
      x-api-path-slug: searchrootpath-get
      parameters:
      - in: query
        name: file_limit
        description: The maximum and default value is 1,000
      - in: query
        name: include_deleted
        description: If this parameter is set to `true`, then files and folders that
          have been deleted will also be includedin the search
      - in: query
        name: include_membership
        description: If `true`, metadata for a shared folder will include a list of
          members and a list of groups
      - in: query
        name: locale
        description: The metadata returned will have its `size` field translated based
          on the given `locale`
      - in: path
        name: path
        description: The path to the folder you want to search from
      - in: query
        name: query
        description: The search string
      - in: path
        name: root
        description: 'Root folder: `auto` - automatically determines the appropriate
          root folder using your apps permissionlevel (recommended); `sandbox` - the
          codename for app folder level; `dropbox` - full dropbox access'
      responses:
        200:
          description: OK
      tags:
      - Storage
      - Documents
      - Search
      - Root
      - Path
    post:
      summary: Search for files and folders by name.
      description: |-
        Returns metadata for all files and folders whose filename contains the given search string as a substring.

        Searches are limited to the folder path and its sub-folder hierarchy provided in the call.

        **Note:** Recent changes may not immediately be reflected in search results due to a short delay in indexing.
      operationId: returns-metadata-for-all-files-and-folders-whose-filename-contains-the-given-search-string-as-a-subs
      x-api-path-slug: searchrootpath-post
      parameters:
      - in: formData
        name: file_limit
        description: The maximum and default value is 1,000
      - in: formData
        name: include_deleted
        description: If this parameter is set to `true`, then files and folders that
          have been deleted will also be includedin the search
      - in: formData
        name: include_membership
        description: If `true`, metadata for a shared folder will include a list of
          members and a list of groups
      - in: formData
        name: locale
        description: The metadata returned will have its `size` field translated based
          on the given `locale`
      - in: path
        name: path
        description: The path to the folder you want to search from
      - in: formData
        name: query
        description: The search string
      - in: path
        name: root
        description: 'Root folder: `auto` - automatically determines the appropriate
          root folder using your apps permissionlevel (recommended); `sandbox` - the
          codename for app folder level; `dropbox` - full dropbox access'
      responses:
        200:
          description: OK
      tags:
      - Storage
      - Documents
      - Search
      - Root
      - Path
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