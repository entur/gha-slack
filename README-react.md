# `gha-slack/react`

Add an emoji reaction to a Slack message

## Usage

This workflow can be used to react to a Slack message using its `message_ts` (the unique message ID returned by `gha-slack/post`).

## Prerequisites

Please read the [prerequisites](/.github/README.md)

## Channel ID

The `channel_id` must be the channel ID, not the name of the Slack channel. You can find this under "channel details" in Slack.

## Examples

React to a message posted in the same workflow:

## Slack Emoji

Supports all emoji's added to Entur's slack organisation, ie:

- `white_check_mark` ✅ success / done
- `x` ❌ failure
- `rocket` 🚀 deployment / release
- `eyes` 👀 reviewing / taking a look
- `tada` 🎉 celebration
- `warning` ⚠️ warning
- `thumbsup` 👍 approval
- +++

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

| INPUT                                                                         | TYPE   | REQUIRED | DEFAULT | DESCRIPTION                                                                                                                                                                                                                                                                                      |
| ----------------------------------------------------------------------------- | ------ | -------- | ------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| <a name="input_channel_id"></a>[channel_id](#input_channel_id)                | string | true     |         | Slack channel ID where the <br>message was posted                                                                                                                                                                                                                                                |
| <a name="input_emoji"></a>[emoji](#input_emoji)                               | string | true     |         | Emoji name to react with (without colons). Common examples: <br>- `white_check_mark` ✅ success / done <br>- `x` ❌ failure <br>- `rocket` 🚀 deployment / release <br>- `eyes` 👀 reviewing / taking a look <br>- `tada` 🎉 celebration <br>- `warning` ⚠️ warning <br>- `thumbsup` 👍 approval |
| <a name="input_message_ts"></a>[message_ts](#input_message_ts)                | string | true     |         | Slack message timestamp (unique message ID) to <br>react to                                                                                                                                                                                                                                      |
| <a name="input_timeout_minutes"></a>[timeout_minutes](#input_timeout_minutes) | number | false    | `5`     | Job timeout in minutes                                                                                                                                                                                                                                                                           |

<!-- AUTO-DOC-INPUT:END -->

## Outputs

<!-- AUTO-DOC-OUTPUT:START - Do not remove or modify this section -->

No outputs.

<!-- AUTO-DOC-OUTPUT:END -->
