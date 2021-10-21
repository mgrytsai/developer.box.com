---
rank: 25
required_guides:
  - authorization/custom-app-approval
  - authorization/limited-access-approval
  - authorization/custom-skill-approval
category_id: authorization
subcategory_id: null
is_index: true
id: authorization
type: guide
total_steps: 4
sibling_id: guides
parent_id: guides
next_page_id: ''
previous_page_id: authorization/common-errors
source_url: >-
  https://github.com/box/developer.box.com/blob/main/content/guides/authorization/index.md
---
# Authorization

Some applications require explicit Admin authorization before use with an
enterprise. The steps an Admin needs to take are dependent on the
developer-selected authentication method and enabled enterprise settings.

## Authentication methods

The following [authentication methods][auth] always require explicit Admin
authorization:

- [Server Authentication (with JWT)][jwt]
- [Server Authentication (with Client Credentials Grant)][cc]
- [Custom Skill][skill]

These authentication methods automatically generate a [Service Account][sa].
With the right [scopes][scopes] enabled, a Service Account can perform many
Admin actions, thus requiring Admin authorization before use. 

[OAuth 2.0][oauth] and [App Token][apptoken] apps may also require explicit
Admin authorization based on enabled enterprise settings. 

## Enterprise settings

Subsequent steps are required if any of the following enterprise settings are
enabled: 

- Disable published apps by default
- Disable unpublished apps by default
- Require manual admin authorization for transactional access apps

These [settings][setting] can be found by navigating to: 

**Admin Console** > **Apps** > **Custom Apps** > click the ⚙ icon

<Message tip>

Published apps are any applications that can be found in our App Gallery.

</Message>

## Required actions

To see what steps an Admin must complete for a given app, review the following
scenarios.

<!-- markdownlint-disable line-length -->

<!--alex ignore-->

**Disable published apps by default**:

| Authentication Method                            | Enabled                                     | Disabled
| ------------------------------------------------ | ------------------------------------------- | -------------- |
|[OAuth 2.0][standauth]                            | Set to available in individual app controls | Ready for use  |
|[Server Authentication (with JWT)][jwt]           | N/A                                         | N/A            |
|[Server Authentication (client credentials)][cc]  | N/A                                         | N/A            |
|[App Token Authentication][apptoken]              | N/A                                         | N/A            |

**Disable unpublished apps by default**:

| Authentication Method                            | Enabled                                                       | Disabled
| ------------------------------------------------ | ------------------------------------------------------------- | --------------------------------------- |
|[OAuth 2.0][standauth]                            | Add to allow list                                             | Ready for use                           |
|[Server Authentication (with JWT)][jwt]           | Authorize in **Apps** > **Custom Apps** and add to allow list | Authorize in **Apps** > **Custom Apps** |
|[Server Authentication (client credentials)][cc]  | Authorize in **Apps** > **Custom Apps** and add to allow list | Authorize in **Apps** > **Custom Apps** |
|[App Token Authentication][apptoken]              | Add to allow list                                             | Ready for use                           |

**Require manual admin authorization for transactional access apps**:

| Authentication Method                            | Enabled                                 | Disabled                                 |
| ------------------------------------------------ | ----------------------------------------| ---------------------------------------- |
|[OAuth 2.0][standauth]                            | N/A                                     | N/A                                      |
|[Server Authentication (with JWT)][jwt]           | N/A                                     | N/A                                      |
|[Server Authentication (client credentials)][cc]  | N/A                                     | N/A                                      |
|[App Token Authentication][apptoken]              | Authorize in **Apps** > **Custom Apps** | Automatically authorized upon creation   |

<!--alex enable-->

<!-- markdownlint-enable line-length -->

[auth]: g://authentication/select
<!-- i18n-enable localize-links -->

[setting]: https://support.box.com/hc/en-us/articles/360044196653-Managing-custom-apps
<!-- i18n-disable localize-links -->

[sa]: g://getting-started/user-types/service-account
[scopes]: g://api-calls/permissions-and-errors/scopes
[ag]: g://applications/app-gallery
[standauth]: g://authentication/oauth2
[jwt]: g://authentication/jwt
[cc]: g://authentication/client-credentials
[apptoken]: g://authentication/app-token
[skill]: g://applications/custom-skills
[oauth]: g://authentication/oauth2