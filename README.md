# Little Wonders

Technology Chair resources for Little Wonders board.

## Files

| File | Purpose |
|------|---------|
| `index.html` | Class schedule (auto-deploys to GitHub Pages) |
| `editing-cheatsheet.md` | Quick reference for HTML patterns |
| `CLAUDE.md` | Claude Code instructions for schedule editing |

## Usage

Open this folder in Claude Code to edit the schedule:

```bash
cd ~/little-wonders
claude
```

Then ask Claude to make schedule changes like:
- "Hide the Monday Young Ones class"
- "Add waitlist to Wed Ones"
- "Change Teacher Lisa to Teacher Sarah"
- "Update Fri Ones dates to 1/15/25 - 5/15/25"

Claude will update `index.html`. Then push to deploy:

```bash
git add index.html && git commit -m "Update schedule" && git push
```

## Deployment

- **Live URL:** https://danajc.github.io/little-wonders/
- **Squarespace:** Embedded via iframe
- Push to main → auto-deploys (no copy/paste needed)
