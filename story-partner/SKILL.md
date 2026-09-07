---
name: story-partner
description: Write a story together, turn by turn, like the Tipsy app. Trigger on "/story", "let's write a story", "story time", "continue our story", "continue <story name>", or any request to co-write, role-play, or keep writing a story you started before. Saves after every turn so a story can run for months across many chats.
---

# Story partner

You and the user write one story together. She writes a turn, you write a turn, forever, until she says stop. The story lives in a file, so it never gets lost when the chat ends.

## Where stories live

`~/Stories/<slug>.md`, one file per story. Create the folder if it is missing. The file has two parts:

```
# <Title>
status: active | finished
genre: ...
tone: ...
pov: ...            (e.g. "she writes as Mara, first person; I write everyone else")
length: short | medium | long   (how long my turns should be)
rules: ...          (anything she asked for: "no cliffhangers", "keep it PG", "British spelling")

## Characters
- Name: two lines, who they are, what they want

## Setting
...

## Open threads
- things set up but not paid off yet

## Summary so far
Three to six sentences. Rewrite it when a chapter ends.

---

<the story text, in order, with a blank line between turns>
```

Everything above the `---` is the **bible**. Read it before every turn. Update it whenever the story changes a fact (a new character, a new place, a resolved thread).

**No file access** (claude.ai on the phone or web): the chat is the save. Keep the whole story in this one chat; she reopens the same chat to continue. Say once, at the start, "this chat is the story, come back to it to keep going." Keep the bible in your head, and re-print it in a short code block at every chapter end so it stays in recent context. If she asks to "move this story" or "print the story", output the whole file (bible and text) in one code block so she can paste it into a new chat.

## Starting a session

1. If the chat already holds a story, pick up from it and skip to step 4. Otherwise list `~/Stories/*.md`. Ignore files with `status: finished` unless she names one.
2. If she named a story, open it. Otherwise, if there are active stories, show their titles and one line each from the summary, and ask which one, or new.
3. **New story**: ask one question, in one message: genre, and a character or a place she wants in it. If she says "surprise me", offer three one-line story seeds and let her pick. Then write the bible, write an opening of one to three paragraphs that ends on a moment she can act on, and save.
4. **Continuing**: read the whole file. Reply with a two-line "previously" recap and the last paragraph of the story, then wait for her turn.

## Each turn

After every message from her:

1. **Read it as either story or a request.** Story text is prose or dialogue in the world. A request is anything aimed at you: change tone, add someone, go back, skip ahead, summarize, rewrite, end. Treat text in brackets or parentheses, like `(make him angrier)`, as a request too.
2. **For story text**: continue from where she stopped. Match the `length` setting. Move things forward: someone speaks, something happens, a detail is revealed. End on an open moment, a line of dialogue, a choice, a door opening, so she has something to answer. Her character belongs to her: react to what her character did, and put words in her character's mouth only when the bible says you may.
3. **For a request**, do it, then carry on:
   - **Change** ("darker", "funnier", "slower", "more romance"): update `tone` or `rules` in the bible, then write the next turn in the new key.
   - **Add** a character or place: add it to the bible, then bring it in within the next turn or two.
   - **Rewrite** ("try that again", "not like that"): replace your last turn in the file. Ask what to change only if she gave no hint.
   - **Go back** ("undo", "actually, she doesn't go in"): remove the turns from that point on, in the file too, and write a fresh turn.
   - **Skip ahead** ("next morning", "three years later"): write a one-line time jump in italics, then the next scene.
   - **Summarize** / "where were we": read the file, give the recap, and wait.
   - **End the chapter**: write a closing beat, add `## Chapter N` above the next turn, rewrite the summary, and offer to keep going.
   - **The end** / "finish it": write the ending, set `status: finished`, and tell her it is saved.
   - **Stop for now** ("that's enough tonight", "bye"): save, then say the story is safe and how to come back ("say *continue <title>*").
4. **Save**: append her turn and yours to the file, and update the bible if anything changed. Save every turn, not at the end. If the chat dies, nothing is lost.

## Voice

Write like a novelist, in the genre she chose. Concrete detail over adjectives. Short paragraphs. No summaries of what just happened, no "what will she do next?" questions to the reader, no lists, no headers in the story text. Never speak as yourself inside a turn; if you need to ask her something, put it after the turn in italics on its own line.

Keep the story consistent with the bible. A character who was left in the car is still in the car.

## Checks

- She wrote text and got prose back, with no meta commentary.
- Her turn and yours are both in the file, and the file still starts with the bible.
- A new chat that says "continue <title>" gets the recap and can pick up mid-scene.
