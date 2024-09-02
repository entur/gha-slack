# `gha-slack/post`

Post a slack message

## Usage

The workflow can be used to send a plain text message og a rich message using Block Kit (https://api.slack.com/tools/block-kit-builder).

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

Send message with blocks (JSON payload):

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

|                                     INPUT                                     |  TYPE  | REQUIRED | DEFAULT |                            DESCRIPTION                             |
|-------------------------------------------------------------------------------|--------|----------|---------|--------------------------------------------------------------------|
|              <a name="input_blocks"></a>[blocks](#input_blocks)               | string |  false   |         | The Slack blocks to include <br>in the message (as a JSON string)  |
|        <a name="input_channel_id"></a>[channel_id](#input_channel_id)         | string |   true   |         |         Slack channel id you wish <br>to post message to           |
|             <a name="input_message"></a>[message](#input_message)             | string |  false   |         |          Simple plain text message to <br>post to Slack            |
| <a name="input_timeout_minutes"></a>[timeout_minutes](#input_timeout_minutes) | number |  false   |   `5`   |                       Job timeout in minutes                       |

<!-- AUTO-DOC-INPUT:END -->

## Outputs

<!-- AUTO-DOC-OUTPUT:START - Do not remove or modify this section -->
No outputs.
<!-- AUTO-DOC-OUTPUT:END -->
