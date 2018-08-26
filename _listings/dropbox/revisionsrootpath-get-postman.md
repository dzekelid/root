{
  "info": {
    "name": "Dropbox Core Obtains metadata for all available revisions of a file, including the current revision.",
    "_postman_id": "fd815e3f-b892-4e27-950f-778ff406fdd9",
    "description": "Obtains metadata for all available revisions of a file, including the current revision.\n\nOnly revisions up to thirty days old are available (or more if the Dropbox user has\n[Extended Version History](https://www.dropbox.com/help/113)). You can use the revision number in conjunction\nwith the `/restore` call to revert the file to its previous state.",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "Storage",
      "item": [
        {
          "id": "2d3a0720-060b-4ce2-a865-d4e8d85f3647",
          "name": "this-endpoint-should-be-used-by-apps-transitioning-from-oauth-1-to-oauth-2-it-will-return-an-oauth-2",
          "request": {
            "url": "http://api.dropbox.com/1/oauth2/token_from_oauth1",
            "method": "POST",
            "body": {
              "mode": "raw"
            },
            "description": "This endpoint should be used by apps transitioning from OAuth 1 to OAuth 2. It will return an OAuth 2 token\nfor the authenticated user."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "eaf8fad0-880e-4713-90e1-693c239ab406"
            }
          ]
        },
        {
          "id": "de2cbc4d-7f70-4a35-b53f-c47c1ee07484",
          "name": "disables-the-access-token-used-to-authenticate-the-call-this-method-works-for-oauth-1-and-oauth-2-to",
          "request": {
            "url": "http://api.dropbox.com/1/disable_access_token",
            "method": "POST",
            "body": {
              "mode": "raw"
            },
            "description": "Disables the access token used to authenticate the call. This method works for OAuth 1 and OAuth 2 tokens."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "93963014-7ccd-419e-a360-13921d2b202a"
            }
          ]
        },
        {
          "id": "5b960b61-14f5-4d36-9024-c63cc3f91ed3",
          "name": "retrieves-information-about-the-users-account",
          "request": {
            "url": "http://api.dropbox.com/1/account/info?locale=%7B%7D",
            "method": "GET",
            "body": {
              "mode": "raw"
            },
            "description": "Retrieves information about the user's account."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "5b42704b-1d9e-4d14-bff9-d6fc75e508bc"
            }
          ]
        },
        {
          "id": "135b54c5-03db-423a-b845-06118b8ecebe",
          "name": "retrieves-file-and-folder-metadatanote-modified-rev-and-revision-arent-returned-in-the-metadata-for-",
          "request": {
            "url": {
              "protocol": "http",
              "host": "api.dropbox.com",
              "path": [
                "1",
                "metadata/:root/:path"
              ],
              "query": [
                {
                  "key": "file_limit",
                  "value": "%7B%7D",
                  "disabled": false
                },
                {
                  "key": "hash",
                  "value": "%7B%7D",
                  "disabled": false
                },
                {
                  "key": "include_deleted",
                  "value": "%7B%7D",
                  "disabled": false
                },
                {
                  "key": "include_media_info",
                  "value": "%7B%7D",
                  "disabled": false
                },
                {
                  "key": "include_membership",
                  "value": "%7B%7D",
                  "disabled": false
                },
                {
                  "key": "list",
                  "value": "%7B%7D",
                  "disabled": false
                },
                {
                  "key": "locale",
                  "value": "%7B%7D",
                  "disabled": false
                },
                {
                  "key": "rev",
                  "value": "%7B%7D",
                  "disabled": false
                }
              ],
              "variable": [
                {
                  "id": "path",
                  "value": "{}",
                  "type": "string"
                },
                {
                  "id": "root",
                  "value": "{}",
                  "type": "string"
                }
              ]
            },
            "method": "GET",
            "body": {
              "mode": "raw"
            },
            "description": "Retrieves file and folder metadata.\n\n**Note:** `modified`, `rev`, and `revision` aren't returned in the metadata for the root/top-level path."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "8acd680f-f713-411e-b90d-c44190effb7b"
            }
          ]
        },
        {
          "id": "7d76bdc7-4f40-43be-8516-d2e67ffef50e",
          "name": "a-way-of-letting-you-keep-up-with-changes-to-files-and-folders-in-a-users-dropboxyou-can-periodicall",
          "request": {
            "url": "http://api.dropbox.com/1/delta",
            "method": "POST",
            "body": {
              "mode": "urlencoded",
              "urlencoded": [
                {
                  "key": "cursor",
                  "value": "{}",
                  "disabled": false,
                  "description": "A string that is used to keep track of your current state"
                },
                {
                  "key": "include_media_info",
                  "value": "{}",
                  "disabled": false,
                  "description": "If `true`, each file will include a `photo_info` dictionary for photos and a `video_info` dictionary forvideos with additional media info"
                },
                {
                  "key": "locale",
                  "value": "{}",
                  "disabled": false,
                  "description": "The metadata returned will have its `size` field translated based on the given `locale`"
                },
                {
                  "key": "path_prefix",
                  "value": "{}",
                  "disabled": false,
                  "description": "If present, this parameter filters the response to only include entries at or under the specified path"
                }
              ]
            },
            "description": "A way of letting you keep up with changes to files and folders in a user's Dropbox.\n\nYou can periodically call `/delta` to get a list of \"delta entries\", which are instructions on how to\nupdate your local state to match the server's state.\n\nIf you use the `path_prefix` parameter, you must continue to pass the correct prefix on subsequent calls\nusing the returned cursor. You can switch the `path_prefix` on any existing cursor to a descendant of the\nexisting `path_prefix` on subsequent calls to `/delta`. For example if your cursor has no `path_prefix`,\nyou can switch to any `path_prefix`. If your cursor has a `path_prefix` of \"/Photos\", you can switch it\nto \"/Photos/Vacaction\".\n\nWhen `include_media_info` is specified, files will only appear in delta responses when the media info is\nready. If you use the `include_media_info` parameter, you must continue to pass the same value on subsequent\ncalls using the returned cursor.\n\n**Important:** Unfortunately it is not possible to model correct Dropbox response with Swagger specification,\ndue to [nested array](https://github.com/swagger-api/swagger-spec/issues/40) usage in delta response.\n\nSuccessful result [will return](https://gist.github.com/ando-takahiro/5203137) an array of delta `entries`.\nEach delta entry is a 2-item list of one of the following forms:\n\n  * `[, ]` - Indicates that there is a file/folder at the given path. You should add the entry\n  to your local state. The metadata value is the same as what would be returned by the `/metadata` call, except\n  folder metadata doesn't have `hash` or `contents` fields. To correctly process delta entries:\n    * If the new entry includes parent folders that don't yet exist in your local state, create those parent\n    folders in your local state.\n    * If the new entry is a file, replace whatever your local state has at path with the new entry.\n    * If the new entry is a folder, check what your local state has at ``. If it's a file, replace it\n    with the new entry. If it's a folder, apply the new `` to the folder, but don't modify the\n    folder's children. If your local state doesn't yet include this path, create it as a folder.\n    * If the new entry is a folder with the `read-only` field set to `true`, apply the read-only permission\n    recursively to all files within the shared folder.\n  * `[, null]` - Indicates that there is no file/folder at the given path. To update your local state\n  to match, anything at path and all its children should be deleted. Deleting a folder in your Dropbox will\n  sometimes send down a single deleted entry for that folder, and sometimes separate entries for the folder\n  and all child paths. If your local state doesn't have anything at path, ignore this entry.\n\n**Note:** Dropbox treats file names in a case-insensitive but case-preserving way. To facilitate this,\nthe `` values above are lower-cased versions of the actual path. The last path component of the\n`` value will be case-preserved."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "79b55e35-68df-4351-9da4-ee18b4811ee8"
            }
          ]
        },
        {
          "id": "9045e588-77cd-4044-8fb8-652b3bb36bcc",
          "name": "a-way-to-quickly-get-a-cursor-for-the-servers-state-for-use-with-deltaunlike-delta-deltalatest-curso",
          "request": {
            "url": "http://api.dropbox.com/1/delta/latest_cursor",
            "method": "POST",
            "body": {
              "mode": "urlencoded",
              "urlencoded": [
                {
                  "key": "include_media_info",
                  "value": "{}",
                  "disabled": false,
                  "description": "If `true`, the returned cursor will be encoded with `include_media_info` set to `true` for usewith `/delta`"
                },
                {
                  "key": "path_prefix",
                  "value": "{}",
                  "disabled": false,
                  "description": "If present, the returned cursor will be encoded with a `path_prefix` for the specified path for usewith `/delta`"
                }
              ]
            },
            "description": "A way to quickly get a cursor for the server's state, for use with `/delta`.\n\nUnlike `/delta`, `/delta/latest_cursor` does not return any entries, so your app will not know about any\nexisting files or folders in the Dropbox account. For example, if your app processes future delta entries\nand sees that a folder was deleted, your app won't know what files were in that folder. Use this endpoint\nif your app only needs to know about new files and modifications and doesn't need to know about files that\nalready exist in Dropbox.\n\nIf you need to build local state to match the server state in Dropbox, you should instead use `/delta`."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "2e582b61-e1db-4e02-879e-76ecd7dc4029"
            }
          ]
        },
        {
          "id": "a398931e-ebab-494d-bde0-fc664a202682",
          "name": "obtains-metadata-for-all-available-revisions-of-a-file-including-the-current-revisiononly-revisions-",
          "request": {
            "url": {
              "protocol": "http",
              "host": "api.dropbox.com",
              "path": [
                "1",
                "revisions/:root/:path"
              ],
              "query": [
                {
                  "key": "locale",
                  "value": "%7B%7D",
                  "disabled": false
                },
                {
                  "key": "rev_limit",
                  "value": "%7B%7D",
                  "disabled": false
                }
              ],
              "variable": [
                {
                  "id": "path",
                  "value": "{}",
                  "type": "string"
                },
                {
                  "id": "root",
                  "value": "{}",
                  "type": "string"
                }
              ]
            },
            "method": "GET",
            "body": {
              "mode": "raw"
            },
            "description": "Obtains metadata for all available revisions of a file, including the current revision.\n\nOnly revisions up to thirty days old are available (or more if the Dropbox user has\n[Extended Version History](https://www.dropbox.com/help/113)). You can use the revision number in conjunction\nwith the `/restore` call to revert the file to its previous state."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "a2c000e2-a5a1-44f3-b02f-24f6f5544b06"
            }
          ]
        }
      ]
    }
  ]
}