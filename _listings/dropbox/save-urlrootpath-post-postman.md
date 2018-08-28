{
  "info": {
    "name": "Dropbox Core Save a file from the specified URL into Dropbox.",
    "_postman_id": "28602dee-569b-47be-8bcf-ecc51a60b8b8",
    "description": "Save a file from the specified URL into Dropbox.\n\nIf the given path already exists, the file will be renamed to avoid the conflict (e.g. `myfile (1).txt`).",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "Storage",
      "item": [
        {
          "id": "02934449-ccd6-40ec-bcdf-e08ffd931d69",
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
              "id": "fd6c5658-9b99-4d12-9955-abf40f0c6a63"
            }
          ]
        },
        {
          "id": "7148fc4a-77b5-48c6-bb83-44d3ae8745c4",
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
              "id": "ba8c2eb7-3009-41c2-95f8-641e8c9863ee"
            }
          ]
        },
        {
          "id": "4cbe4ace-c343-4adf-8019-32a231d1d914",
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
              "id": "56946a4b-2777-411d-835a-940c0ab6064f"
            }
          ]
        },
        {
          "id": "8b090ee7-616b-4390-97d7-f661c9d25451",
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
              "id": "ca9649d7-1023-4243-bffa-b238f2752f4e"
            }
          ]
        },
        {
          "id": "c57abf28-3093-4300-abd6-2ea24d271562",
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
              "id": "601887b4-5aed-499b-a35e-b02c579f1049"
            }
          ]
        },
        {
          "id": "780212fe-a4e9-4f0b-ae86-1c7f3a766414",
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
              "id": "a0e39033-42fd-4bdc-8440-6f0959c68834"
            }
          ]
        },
        {
          "id": "986575f6-8c51-4e4b-9fe5-cef58e6cc820",
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
              "id": "47bd78fb-de8e-439c-910a-8c64e0f4bd07"
            }
          ]
        },
        {
          "id": "76d8f3e1-48f3-4393-9d00-19192647a7c5",
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
              "id": "86edf4ca-cd83-4554-b824-40029f9363ac"
            }
          ]
        },
        {
          "id": "92e45b77-e8cc-4a79-9e82-4ecffe504082",
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
              "id": "9b7d7951-f92d-4e37-bc02-352ca937a1a9"
            }
          ]
        },
        {
          "id": "748593b7-2bb5-4dee-b113-9a1faad420de",
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
              "id": "e8792ded-6ab7-4690-a4e1-b69dc56f7255"
            }
          ]
        },
        {
          "id": "6a702592-c0af-4d52-bf3f-c1d972e2cb1b",
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
              "id": "36a8abb2-30a3-4cfd-b787-80151a47ef45"
            }
          ]
        },
        {
          "id": "05615002-5e8c-4ebc-b18e-866f51a434ff",
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
              "id": "2fae2138-9969-48f8-ac46-3bf76ff906f6"
            }
          ]
        },
        {
          "id": "c3d33cd1-b54e-4879-b335-352996121175",
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
              "id": "54133ecd-a8e5-4ee0-8430-a871de123197"
            }
          ]
        },
        {
          "id": "ac27254c-9250-42b5-8c63-38bb6db92f15",
          "name": "returns-a-list-of-all-shared-folders-the-authenticated-user-has-access-tothis-api-call-requires-full",
          "request": {
            "url": "http://api.dropbox.com/1/shared_folders?include_membership=%7B%7D",
            "method": "GET",
            "body": {
              "mode": "raw"
            },
            "description": "Returns a list of all shared folders the authenticated user has access to.\n\nThis API call requires Full Dropbox or File type [permissions](https://www.dropbox.com/developers/reference/devguide#app-permissions).\n\nNote that `same_team` is only present if the linked account is a member of a Dropbox for Business team,\nand `member_id` is only present when this endpoint is called by a Dropbox for Business app and the user\nis on that team.\n\nThe `membership` field only contains users who have joined the shared folder and does not include users who\nhave been invited but have not accepted. When the `active` field is `false`, it means that a user has left\na shared folder (but may still rejoin)."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "cc5d0c96-c205-453d-9b57-408af6e2b7fb"
            }
          ]
        },
        {
          "id": "7eea1172-123d-490f-aa61-4ca11473dfb9",
          "name": "returns-metadata-about-a-specific-shared-folderthis-api-call-requires-full-dropbox-or-file-type-perm",
          "request": {
            "url": {
              "protocol": "http",
              "host": "api.dropbox.com",
              "path": [
                "1",
                "shared_folders/:shared_folder_id"
              ],
              "query": [
                {
                  "key": "include_membership",
                  "value": "%7B%7D",
                  "disabled": false
                }
              ],
              "variable": [
                {
                  "id": "shared_folder_id",
                  "value": "{}",
                  "type": "string"
                }
              ]
            },
            "method": "GET",
            "body": {
              "mode": "raw"
            },
            "description": "Returns metadata about a specific shared folder.\n\nThis API call requires Full Dropbox or File type [permissions](https://www.dropbox.com/developers/reference/devguide#app-permissions).\n\nNote that `same_team` is only present if the linked account is a member of a Dropbox for Business team,\nand `member_id` is only present when this endpoint is called by a Dropbox for Business app and the user\nis on that team.\n\nThe `membership` field only contains users who have joined the shared folder and does not include users who\nhave been invited but have not accepted. When the `active` field is `false`, it means that a user has left\na shared folder (but may still rejoin)."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "f81c1d7e-aa1a-457a-8600-076aaa6bd9f0"
            }
          ]
        },
        {
          "id": "f325fa01-07e6-4e0b-be45-085ebd867ab5",
          "name": "save-a-file-from-the-specified-url-into-dropboxif-the-given-path-already-exists-the-file-will-be-ren",
          "request": {
            "url": {
              "protocol": "http",
              "host": "api.dropbox.com",
              "path": [
                "1",
                "save_url/:root/:path"
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
                  "key": "url",
                  "value": "{}",
                  "disabled": false,
                  "description": "The URL to be fetched"
                }
              ]
            },
            "description": "Save a file from the specified URL into Dropbox.\n\nIf the given path already exists, the file will be renamed to avoid the conflict (e.g. `myfile (1).txt`)."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "9e2b5443-7db6-4947-afb7-d63898c679c9"
            }
          ]
        }
      ]
    }
  ]
}