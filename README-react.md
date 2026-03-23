# `gha-slack/react`

Add an emoji reaction to a Slack message

## Usage

This workflow can be used to react to a Slack message using its `message_ts` (the unique message ID returned by `gha-slack/post`).

Please read the [prerequisites](/.github/README.md)

## Examples

React to a message posted in the same workflow:

```yml
jobs:
  post-message:
    uses: entur/gha-slack/.github/workflows/post.yml@v3
    with:
      channel_id: "CHANNEL_ID"
      message: "Deployment started"
    secrets: inherit

  react-to-message:
    needs: post-message
    uses: entur/gha-slack/.github/workflows/react.yml@v3
    with:
      channel_id: "CHANNEL_ID"
      message_ts: ${{ needs.post-message.outputs.message_ts }}
      emoji: "white_check_mark"
    secrets: inherit
```

## Inputs

<!-- AUTO-DOC-INPUT:START - Do not remove or modify this section -->

|                                     INPUT                                     |  TYPE  | REQUIRED | DEFAULT |                                                                                                                             DESCRIPTION                                                                                                                              |
|-------------------------------------------------------------------------------|--------|----------|---------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|        <a name="input_channel_id"></a>[channel_id](#input_channel_id)         | string |   true   |         |                                                                                                          Slack channel ID where the <br>message was posted                                                                                                           |
|                <a name="input_emoji"></a>[emoji](#input_emoji)                | string |   true   |         | Emoji name to react with <br>(without colons). Common examples: white_check_mark ✅ <br>success / done x ❌ <br>failure rocket 🚀 deployment / <br>release eyes 👀 reviewing / <br>taking a look tada 🎉 <br>celebration warning ⚠️ warning thumbsup <br>👍 approval  |
|        <a name="input_message_ts"></a>[message_ts](#input_message_ts)         | string |   true   |         |                                                                                                     Slack message timestamp (unique message ID) to <br>react to                                                                                                      |
| <a name="input_timeout_minutes"></a>[timeout_minutes](#input_timeout_minutes) | number |  false   |   `5`   |                                                                                                                        Job timeout in minutes                                                                                                                        |

<!-- AUTO-DOC-INPUT:END -->

## Outputs

<!-- AUTO-DOC-OUTPUT:START - Do not remove or modify this section -->
No outputs.
<!-- AUTO-DOC-OUTPUT:END -->
