# Story partner

A Claude skill for writing a story together, turn by turn. You write a bit, Claude writes a bit, and the story keeps going for as long as you like. Each story is saved to a file, so you can close the chat and pick it up again next week.

Status: working. One skill file, no code, no dependencies.

## What it does

- Takes turns with you: you write story text, Claude continues from where you stopped and ends on a moment you can answer.
- Keeps a short "bible" for each story (title, genre, tone, who writes which character, turn length, rules, characters, setting, open threads, summary so far) and reads it before every turn.
- Saves every turn to `~/Stories/<slug>.md`, so nothing is lost if a chat ends.
- Lists your active stories when you start, and opens a story by name ("continue The Lighthouse").
- Understands requests mid-story: change the tone, add a character, rewrite a turn, undo, skip ahead, end a chapter, finish.
- Works without file access (phone, web) by treating the chat itself as the save.

## Install

**Claude desktop app or Claude Code:** copy the `story-partner` folder into `~/.claude/skills/` (make the folder if it is not there).

```bash
git clone https://github.com/chrisbrown042/story.git
mkdir -p ~/.claude/skills
cp -r story/story-partner ~/.claude/skills/
```

Start a new session after copying so Claude picks the skill up.

**claude.ai (web):** go to Settings, Capabilities, Skills, and upload a zip of the `story-partner` folder.

```bash
cd story && zip -r story-partner.zip story-partner
```

**Phone (Claude app):** skills are uploaded from a computer, then work everywhere. If you would rather skip that, make a Project instead: in the Claude app, New Project, name it "Story", and paste the text of [`project-instructions.md`](project-instructions.md) into the project instructions. Every chat in that project is a story.

On the phone there is no file to save to, so **the chat is the save**. Keep one chat per story and reopen it to continue. To move a story to a new chat, say "print the story" and paste the result into the new one.

## Use

Start a new chat and say one of:

- `/story`
- "let's write a story"
- "continue The Lighthouse" (or whatever you called it)

For a new story Claude asks one question (genre, and a character or place you want). Say "surprise me" to pick from three story seeds. Then just write. Things you can say at any time:

- "make it darker" / "more funny" / "slow down"
- "add a rival named Cass"
- "try that again"
- "undo, she doesn't open the door"
- "skip to the next morning"
- "where were we?"
- "end the chapter"
- "the end"
- "that's enough for tonight"
- "print the story" (outputs the bible and full text in one block)

Text in brackets, like `(make him angrier)`, is read as a request, not story.

Stories are saved in `~/Stories/`, one Markdown file each. You can open and edit them yourself.

## How it works

There is no code. The skill is a set of instructions Claude follows. Each story file starts with the bible, then a `---` line, then the story text in order.

| File | What it holds |
|---|---|
| `story-partner/SKILL.md` | The skill: triggers, story file format, turn rules, voice rules |
| `project-instructions.md` | A paste-ready version for a Claude Project, for when skills are not available (chat is the save) |
| `LICENSE` | MIT License |

## Data

Nothing is stored in this repo. Your stories live on your own machine in `~/Stories/`, or in the chat itself on phone and web.

## License

MIT. See [`LICENSE`](LICENSE).
