# DeepInfra

DeepInfra serves open-weight LLMs and embedding models through an OpenAI-compatible
API at a low per-token price, and can be used directly from Dify.

## Features
- Provides `llm` and `text-embedding` models in Dify.
- Ships the full DeepInfra catalog: **106 chat models** and **24 embedding models**,
  so every model DeepInfra advertises is selectable without typing an ID.
- Capability flags are measured, not guessed: `context_size` and pricing come from
  DeepInfra's `/v1/openai/models` metadata, `vision` from its model tags, and
  `tool-call` from probing every chat model against the live API — 10 of the 106 do
  not support tool calling and are marked accordingly.
- Supports predefined model and customizable model configuration. Models DeepInfra
  adds after this release can be used immediately through **customizable model**
  configuration.

## Setup
1. Install this plugin from the Dify Marketplace.
2. Get an API key from [DeepInfra](https://deepinfra.com/dash/api_keys).
3. In Dify, open **Settings → Model Provider → DeepInfra** and enter the API key.
4. Save the configuration.

### Required credentials
- **API Key** (required): a DeepInfra API key. It is the only credential this plugin
  uses.

### Connection requirements
The Dify plugin runtime must be able to reach `https://api.deepinfra.com` over HTTPS
(outbound port 443). The plugin calls DeepInfra's OpenAI-compatible endpoint at
`https://api.deepinfra.com/v1/openai`; no other host is contacted. If your Dify
deployment uses an egress proxy, allow this host.

## Usage
Select **DeepInfra** as the model provider in Dify, choose an available model, and use
it in applications, agents, or workflows.

To use a model released after this plugin version, choose **Add Model**, enter the
DeepInfra model ID exactly as it appears on the
[DeepInfra models page](https://deepinfra.com/models), and set the context size and
capability flags to match that model.

### Reasoning models
Several DeepInfra models emit `reasoning_content` before their answer. With a small
`max_tokens` budget the whole allowance can be spent reasoning, leaving the visible
response empty. Give reasoning models at least ~1000 max tokens.

## Privacy
This plugin sends the inputs required by the selected operation to DeepInfra. See
[PRIVACY.md](PRIVACY.md) for details, and review
[DeepInfra's privacy policy](https://deepinfra.com/privacy) before use.

## Source and contact
- Source repository: https://github.com/hiroppelx/dify-plugin-deepinfra
- Issues: https://github.com/hiroppelx/dify-plugin-deepinfra/issues
- Contact: hiroppelx@gmail.com
