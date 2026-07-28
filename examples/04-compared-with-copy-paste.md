# 04. Compared with the copy-and-paste workflow

If you search for how to turn ChatGPT or Claude conversations into
spaced-repetition flashcards, the usual advice is one of these:

- ask the assistant to output CSV or TSV, then import that file into Anki
- run a browser extension that scrapes the chat page
- wire up AnkiConnect with a local script
- keep a note open and paste words across by hand

All of them work. The reason MindDory exists is that all of them are a second
job, and the second job is the part people quit.

## Side by side

| | Export workflow | MindDory MCP |
| --- | --- | --- |
| Setup | Install an extension or write a script, then keep it working | Connect once, magic-link sign-in |
| During the conversation | Nothing happens, you are accumulating a backlog | Words are captured as they come up |
| After the conversation | Ask for CSV, check the formatting, download, import, fix fields | Nothing to do |
| Deduplication | You reimport words you already know | Checks `get_known_words` first |
| Context | Usually lost, you get word and translation | Captured with the sentence it appeared in |
| Review scheduling | Starts when you get around to importing | Starts immediately, on SM-2 |
| When you skip a day | The backlog grows and the import gets bigger | There is no backlog to import |

## The honest limits

- The write tools require MindDory Premium. Read tools work on the free tier, so
  you can connect and query your deck without paying, but automatic capture is a
  paid feature.
- It captures into MindDory, not into Anki. If you want your cards to live in
  Anki specifically, the export workflow is still your answer.
- It needs an MCP-compatible client. That covers Claude and Cursor today, and the
  list keeps growing, but it is not every chat interface.

## Why this is not just an integration

An export step is not merely slower. It moves the work to a moment when the
motivation has gone. You capture words while you are curious about them, in the
sentence where you met them, or you capture them later from a list where they
have already stopped meaning anything. That difference is the whole product.
