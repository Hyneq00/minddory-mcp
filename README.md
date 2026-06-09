# MindDory MCP Server

The official [Model Context Protocol](https://modelcontextprotocol.io) server for
**[MindDory](https://minddory.com)**, an AI flashcard and vocabulary-learning app.

Connect MindDory to Claude (or any MCP-compatible client) and your AI becomes a
language study partner: as you chat in a language you are learning, it captures the
new words and phrases you meet into spaced-repetition flashcards, logs grammar
mistakes for review, and can quiz you on whatever is due today — all scoped to your
CEFR level and target language. Everything syncs with the MindDory apps (iOS,
Android, and web at [app.minddory.com](https://app.minddory.com)).

It is transparent and opt-in: you connect MindDory yourself, and on its first reply
the assistant tells you it is connected and will add new vocabulary as you chat. It
never captures silently, and it answers honestly if you ask what it has saved.

## Connection

- **Endpoint:** `https://api.minddory.com/v1/brain/mcp`
- **Transport:** streamable-http
- **Auth:** OAuth 2.1 (magic-link sign-in)
- **Hosting:** EU

### Add to Claude

Settings → Connectors → **Add custom connector** → paste the endpoint URL above,
then complete the magic-link sign-in. Setup guide: https://minddory.com/connect

## Tools

| Tool | Type | What it does |
| --- | --- | --- |
| `get_system_instructions` | read | Load the learner profile + study-partner role for the conversation |
| `get_user_profile` | read | CEFR level, target/native language, due-card count, weak words |
| `get_queue` | read | Cards due now and within 24 hours |
| `get_known_words` | read | Words verified known via flashcard practice |
| `get_active_vocab` | read | Most frequently encountered words (frontier vocabulary) |
| `get_card` | read | Single card detail (translation, mastery, recent events) |
| `get_recent_activity` | read | Recent interaction log |
| `capture_word` | write | Save a new word/phrase from chat into the deck |
| `capture_grammar_mistake` | write | Log a grammar mistake into the Grammar Patterns view |
| `mark_demonstrated` | write | Reinforce a word used correctly (SM-2 boost) |
| `mark_struggled` | write | Down-weight a word the user got wrong (SM-2) |
| `log_interaction` | write | Append a lookup / discussion / read-in-context signal |

Read tools are annotated `readOnlyHint`; write tools mutate only the user's own
deck and are additive (`destructiveHint: false`).

Built on the proven SM-2 spaced-repetition algorithm. Free to connect; advanced
spaced-repetition writes are part of MindDory Premium.

## Troubleshooting

- **No sign-in email / can't authorize.** Connecting sends a one-time magic link to your MindDory account email. Check spam, and use the same email as your MindDory account. Links expire after a short window; reconnect to get a fresh one.
- **"This tool requires an active MindDory Premium subscription" (HTTP 402).** The write tools (`capture_word`, `capture_grammar_mistake`, `mark_demonstrated`, `mark_struggled`, `log_interaction`) require MindDory Premium. Read tools work on the free tier. Upgrade in the app or at https://app.minddory.com.
- **Tools don't appear after connecting.** MCP clients cache the tool list; disconnect and reconnect the connector to refresh it.
- **Captured words aren't in the app.** New words sync to the "Chat Discoveries" folder. Re-open or pull-to-refresh the app, and confirm you're signed into the same account.
- **Wrong language captured.** Capture is scoped to a language code; if a word lands under the wrong language, tell the assistant the correct language and it will recapture.

Support: support@minddory.com

## Links

- Website: https://minddory.com
- Web app: https://app.minddory.com
- Connect guide: https://minddory.com/connect
- Privacy policy: https://minddory.com/privacy-policy
