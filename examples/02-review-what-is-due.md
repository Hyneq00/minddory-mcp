# 02. Review what is due, in the chat

**The problem this solves:** spaced repetition works, but opening a flashcard app
and tapping through cards is a separate chore. If you are already talking to an
assistant every day, the review can happen there.

## Prompt

```
What do I have due in MindDory today?
Quiz me on it, one word at a time, in context rather than as a bare
translation. Do not show me the answer until I have guessed.
```

## What happens

1. The assistant calls `get_queue` for the cards due now and in the next 24 hours.
2. It quizzes you conversationally: a sentence with the word missing, a
   definition to name, or a situation where you would need the word.
3. When you get one right it calls `mark_demonstrated`; when you get one wrong it
   calls `mark_struggled`. Both feed the same SM-2 schedule the apps use, so the
   review counts. You are not doing a shadow session that gets thrown away.

## Useful follow-ups

See where you actually stand:

```
Which of my words am I struggling with most? Show me the weak ones
and help me build a memory hook for each.
```

Focus the session:

```
Only quiz me on verbs today, and give me each one in a sentence
I might actually say.
```

Understand a single card:

```
Tell me everything MindDory knows about the word "aprovechar":
when I first met it, how often I have got it right, and when it is due next.
```

That last one uses `get_card` and `get_recent_activity`, which is also the
fastest way to check that the connection is genuinely reading your account and
not making things up.
