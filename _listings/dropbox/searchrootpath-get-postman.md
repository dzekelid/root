{
  "info": {
    "name": "Dropbox Core Search for files and folders by name.",
    "_postman_id": "1af455e3-3672-479c-ae3a-08754c75a023",
    "description": "Returns metadata for all files and folders whose filename contains the given search string as a substring.\n\nSearches are limited to the folder path and its sub-folder hierarchy provided in the call.\n\n**Note:** Recent changes may not immediately be reflected in search results due to a short delay in indexing.",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "Storage",
      "item": [
        {
          "id": "01d258d5-19d8-454d-a884-0023c81a8f67",
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
              "id": "e7ac599c-78e2-4182-8978-968b08c6a817"
            }
          ]
        },
        {
          "id": "8578f1cf-b6d8-4c4b-99e5-20d83408d98b",
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
              "id": "630b032c-37fa-40f9-ae4c-4ee22f0f35aa"
            }
          ]
        },
        {
          "id": "360d5a24-20a8-4ea9-a14e-760e40b9df9d",
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
              "id": "f148f96e-b41d-4c86-8b51-c757b03cbd55"
            }
          ]
        },
        {
          "id": "81bb556c-dbb2-484f-9158-0f30a6f4132d",
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
              "id": "8c165eac-46fe-42c9-b6ee-fae5250eff93"
            }
          ]
        },
        {
          "id": "a011c64f-20fe-4c6d-a741-226e22c78b37",
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
              "id": "2defc6a4-68a0-48f3-9252-ef2451049dab"
            }
          ]
        },
        {
          "id": "e1453c78-58a5-4b7f-96cb-49ea2936c150",
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
              "id": "8f29687a-c732-4f0f-98da-05b0622ef9d3"
            }
          ]
        },
        {
          "id": "b74f8976-40b3-44f9-a155-790417f56658",
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
              "id": "332a34ad-4924-4ec8-85cd-eda346bbeb98"
            }
          ]
        },
        {
          "id": "35626771-bde3-4504-a011-959086670410",
          "name": "restores-a-file-path-to-a-previous-revisionunlike-downloading-a-file-at-a-given-revision-and-then-re",
          "request": {
            "url": {
              "protocol": "http",
              "host": "api.dropbox.com",
              "path": [
                "1",
                "restore/:root/:path"
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
            "method": "POST",
            "body": {
              "mode": "urlencoded",
              "urlencoded": [
                {
                  "key": "locale",
                  "value": "{}",
                  "disabled": false,
                  "description": "The metadata returned will have its `size` field translated based on the given `locale`"
                },
                {
                  "key": "rev",
                  "value": "{}",
                  "disabled": false,
                  "description": "The revision of the file to restore"
                }
              ]
            },
            "description": "Restores a file path to a previous revision.\n\nUnlike downloading a file at a given revision and then re-uploading it, this call is atomic. It also saves\na bunch of bandwidth."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "5f419301-2dda-4293-aede-f3e8da408a46"
            }
          ]
        },
        {
          "id": "aa948d26-8e39-424c-ab28-9d50139f3689",
          "name": "returns-metadata-for-all-files-and-folders-whose-filename-contains-the-given-search-string-as-a-subs",
          "request": {
            "url": {
              "protocol": "http",
              "host": "api.dropbox.com",
              "path": [
                "1",
                "search/:root/:path"
              ],
              "query": [
                {
                  "key": "file_limit",
                  "value": "%7B%7D",
                  "disabled": false
                },
                {
                  "key": "include_deleted",
                  "value": "%7B%7D",
                  "disabled": false
                },
                {
                  "key": "include_membership",
                  "value": "%7B%7D",
                  "disabled": false
                },
                {
                  "key": "locale",
                  "value": "%7B%7D",
                  "disabled": false
                },
                {
                  "key": "query",
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
            "description": "Returns metadata for all files and folders whose filename contains the given search string as a substring.\n\nSearches are limited to the folder path and its sub-folder hierarchy provided in the call.\n\n**Note:** Recent changes may not immediately be reflected in search results due to a short delay in indexing."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "4a0ca736-e1eb-403b-87ea-6ed2e0a3b643"
            }
          ]
        }
      ]
    }
  ]
}