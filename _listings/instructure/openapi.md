swagger: "2.0"
x-collection-name: Instructure
x-complete: 1
info:
  title: Instructure Canvas Utility APIs
  description: canvas-lms-includes-a-rest-api-for-accessing-and-modifying-data-externally-from-the-main-application-in-your-own-programs-and-scripts--
  termsOfService: https://www.canvaslms.com/policies/api-policy
  version: v1
host: canvas.instructure.com
basePath: /api/v1
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /courses/{course_id}/root_outcome_group:
    get:
      summary: Redirect to root outcome group for context
      description: Redirect to root outcome group for context.
      operationId: redirect-to-root-outcome-group-for-context
      x-api-path-slug: coursescourse-idroot-outcome-group-get
      responses:
        "":
          description: ""
        400:
          description: Bad input parameter
        401:
          description: Bad or expired token
        403:
          description: Bad OAuth request (wrong consumer key, bad nonce, expired timestamp
        404:
          description: File or folder not found at the specified path
        405:
          description: Request method not expected (generally should be GET or POST)
        429:
          description: Your app is making too many requests and is being rate limited
        503:
          description: If the response includes the Retry-After header, this means
            your OAuth 1
        507:
          description: User is over Dropbox storage quota
        5xx:
          description: Server error
        200:
          description: OK
      tags:
      - Courses
      - Course
      - Id
      - Root
      - Outcome
      - Group
  /global/root_outcome_group:
    get:
      summary: Redirect to root outcome group for context
      description: Redirect to root outcome group for context.
      operationId: redirect-to-root-outcome-group-for-context
      x-api-path-slug: globalroot-outcome-group-get
      responses:
        200:
          description: OK
      tags:
      - Global
      - Root
      - Outcome
      - Group