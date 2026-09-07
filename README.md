# Story partner

A Claude skill for writing a story together, turn by turn. You write a bit, Claude writes a bit, and the story keeps going for as long as you like. Each story is saved to a file, so you can close the chat and pick it up again next week.

## Install

**Claude desktop app or Claude Code:** copy the `story-partner` folder into `~/.claude/skills/` (make the folder if it is not there).

```bash
mkdir -p ~/.claude/skills
cp -r story-partner ~/.claude/skills/
```

**claude.ai (web):** go to Settings, Capabilities, Skills, and upload a zip of the `story-partner` folder.

**Phone (Claude app):** skills are uploaded from a computer, then work everywhere. If you would rather skip that, make a Project instead: in the Claude app, New Project, name it "Story", and paste the text of `story-partner/SKILL.md` (everything below the `---` header) into the project instructions. Every chat in that project is a story.

On the phone there is no file to save to, so **the chat is the save**. Keep one chat per story and reopen it to continue. To move a story to a new chat, say "print the story" and paste the result into the new one.

## Use

Start a new chat and say one of:

- `/story`
- "let's write a story"
- "continue The Lighthouse" (or whatever you called it)

Then just write. Things you can say at any time:

- "make it darker" / "more funny" / "slow down"
- "add a rival named Cass"
- "try that again"
- "undo, she doesn't open the door"
- "skip to the next morning"
- "where were we?"
- "end the chapter"
- "the end"
- "that's enough for tonight"

Stories are saved in `~/Stories/`, one Markdown file each. You can open and edit them yourself.
