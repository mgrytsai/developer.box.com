---
rank: 5
related_endpoints:
  - get_files_id_content
  - post_files_content
  - post_files_id_content
related_guides: []
required_guides: []
alias_paths:
  - /docs/domain-whitelisting
  - /guides/api-calls/domain-whitelisting
category_id: api-calls
subcategory_id: null
is_index: false
id: api-calls/allowing-domain-access
type: guide
total_steps: 8
sibling_id: api-calls
parent_id: api-calls
next_page_id: api-calls/suppress-notifications
previous_page_id: api-calls/ensure-consistency
source_url: >-
  https://github.com/box/developer.box.com/blob/main/content/guides/api-calls/allowing-domain-access.md
---
# Allowing Domain Access

To use the Box APIs it is important that your application and users have access
to the following domains, where needed.

## File Preview

To enable file preview, your application might need to load javascript file from
the Box content delivery network (CDN). This file is loaded from the following
domains.

- `api.box.com`
- `boxcdn.net`
- `boxcloud.com`
- `dl2.boxcloud.com` to `dl20.boxcloud.com`

## File downloads

The following API domains are used to download files via the Box API.

- `api.box.com` to initially request a file to download
- `dl.boxcloud.com` to actually download files for authenticated users
- `public.boxcloud.com` to actually download files for unauthenticated users

<Message type='warning'>

Ensuring access to these domains is only a first step to downloading a file.
To download a file the users need to have proper access permissions and need
to be fully authenticated where needed.

</Message>

## File uploads

The following API domains are used to upload files via the Box API.

- `api.box.com` to start a file upload
- `upload.app.box.com` and `upload.box.com` to upload the file to Box