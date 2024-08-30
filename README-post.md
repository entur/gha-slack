# `gha-slack/post`

Post a slack message

## Usage

The workflow checks if the blocks input is provided. If blocks are provided, they are used in the payload; otherwise, the plain text message is sent.

## Examples

Send plain message:

```yml
jobs:
  post-message-to-slack:
    uses: entur/gha-slack/.github/workflows/post.yml@v2
    with:
      channel: "CHANNEL_ID"
      message: "My message"
    secrets: inherit
```

Send message with blocks:

```yml
jobs:
  post-message-to-slack:
    uses: entur/gha-slack/.github/workflows/post.yml@v2
    with:
      channel: "CHANNEL_ID"
      blocks: |
        {
         	"blocks": [
          		{
         			"type": "section",
         			"text": {
          				"type": "mrkdwn",
          				"text": "*My message!* :rocket:"
         			}
          		},
          		{
         			"type": "divider"
          		},
          		{
         			"type": "section",
         			"fields": [
          				{
         					"type": "mrkdwn",
         					"text": "*Field 1:*\nThis is field 1"
          				},
          				{
         					"type": "mrkdwn",
         					"text": "*Field 2:*\nThis is field 2"
          				}
         			]
          		}
         	]
        }
    secrets: inherit
```

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
