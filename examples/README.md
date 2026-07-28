# Examples: turn Claude and ChatGPT conversations into flashcards

Worked examples of the MindDory MCP server in use. Every example is a real
conversation shape you can copy, not pseudocode. They assume you have already
connected the server once (see [Connection](../README.md#connection)).

The point of all of them is the same: **you do not export anything.** There is no
copy and paste, no CSV file, no browser extension, and no AnkiConnect script. You
have a conversation in the language you are learning, and the vocabulary lands in
your spaced-repetition queue while you talk.

| Example | What it shows |
| --- | --- |
| [01. Capture words while chatting](01-capture-words-while-chatting.md) | The core loop: new words from a normal conversation become flashcards |
| [02. Review what is due](02-review-what-is-due.md) | Using the assistant as the review session instead of an app screen |
| [03. Log grammar mistakes](03-log-grammar-mistakes.md) | Turning errors you make into a reviewable pattern list |
| [04. Compared with the copy-and-paste workflow](04-compared-with-copy-paste.md) | Step-by-step against the usual export workaround |

## Which client?

Anything that speaks MCP. These examples were written against Claude, and the same
prompts work in any MCP-compatible client, including Cursor. The endpoint and the
tool list do not change per client.

## A note on honesty

The server is opt-in and it says so. On its first reply the assistant tells you it
is connected to MindDory and that it will add new vocabulary as you chat. If you
ask it what it has saved, it answers truthfully. Nothing is captured silently.
