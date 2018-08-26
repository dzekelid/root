{
  "info": {
    "name": "Dropbox Core Creates and returns a copy_ref to a file.",
    "_postman_id": "cec1c34c-edf5-41e9-b720-c68bb7066b45",
    "description": "Creates and returns a `copy_ref` to a file.\n\nThis reference string can be used to copy that file to another user's Dropbox by passing it in as the\n`from_copy_ref` parameter on [/fileops/copy](https://www.dropbox.com/developers/core/docs#fileops-copy).",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "Storage",
      "item": [
        {
          "id": "fd23e92b-9022-4900-b2a0-d31e23f8462c",
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
              "id": "f4d944ce-4d66-4310-be6b-45320be9ea2a"
            }
          ]
        },
        {
          "id": "6572104d-dee2-4813-ad48-8a67bc68a482",
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
              "id": "6c37340f-d98c-45d9-a71f-0f8751db2290"
            }
          ]
        },
        {
          "id": "51523fff-79f2-4b14-a92e-20c6d4f00ac8",
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
              "id": "17e9484c-1e12-4b7c-b70f-05fa5986d21b"
            }
          ]
        },
        {
          "id": "17286f82-58a2-474a-97d6-1815e993e710",
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
              "id": "46ba06d2-2e27-438d-ac32-5f0a31e64f0e"
            }
          ]
        },
        {
          "id": "b1688a47-513a-473c-bb7f-6279acf4a996",
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
              "id": "00268aea-cfd2-4255-bc68-4d7f81ca1512"
            }
          ]
        },
        {
          "id": "d6b5b1c3-c152-41e5-801e-acd1fca61080",
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
              "id": "2249e284-75d9-4954-af16-e2f395e849e6"
            }
          ]
        },
        {
          "id": "81621f7e-34d4-460b-b4f3-3ef6959fb308",
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
              "id": "3f9496a1-cac3-4319-9c5c-57101118922a"
            }
          ]
        },
        {
          "id": "3c49a39c-af3e-4b23-bb74-785ac7b93221",
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
              "id": "7169df5c-e2c4-4b24-a209-d41a89b9a026"
            }
          ]
        },
        {
          "id": "919d11be-c3c9-4e98-a375-ad4ee271ca65",
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
              "id": "f54f97fb-9320-4ea2-8639-832211c41dd6"
            }
          ]
        },
        {
          "id": "07b936ca-ee1f-4951-b64c-2b7f9b69fe02",
          "name": "returns-metadata-for-all-files-and-folders-whose-filename-contains-the-given-search-string-as-a-subs",
          "request": {
            "url": {
              "protocol": "http",
              "host": "api.dropbox.com",
              "path": [
                "1",
                "search/:root/:path"
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
                  "key": "file_limit",
                  "value": "{}",
                  "disabled": false,
                  "description": "The maximum and default value is 1,000"
                },
                {
                  "key": "include_deleted",
                  "value": "{}",
                  "disabled": false,
                  "description": "If this parameter is set to `true`, then files and folders that have been deleted will also be includedin the search"
                },
                {
                  "key": "include_membership",
                  "value": "{}",
                  "disabled": false,
                  "description": "If `true`, metadata for a shared folder will include a list of members and a list of groups"
                },
                {
                  "key": "locale",
                  "value": "{}",
                  "disabled": false,
                  "description": "The metadata returned will have its `size` field translated based on the given `locale`"
                },
                {
                  "key": "query",
                  "value": "{}",
                  "disabled": false,
                  "description": "The search string"
                }
              ]
            },
            "description": "Returns metadata for all files and folders whose filename contains the given search string as a substring.\n\nSearches are limited to the folder path and its sub-folder hierarchy provided in the call.\n\n**Note:** Recent changes may not immediately be reflected in search results due to a short delay in indexing."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "1f35c6cd-7fb8-4d74-a660-1bd57cac590e"
            }
          ]
        },
        {
          "id": "bddc890a-5c01-4caf-ad60-b2d821583be0",
          "name": "creates-and-returns-a-shared-linkhttpswwwdropboxcomhelp167-to-a-file-or-folderdropbox-for-business-u",
          "request": {
            "url": {
              "protocol": "http",
              "host": "api.dropbox.com",
              "path": [
                "1",
                "shares/:root/:path"
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
                  "description": "Use to specify language settings for user error messages and other language specific text"
                },
                {
                  "key": "short_url",
                  "value": "{}",
                  "disabled": false,
                  "description": "When `true` (default), the URL returned will be shortened using the Dropbox URL shortener"
                }
              ]
            },
            "description": "Creates and returns a [shared link](https://www.dropbox.com/help/167) to a file or folder.\n\nDropbox for Business users can set restrictions on shared links; the `visibility` field indicates what\n(if any) restrictions are set on this particular link. Possible values include:\n  * `PUBLIC` - anyone can view\n  * `TEAM_ONLY` - only the owner's team can view\n  * `PASSWORD` - a password is required\n  * `TEAM_AND_PASSWORD` - a combination of `TEAM_ONLY` and `PASSWORD` restrictions\n  * `SHARED_FOLDER_ONLY` - only [members](https://www.dropbox.com/help/6636) of the enclosing shared folder can view\n\nNote that other values may be added at any time."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "4572e622-3048-4847-a77f-7432919a6522"
            }
          ]
        },
        {
          "id": "479af777-674b-45b1-afd0-30cce7c56891",
          "name": "returns-a-link-directly-to-a-filesimilar-to-shareshttpswwwdropboxcomdeveloperscoredocsshares-the-dif",
          "request": {
            "url": {
              "protocol": "http",
              "host": "api.dropbox.com",
              "path": [
                "1",
                "media/:root/:path"
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
                  "description": "Use to specify language settings for user error messages and other language specific text"
                }
              ]
            },
            "description": "Returns a link directly to a file.\n\nSimilar to [/shares](https://www.dropbox.com/developers/core/docs#shares). The difference is that this\nbypasses the Dropbox webserver, used to provide a preview of the file, so that you can effectively stream\nthe contents of your media. This URL should not be used to display content directly in the browser.\n\nThe `/media` link expires after four hours, allotting enough time to stream files, but not enough to leave\na connection open indefinitely."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "10860de6-c30a-47d2-abf4-b9add99318c8"
            }
          ]
        },
        {
          "id": "9296d822-303e-4707-996b-b43b6b402257",
          "name": "creates-and-returns-a-copy-ref-to-a-filethis-reference-string-can-be-used-to-copy-that-file-to-anoth",
          "request": {
            "url": {
              "protocol": "http",
              "host": "api.dropbox.com",
              "path": [
                "1",
                "copy_ref/:root/:path"
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
            "description": "Creates and returns a `copy_ref` to a file.\n\nThis reference string can be used to copy that file to another user's Dropbox by passing it in as the\n`from_copy_ref` parameter on [/fileops/copy](https://www.dropbox.com/developers/core/docs#fileops-copy)."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "4e8e772b-1fd5-4dfb-8c0c-30b99938952a"
            }
          ]
        }
      ]
    }
  ]
}