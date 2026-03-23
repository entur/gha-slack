# `gha-slack/post`

Post a slack message

## Usage

This workflow can be used to send a plain text message or a rich message using [Block Kit](https://api.slack.com/tools/block-kit-builder)

Please read the [prerequisites](/.github/README.md)

## Channel name vs ID

The `channel_id` can be a Slack "channel name" when posting messages, but using the _Channel ID_ is recommended for future-proofing in case the channel is renamed. You can find this under "channel details" in Slack.

## Examples

Send plain message:

```yml
jobs:
  post-message-to-slack:
    uses: entur/gha-slack/.github/workflows/post.yml@v3
    with:
      channel_id: "CHANNEL_ID"
      message: "My message"
    secrets: inherit
```

Send message with blocks (JSON payload):

```yml
jobs:
  post-message-to-slack:
    uses: entur/gha-slack/.github/workflows/post.yml@v3
    with:
      channel_id: "CHANNEL_ID"
      message: "Message to use if blocks is not read"
      blocks: |
        [
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
    secrets: inherit
```

## Inputs

<!-- AUTO-DOC-INPUT:START - Do not remove or modify this section -->

|                                     INPUT                                     |  TYPE  | REQUIRED |          DEFAULT          |                                  DESCRIPTION                                   |
|-------------------------------------------------------------------------------|--------|----------|---------------------------|--------------------------------------------------------------------------------|
|              <a name="input_blocks"></a>[blocks](#input_blocks)               | string |  false   |                           |                The Slack blocks to include <br>in the message                  |
|        <a name="input_channel_id"></a>[channel_id](#input_channel_id)         | string |   true   |                           |               Slack channel id you wish <br>to post message to                 |
|             <a name="input_message"></a>[message](#input_message)             | string |  false   | `"Default slack message"` |                Simple plain text message to <br>post to Slack                  |
|          <a name="input_thread_ts"></a>[thread_ts](#input_thread_ts)          | string |  false   |                           | Post as a threaded reply <br>to this message_ts (the unique Slack message ID)  |
| <a name="input_timeout_minutes"></a>[timeout_minutes](#input_timeout_minutes) | number |  false   |            `5`            |                             Job timeout in minutes                             |

<!-- AUTO-DOC-INPUT:END -->

## Outputs

<!-- AUTO-DOC-OUTPUT:START - Do not remove or modify this section -->

|                              OUTPUT                              |                     VALUE                     |                                                                              DESCRIPTION                                                                               |
|------------------------------------------------------------------|-----------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <a name="output_message_ts"></a>[message_ts](#output_message_ts) | `"${{ jobs.slack-post.outputs.message_ts }}"` | Slack message timestamp, which serves <br>as the unique message ID. <br>Use as thread_ts to post <br>threaded replies, or with reactions.add/chat.update/chat.delete.  |

<!-- AUTO-DOC-OUTPUT:END -->
