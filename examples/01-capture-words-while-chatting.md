# 01. Capture words while chatting

**The problem this solves:** you practise a language by chatting with an AI, you
meet useful words, and by next week you have forgotten all of them. The usual
answer is to keep a second window open and paste words into a flashcard app. This
is the version where you do not have to.

## Prompt

Paste this at the start of a conversation:

```
Let's have a conversation in Spanish. I am around B1.
Talk to me naturally, and whenever a word or phrase comes up that is
probably new for me, capture it into MindDory so I can review it later.
Tell me what you captured at the end.
```

## What happens

1. The assistant calls `get_system_instructions` and `get_user_profile` to load
   your CEFR level, target language, and native language, so it pitches the
   conversation at the right level instead of guessing.
2. You chat. When a word appears that is outside your known set, the assistant
   calls `capture_word` with the word, its context, and the language code.
3. Captured words land in the **Chat Discoveries** folder in the MindDory apps
   and enter the review schedule immediately.
4. If you use a word correctly during the conversation, the assistant can call
   `mark_demonstrated`, which nudges that card forward instead of drilling you on
   something you have clearly got.

## Variations worth trying

Ask for a specific domain, and the capture follows:

```
Let's talk about cooking in French. I want kitchen vocabulary specifically.
Capture anything I would need to follow a recipe.
```

Read something together, and capture as you go:

```
I am going to paste three paragraphs of a German news article.
Explain the hard parts at my level, and capture the vocabulary I will need
if I want to read this newspaper regularly.
```

Ask what it saved, at any point:

```
What have you captured so far today, and why those words?
```

## What it does not do

It does not capture silently, it does not capture words you already know (it
checks `get_known_words` first), and it does not touch anything outside your own
deck. Write tools require MindDory Premium; read tools work on the free tier.
