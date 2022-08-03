---
rank: 1
related_endpoints: []
related_guides: []
required_guides: []
related_resources: []
alias_paths: []
category_id: security
subcategory_id: null
is_index: false
id: security/fedramp-high
type: guide
total_steps: 3
sibling_id: security
parent_id: security
next_page_id: security/cors
previous_page_id: ''
source_url: >-
  https://github.com/box/developer.box.com/blob/main/content/guides/security/fedramp-high.md
---
# FedRAMP

## Overview

It is a certification program that allows federal agencies to use cloud
providers for increasingly secure/sensitive government or government-adjacent
data.

FedRAMP defines three categories regarding levels of security, Low, Moderate,
and High.

The higher the security level the more restrictions are in place.

Box is already certified as [FedRAMP Moderate and High][FedRAMPCert].

## Considerations

In order to be FedRAMP High compliant, your administrator must setup Box in
very a very specific way. It is possible that the administrator has further
restricted access to Box functionalities.

Consult with your administrator to identify security restrictions in place that
might affect the usage of the API.

## API usage in FedRAMP High

For FedRAMP high, Box uses a specific domain, `box-gov.com` and this affects
all API's entry points.

<!-- markdownlint-disable line-length -->

|FedRAMP Moderate |FedRAMP High       |
|-----------------|-------------------|
|account.box.com  |account.box-gov.com|
|api.box.com      |api.box-gov.com    |
|upload.box.com   |upload.box-gov.com |
|dl.boxcloud.com  |dl.boxcloud-gov.com|

<!-- markdownlint-enable line-length -->

## API Restrictions

The following API entry points are not available for usage under FedRAMP High configuration.

<!-- markdownlint-disable line-length -->

<!-- markdownlint-disable spelling -->

|API Entry points |
|----------------|
|/collaborations|
|/device_pinners|
|/enterprises/{enterprise_id}/device_pinners|
|/events|
|/files/{file_id}/collaborations|
|/files/{file_id}/metadata/global/boxSkillsCards|
|/folders/{folder_id}/collaborations|
|/folders/{folder_id}#add_shared_link|
|/folders/{folder_id}#get_shared_link|
|/folders/{folder_id}#remove_shared_link|
|/folders/{folder_id}#update_shared_link|
|/skill_invocations/{skill_id}|
|/web_links|

<!-- markdownlint-enable line-length -->

The following API entry points are not yet available for usage under FedRAMP
High configuration.

<!-- markdownlint-disable line-length -->

|API Entry point |
|----------------|
|/sign_requests|

<!-- markdownlint-enable line-length -->

<!-- ## Code Samples  Code samples allow you to bring in SDK, CLI, and cURL code samples. The ID needs to be an endpoint ID.  <Samples id='get_files_id' >

</Samples>

Make sure to close the HTML tag, either directly or like this.

<Samples id='get_files_id'>

</Samples>

## Messages

Messages are used to mark a text visually as being notable, a warning, or a sign
of danger.

<Message type='notice'>

A simple note

</Message>

<Message type='warning'>

A warning note

</Message>

<Message type='danger'>

A danger note

</Message>

Messages support a small size, and the content can include more Markdown text.

<Message size='small'>

# A title

A danger note with a markdown title and body.

</Message>

## Tabs

Not all code samples exist in the SDKs/CLI. You can add new code samples
for each language as follows.

<Tabs>

<Tab title='Node'>

```js
console.log('!')
```

</Tab>

<Tab title='.NET'>

```dotnet
// some .NET code
```

</Tab>

</Tabs>

## Links

We recommend using referenced links.

This would [look like this][1].

At the end of the document, define the link.

[1]: https://box.com

We provide ways to link to guides, endpoints,
and resources without hard-coding the locale.

[Get a file by ID][endpoint://get-files-id]

[File resource][resource://file]
-->

[FedRAMPCert]:https://marketplace.fedramp.gov/#!/product/box-enterprise-cloud-content-collaboration-platform/versus/box-enterprise-cloud-content-collaboration-platform---high?sort=productName&productNameSearch=box