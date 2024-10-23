<h1 align="center">
      <img src="logo.jpg" width="96px" height="96px" />
      <br>entur/gha-slack<br>
</h1>

[![Entur/Slack/CI](https://github.com/entur/gha-slack/actions/workflows/ci.yml/badge.svg?event=pull_request)](https://github.com/entur/gha-slack/actions/workflows/ci.yml)

Easily post messages to Slack

## Prereqs

The Slack integration application needs to have access to your slack channel. In your designated slack channel enter the following command(message):

* `/invite @GitHub Actions Slack send`

You can now send messages using the slack-send action. The SLACK_BOT_TOKEN is already provided in our organisation.

## Reusable workflows documentation

* [Slack post](../README-post.md)
