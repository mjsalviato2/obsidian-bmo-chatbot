# obsidian-bmo-chatbot

Brainstorm ideas and generate text without leaving your Obsidian notes. This Obsidian plugin for Ollama and other LLM providers lets you ask questions about the current note, use reusable chatbot profiles, and save conversations as Markdown.

## Features

- Connect to local models through Ollama, LM Studio, or OpenAI-compatible endpoints, or use hosted providers such as Anthropic, Google Gemini, Mistral AI, OpenAI, and OpenRouter.
- Create chatbot profiles with specific knowledge, personalities, and presets.
- Generate responses from the editor with BMO Generate or the Prompt Select Generate command.
- Reference the current note in chat and render responses with Obsidian Markdown, including code blocks.
- Save and load conversations as Markdown notes, or append the current conversation to the active note.

## Installation

You need Obsidian and a working model provider. Local providers require a running API server; hosted providers may require an API key.

To build from a local checkout, install Node.js and npm, then run:

```sh
cd obsidian-bmo-chatbot
npm install
npm run build
```

Copy the built `main.js`, `manifest.json`, and `styles.css` if present into your vault's `.obsidian/plugins/obsidian-bmo-chatbot/` directory. Reload Obsidian and enable the plugin under Settings → Community plugins. Use the plugin ID in `manifest.json` as the directory name if it differs.

**Release download template:** replace `OWNER` with this standalone project's GitHub owner. The command assumes a release asset named `obsidian-bmo-chatbot-v0.1.0.zip` has been published on its GitHub releases page; availability is not established by the donor data.

```sh
curl -fL "https://github.com/OWNER/obsidian-bmo-chatbot/releases/download/v0.1.0/obsidian-bmo-chatbot-v0.1.0.zip" -o obsidian-bmo-chatbot-v0.1.0.zip
```

## Usage

This is an Obsidian plugin, not a terminal application. After enabling it, open its settings and enter your provider's API key or REST API URL. For Ollama or LM Studio, start the local server first. Click the bot icon in Obsidian's left sidebar to open the chat panel.

For example, with a model named `llama2` available from your configured provider, enter these commands in chat:

```text
/model "llama2"
/ref on
/temp 0.7
Suggest a clearer outline for the current note.
/save
```

Replace `llama2` with a model your provider actually offers. `/ref on` enables current-note references; `/save` saves the conversation to a note.

Use `/profile [PROFILE-NAME]` to choose a configured profile, `/append` to append the conversation to the active note, and `/load` to list or load saved chats. Enter `/help` for the command list.

**Check your note before enabling references.** With a hosted provider, referenced note content is sent to that provider as part of the request.

## License

MIT. This project is based on [longy2k/obsidian-bmo-chatbot](https://github.com/longy2k/obsidian-bmo-chatbot), which is also MIT-licensed. Retain the upstream copyright notice and MIT permission notice in copies or substantial portions of its code.

## Related projects

The supplied related-project list contains the repositories below. Their functionality and shared authorship were not documented in the source material, so no feature claims are made here.

- [sakthivelj10-ai/kstone](https://github.com/sakthivelj10-ai/kstone): consult its README for its purpose and usage.
- [serkantan215-cloud/axe](https://github.com/serkantan215-cloud/axe): consult its README for its purpose and usage.
- [boostlyapi/autonomous-agentic-rag](https://github.com/boostlyapi/autonomous-agentic-rag): consult its README for its purpose and usage.

