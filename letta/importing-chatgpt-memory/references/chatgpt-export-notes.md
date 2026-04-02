# ChatGPT export notes

## Official export instructions

If a user needs help obtaining their export, point them to OpenAI’s official help article:

- <https://help.openai.com/en/articles/7260999-how-do-i-export-my-chatgpt-history-and-data>

Prefer linking to the official article instead of copying its step-by-step instructions into this skill, since the export flow may change.

## What to expect in the zip

A typical ChatGPT export often contains:

- `conversations-000.json`, `conversations-001.json`, etc.
- `shared_conversations.json`
- `user.json`
- `user_settings.json`
- `export_manifest.json`
- images, audio, and other attachments

The conversation history is usually sharded across multiple `conversations-*.json` files.

## Conversation structure

Each shard contains a list of conversation objects. Each conversation usually includes:

- `title`
- `id`
- `conversation_id`
- `create_time`
- `update_time`
- `default_model_slug`
- `current_node`
- `mapping`

`mapping` is a graph, not a flat message array. For a readable transcript, the most useful simple approach is to follow the current branch from `current_node` back to the root and then reverse it.

## Hidden saved-memory context

Some exports include hidden system messages with empty visible content but important metadata.

Look for:

- `metadata.is_user_system_message`
- `metadata.is_visually_hidden_from_conversation`
- `metadata.user_context_message_data`

In recent exports, explicit ChatGPT saved memory often appears as:

- `about_user_message`
- `about_model_message`

Typical interpretation:
- `about_user_message`: stable facts ChatGPT believed about the user
- `about_model_message`: custom-instruction-like response preferences

## Practical implication

Do not rely on visible chat text alone. Hidden system/context messages may contain the clearest explicit memory in the export.
