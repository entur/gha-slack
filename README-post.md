# post

Post a slack message

## Inputs

<!-- AUTO-DOC-INPUT:START - Do not remove or modify this section -->

|                                     INPUT                                     |  TYPE  | REQUIRED |    DEFAULT    |                  DESCRIPTION                  |
|-------------------------------------------------------------------------------|--------|----------|---------------|-----------------------------------------------|
|             <a name="input_channel"></a>[channel](#input_channel)             | string |   true   |               |                 Slack channel                 |
|                <a name="input_image"></a>[image](#input_image)                | string |  false   |    `"N/A"`    |                  Image name                   |
|                 <a name="input_mode"></a>[mode](#input_mode)                  | string |  false   |    `"CD"`     | What kind of event triggered <br>the message  |
|     <a name="input_release_name"></a>[release_name](#input_release_name)      | string |  false   | `"repo_name"` |       Release name, default $repo_name        |
|                 <a name="input_team"></a>[team](#input_team)                  | string |   true   |               |                   Team name                   |
| <a name="input_timeout_minutes"></a>[timeout_minutes](#input_timeout_minutes) | number |  false   |      `5`      |            Job timeout in minutes             |

<!-- AUTO-DOC-INPUT:END -->

## Outputs

<!-- AUTO-DOC-OUTPUT:START - Do not remove or modify this section -->
No outputs.
<!-- AUTO-DOC-OUTPUT:END -->
