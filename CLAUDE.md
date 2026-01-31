# Little Wonders - Claude Code Instructions

Dana serves on the Little Wonders board as **Technology Chair**.

## Schedule Editor

Update the 6-column schedule table (Time + Monday–Friday) without changing visual layout. Only modify cell content and attributes, then return a single complete HTML snippet ready to paste.

### Rules

1. Keep **one `<tr>` per time slot** (visual layout unchanged)
2. Toggle individual classes by setting `data-visible="true|false"` on the `<td>` (not on `<tr>`)
3. **Tues/Thurs Twos (2-Day Offering)** appears in both Tue and Thu cells of the same row
4. Keep times on one line (`white-space: nowrap` in CSS)
5. **New Class** label: `<span class="label newclass">New Class</span>`
6. **Waitlist** label: `<span class="label waitlist">Waitlist</span>`
7. **Teacher edits**: change only text inside `<span class="teacher ...">Teacher NAME</span>`
8. **Dates edits**: change only text inside `<span class="dates">…</span>`
9. Never remove required empty cells; maintain exactly 6 cells per row
10. Validate every `<tr>` has 6 `<td>`/`<th>` in order; fix malformed rows silently

### When Given Changes

1. Parse intent (hide/show class, add New Class, set/remove Waitlist, change Teacher/Date/Time)
2. Apply edits to `schedule.html`
3. Re-validate column count and close all tags
4. Output the updated HTML or update the file directly

### Output Format

- Return only `<style>…</style><table>…</table>` block
- No commentary unless asked
- Don't invent classes - ask one clarifying question if ambiguous
- If a change breaks the 6-cell grid, repair silently (add empty `<td>`s)

## Key Files

- `schedule.html` - Current schedule (edit this)
- `editing-cheatsheet.md` - Quick reference for HTML patterns

## Common Tasks

- **Hide a class**: Set `data-visible="false"` on the `<td>`
- **Show a class**: Set `data-visible="true"` on the `<td>`
- **Add waitlist**: Add `<span class="label waitlist">Waitlist</span>`
- **Remove waitlist**: Remove the waitlist span
- **Update teacher**: Change text in `<span class="teacher ...">Teacher NAME</span>`
- **Update dates**: Change text in `<span class="dates">...</span>`
- **Add new class label**: Add `<span class="label newclass">New Class</span>`

## Color Classes

- `.blue` - Blue background
- `.purple` - Purple background
- `.green` - Green background
- `.orange` - Orange background
- `.monday/.tuesday/.wednesday/.thursday/.friday` - Day tint helpers
