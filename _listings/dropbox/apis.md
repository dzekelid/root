---
name: Dropbox
x-slug: dropbox
description: Dropbox is a modern workspace designed to reduce busywork-so you can
  focus on the things that matter. Sign in and put your creative energy to work.
image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/184-dropbox.jpg
x-kinRank: "10"
x-alexaRank: "89"
tags: Root
created: "2018-08-26"
modified: "2018-08-26"
url: https://raw.githubusercontent.com/streamdata-gallery-topics/root/master/_listings/dropbox/apis.md
specificationVersion: "0.14"
apis:
- name: Dropbox Content API v1 - Downloads a file.
  x-api-slug: filesrootpath-get
  description: |-
    Downloads a file.

    This method also supports [HTTP Range Retrieval Requests](http://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.35.2)
    to allow retrieving partial file contents.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/184-dropbox.jpg
  humanURL: http://dropbox.com
  baseURL: https://api-content.dropbox.com//1
  tags: File Storage, Sharing, Storage, Storage, My API Stack, API LIfeyclessss, Indie
    EdTech Data Jam, Storage, Stack, Technology, Mobile, SaaS, internet, API Provider,
    API Service Provider, Profiles, Service API, Relative Data
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-topics/root/master/_listings/dropbox/filesrootpath-get-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-topics/root/master/_listings/dropbox/filesrootpath-get-openapi.md
- name: Dropbox Core API v1 - Retrieves file and folder metadata.
  x-api-slug: metadatarootpath-get
  description: |-
    Retrieves file and folder metadata.

    **Note:** `modified`, `rev`, and `revision` aren't returned in the metadata for the root/top-level path.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/184-dropbox.jpg
  humanURL: http://dropbox.com
  baseURL: https://api.dropbox.com//1
  tags: File Storage, Sharing, Storage, Storage, My API Stack, API LIfeyclessss, Indie
    EdTech Data Jam, Storage, Stack, Technology, Mobile, SaaS, internet, API Provider,
    API Service Provider, Profiles, Service API, Relative Data
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-topics/root/master/_listings/dropbox/metadatarootpath-get-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-topics/root/master/_listings/dropbox/metadatarootpath-get-openapi.md
- name: Dropbox Core API v1 - Obtains metadata for all available revisions of a file,
    including the current revision.
  x-api-slug: revisionsrootpath-get
  description: |-
    Obtains metadata for all available revisions of a file, including the current revision.

    Only revisions up to thirty days old are available (or more if the Dropbox user has
    [Extended Version History](https://www.dropbox.com/help/113)). You can use the revision number in conjunction
    with the `/restore` call to revert the file to its previous state.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/184-dropbox.jpg
  humanURL: http://dropbox.com
  baseURL: https://api.dropbox.com//1
  tags: File Storage, Sharing, Storage, Storage, My API Stack, API LIfeyclessss, Indie
    EdTech Data Jam, Storage, Stack, Technology, Mobile, SaaS, internet, API Provider,
    API Service Provider, Profiles, Service API, Relative Data
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-topics/root/master/_listings/dropbox/revisionsrootpath-get-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-topics/root/master/_listings/dropbox/revisionsrootpath-get-openapi.md
- name: Dropbox Core API v1 - Restores a file path to a previous revision.
  x-api-slug: restorerootpath-post
  description: |-
    Restores a file path to a previous revision.

    Unlike downloading a file at a given revision and then re-uploading it, this call is atomic. It also saves
    a bunch of bandwidth.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/184-dropbox.jpg
  humanURL: http://dropbox.com
  baseURL: https://api.dropbox.com//1
  tags: File Storage, Sharing, Storage, Storage, My API Stack, API LIfeyclessss, Indie
    EdTech Data Jam, Storage, Stack, Technology, Mobile, SaaS, internet, API Provider,
    API Service Provider, Profiles, Service API, Relative Data
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-topics/root/master/_listings/dropbox/restorerootpath-post-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-topics/root/master/_listings/dropbox/restorerootpath-post-openapi.md
- name: Dropbox Core API v1 - Search for files and folders by name.
  x-api-slug: searchrootpath-get
  description: |-
    Returns metadata for all files and folders whose filename contains the given search string as a substring.

    Searches are limited to the folder path and its sub-folder hierarchy provided in the call.

    **Note:** Recent changes may not immediately be reflected in search results due to a short delay in indexing.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/184-dropbox.jpg
  humanURL: http://dropbox.com
  baseURL: https://api.dropbox.com//1
  tags: File Storage, Sharing, Storage, Storage, My API Stack, API LIfeyclessss, Indie
    EdTech Data Jam, Storage, Stack, Technology, Mobile, SaaS, internet, API Provider,
    API Service Provider, Profiles, Service API, Relative Data
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-topics/root/master/_listings/dropbox/searchrootpath-get-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-topics/root/master/_listings/dropbox/searchrootpath-get-openapi.md
- name: Dropbox Core API v1 - Search for files and folders by name.
  x-api-slug: searchrootpath-post
  description: |-
    Returns metadata for all files and folders whose filename contains the given search string as a substring.

    Searches are limited to the folder path and its sub-folder hierarchy provided in the call.

    **Note:** Recent changes may not immediately be reflected in search results due to a short delay in indexing.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/184-dropbox.jpg
  humanURL: http://dropbox.com
  baseURL: https://api.dropbox.com//1
  tags: File Storage, Sharing, Storage, Storage, My API Stack, API LIfeyclessss, Indie
    EdTech Data Jam, Storage, Stack, Technology, Mobile, SaaS, internet, API Provider,
    API Service Provider, Profiles, Service API, Relative Data
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-topics/root/master/_listings/dropbox/searchrootpath-post-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-topics/root/master/_listings/dropbox/searchrootpath-post-openapi.md
- name: Dropbox Core API v1 - Creates and returns a shared link to a file or folder.
  x-api-slug: sharesrootpath-post
  description: |-
    Creates and returns a [shared link](https://www.dropbox.com/help/167) to a file or folder.

    Dropbox for Business users can set restrictions on shared links; the `visibility` field indicates what
    (if any) restrictions are set on this particular link. Possible values include:
      * `PUBLIC` - anyone can view
      * `TEAM_ONLY` - only the owner's team can view
      * `PASSWORD` - a password is required
      * `TEAM_AND_PASSWORD` - a combination of `TEAM_ONLY` and `PASSWORD` restrictions
      * `SHARED_FOLDER_ONLY` - only [members](https://www.dropbox.com/help/6636) of the enclosing shared folder can view

    Note that other values may be added at any time.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/184-dropbox.jpg
  humanURL: http://dropbox.com
  baseURL: https://api.dropbox.com//1
  tags: File Storage, Sharing, Storage, Storage, My API Stack, API LIfeyclessss, Indie
    EdTech Data Jam, Storage, Stack, Technology, Mobile, SaaS, internet, API Provider,
    API Service Provider, Profiles, Service API, Relative Data
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-topics/root/master/_listings/dropbox/sharesrootpath-post-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-topics/root/master/_listings/dropbox/sharesrootpath-post-openapi.md
- name: Dropbox Core API v1 - Returns a link directly to a file.
  x-api-slug: mediarootpath-post
  description: |-
    Returns a link directly to a file.

    Similar to [/shares](https://www.dropbox.com/developers/core/docs#shares). The difference is that this
    bypasses the Dropbox webserver, used to provide a preview of the file, so that you can effectively stream
    the contents of your media. This URL should not be used to display content directly in the browser.

    The `/media` link expires after four hours, allotting enough time to stream files, but not enough to leave
    a connection open indefinitely.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/184-dropbox.jpg
  humanURL: http://dropbox.com
  baseURL: https://api.dropbox.com//1
  tags: File Storage, Sharing, Storage, Storage, My API Stack, API LIfeyclessss, Indie
    EdTech Data Jam, Storage, Stack, Technology, Mobile, SaaS, internet, API Provider,
    API Service Provider, Profiles, Service API, Relative Data
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-topics/root/master/_listings/dropbox/mediarootpath-post-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-topics/root/master/_listings/dropbox/mediarootpath-post-openapi.md
- name: Dropbox Core API v1 - Creates and returns a copy_ref to a file.
  x-api-slug: copy-refrootpath-get
  description: |-
    Creates and returns a `copy_ref` to a file.

    This reference string can be used to copy that file to another user's Dropbox by passing it in as the
    `from_copy_ref` parameter on [/fileops/copy](https://www.dropbox.com/developers/core/docs#fileops-copy).
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/184-dropbox.jpg
  humanURL: http://dropbox.com
  baseURL: https://api.dropbox.com//1
  tags: File Storage, Sharing, Storage, Storage, My API Stack, API LIfeyclessss, Indie
    EdTech Data Jam, Storage, Stack, Technology, Mobile, SaaS, internet, API Provider,
    API Service Provider, Profiles, Service API, Relative Data
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-topics/root/master/_listings/dropbox/copy-refrootpath-get-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-topics/root/master/_listings/dropbox/copy-refrootpath-get-openapi.md
- name: Dropbox Core API v1 - Save a file from the specified URL into Dropbox.
  x-api-slug: save-urlrootpath-post
  description: |-
    Save a file from the specified URL into Dropbox.

    If the given path already exists, the file will be renamed to avoid the conflict (e.g. `myfile (1).txt`).
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/184-dropbox.jpg
  humanURL: http://dropbox.com
  baseURL: https://api.dropbox.com//1
  tags: File Storage, Sharing, Storage, Storage, My API Stack, API LIfeyclessss, Indie
    EdTech Data Jam, Storage, Stack, Technology, Mobile, SaaS, internet, API Provider,
    API Service Provider, Profiles, Service API, Relative Data
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-topics/root/master/_listings/dropbox/save-urlrootpath-post-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-topics/root/master/_listings/dropbox/save-urlrootpath-post-openapi.md
x-common:
- type: x-api-gallery
  url: http://donorschoose.api.gallery.streamdata.io
- type: x-api-stack
  url: http://dropbox.stack.network
- type: x-application-management
  url: https://www.dropbox.com/developers/apps
- type: x-base
  url: https://api.dropbox.com/
- type: x-blog
  url: https://blog.dropbox.com/
- type: x-blog-rss
  url: https://blog.dropbox.com/feed/
- type: x-branding
  url: https://www.dropbox.com/developers/reference/branding
- type: x-branding
  url: https://www.dropbox.com/branding
- type: x-contact-form
  url: https://www.dropbox.com/developers/contact
- type: x-crunchbase
  url: http://www.crunchbase.com/company/dropbox
- type: x-crunchbase
  url: https://crunchbase.com/organization/dropbox
- type: x-developer
  url: https://www.dropbox.com/developers
- type: x-email
  url: privacyshield@dropbox.com
- type: x-email
  url: privacy@dropbox.com
- type: x-email
  url: contractnotices@dropbox.com
- type: x-email
  url: copyright@dropbox.com
- type: x-email
  url: dispute-notice@dropbox.com
- type: x-faq
  url: https://www.dropbox.com/developers/support
- type: x-forum
  url: https://www.dropboxforum.com/hc/communities/public/topics/200209245-API-Development
- type: x-github
  url: https://github.com/dropbox
- type: x-pricing
  url: https://www.dropbox.com/plans
- type: x-privacy
  url: https://www.dropbox.com/privacy
- type: x-stack-overflow
  url: http://stackoverflow.com/questions/tagged/dropbox-api?sort=votes&pagesize=15
- type: x-support
  url: https://www.dropbox.com/help
- type: x-terms-of-service
  url: https://www.dropbox.com/privacy#terms
- type: x-transparency-report
  url: https://www.dropbox.com/transparency
- type: x-twitter
  url: https://twitter.com/dropbox
- type: x-webhooks
  url: https://www.dropbox.com/developers/webhooks/docs
- type: x-website
  url: http://dropbox.com
- type: x-website
  url: https://www.dropbox.com
include: []
maintainers:
- FN: Kin Lane
  x-twitter: apievangelist
  email: info@apievangelist.com
---