---
name: AWS API Gateway
x-slug: aws-api-gateway
description: Amazon API Gateway is a fully managed service that makes it easy for
  developers to create, publish, maintain, monitor, and secure APIs at any scale.
  With a few clicks in the AWS Management Console, you can create an API that acts
  as a front door for applications to access data, business logic, or functionality
  from your back-end services, such as workloads running on Amazon Elastic Compute
  Cloud, code running on AWS Lambda, or any Web application. Amazon API Gateway handles
  all the tasks involved in accepting and processing up to hundreds of thousands of
  concurrent API calls, including traffic management, authorization and access control,
  monitoring, and API version management. Amazon API Gateway has no minimum fees or
  startup costs. You pay only for the API calls you receive and the amount of data
  transferred out.
image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/aws-api-gateway-icon.png
x-kinRank: "10"
x-alexaRank: "0"
tags: Root
created: "2018-08-28"
modified: "2018-08-28"
url: https://raw.githubusercontent.com/streamdata-gallery-topics/root/master/_listings/aws-api-gateway/apis.md
specificationVersion: "0.14"
apis:
- name: AWS API Gateway API - Root Service
  x-api-slug: get
  description: Represents the root of the Amazon API Gateway control service.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/aws-api-gateway-icon.png
  humanURL: https://aws.amazon.com/api-gateway/
  baseURL: :///
  tags: Amazon Web Services, Gateway, Stack Network, API Service Provider, API Service
    Provider, API Provider, Deployments, Profiles, Relative Data
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-topics/root/master/_listings/aws-api-gateway/get-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-topics/root/master/_listings/aws-api-gateway/get-openapi.md
x-common:
- type: x-api-gallery
  url: http://awhere.api.gallery.streamdata.io
- type: x-api-stack
  url: http://aws.api.gateway.stack.network
- type: x-documentation
  url: https://docs.aws.amazon.com/apigateway/api-reference/
- type: x-faq
  url: https://aws.amazon.com/api-gateway/faqs/
- type: x-getting-started
  url: https://aws.amazon.com/api-gateway/getting-started/
- type: x-partners
  url: https://aws.amazon.com/api-gateway/partners/
- type: x-pricing
  url: https://aws.amazon.com/api-gateway/pricing/
- type: x-website
  url: https://aws.amazon.com/api-gateway/
include: []
maintainers:
- FN: Kin Lane
  x-twitter: apievangelist
  email: info@apievangelist.com
---