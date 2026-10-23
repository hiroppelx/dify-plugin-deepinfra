# Privacy Policy

This plugin connects Dify to the [DeepInfra](https://deepinfra.com) inference API.

## Data sent to third parties

When you use a DeepInfra model in Dify, the plugin sends the data required for that
request to DeepInfra (`https://api.deepinfra.com`) over HTTPS:

- Prompts, conversation messages, system instructions, and tool definitions for chat
  models.
- Images included in a message, when you use a vision-capable model.
- Text to be embedded, for embedding models.
- Your DeepInfra API key, sent as the request's authorization header.

DeepInfra processes this data under its own terms. Review
[DeepInfra's privacy policy](https://deepinfra.com/privacy) before use.

## Data collected, stored, or logged by this plugin

The plugin does not collect or store any user data itself. It keeps no database or
files, does not send telemetry or analytics, and does not share data with any party
other than DeepInfra. It never logs prompts, responses, or API keys; the only thing it
logs is an error message when credential validation fails, written to the Dify plugin
runtime log. Your API key is stored by Dify as an encrypted credential, not by the
plugin.

## Contact

Questions about this policy: hiroppelx@gmail.com
