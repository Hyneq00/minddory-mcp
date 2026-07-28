# 03. Log grammar mistakes as a reviewable pattern

**The problem this solves:** vocabulary is easy to track because a word is a
thing you can put on a card. Grammar mistakes are not, so they usually get
corrected once in conversation and then repeated forever.

## Prompt

```
Keep talking to me in Italian, but correct me when I get grammar wrong.
Do not stop the conversation to lecture me. Log each mistake in MindDory
so I can see the pattern later, then carry on.
```

## What happens

1. You make a mistake. The assistant gives you a short correction inline, so the
   conversation keeps its rhythm.
2. It calls `capture_grammar_mistake` with what you wrote, the correction, and
   the underlying rule.
3. Those entries build up in the **Grammar Patterns** view in the MindDory apps,
   where the point is not the individual slip but the repeated one.

## The follow-up that makes it worth doing

```
Look at the grammar mistakes I have logged.
What am I getting wrong repeatedly, and what is the one rule
that would fix the most of them?
```

This is the question a single correction in a chat window can never answer,
because nothing was keeping score. Once the mistakes are logged, the pattern is
visible: it is usually two or three rules causing most of the errors, not fifty
separate mysteries.

## Combining it with vocabulary capture

Nothing stops you doing both at once, and it is the natural way to use it:

```
Conversation practice in Italian, B2 level.
Capture new vocabulary, log my grammar mistakes, and at the end give me
a two-line summary of what I should work on before we talk again.
```
