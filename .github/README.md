<h1 align="center">
      <img src="logo.jpg" width="96px" height="96px" />
      <br>entur/gha-slack<br>
</h1>

[![Entur/Slack/CI](https://github.com/entur/gha-slack/actions/workflows/ci.yml/badge.svg?event=pull_request)](https://github.com/entur/gha-slack/actions/workflows/ci.yml)

Easily post status updates to Slack

- [Slack post](../README-post.md)

### Example

Post a message to Slack after a successful Docker push:

```yaml
post-to-slack:
  uses: entur/gha-slack/.github/workflows/post.yml@v1
  with:
    needs: [docker-push]
    team: my-team
    channel: "CHNLID"
    image: ${{ needs.docker-push.outputs.image_name }}:${{ needs.docker-push.outputs.image_tag}}
    mode: ${{ github.server_url }}/${{ github.repository }}/actions/runs/${{ github.run_id }}
  secrets: inherit
```
