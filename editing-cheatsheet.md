# Schedule Editing Cheat Sheet

Use this with the Schedule Editor (HTML/CSS) Custom GPT.
It updates a 6-column schedule (Time + Monday–Friday) without changing the visual layout.

## Rules
1. Keep **one `<tr>` per time slot** (do not add or remove rows unless adding a new time).
2. Toggle individual classes by setting **`data-visible="true|false"` on the `<td>`** that contains the class.
3. The **Tues/Thurs Twos (2-Day Offering)** appears in **both Tuesday and Thursday cells** of the same row.
4. Keep **times on one line**; CSS already enforces `white-space: nowrap` on the time column cells.
5. **Teacher edits**: change only the text in `<span class="teacher ...">Teacher NAME</span>`.
6. **Dates edits**: change only the text in `<span class="dates">…</span>`.
7. **New Class** label: `<span class="label newclass">New Class</span>`
8. **Waitlist** label: `<span class="label waitlist">Waitlist</span>` (remove it to clear waitlist).
9. Ensure every row has exactly **6 cells**: Time + Mon + Tue + Wed + Thu + Fri.
10. If a day has no class for a time slot, leave an **empty `<td data-visible="true"></td>`** to preserve the grid.

## Common Snippets
- Hide a class cell:
  ```html
  <td class="blue" data-visible="false">…</td>
  ```
- Show a class cell:
  ```html
  <td class="blue" data-visible="true">…</td>
  ```
- Add "New Class" to an existing class:
  ```html
  <span class="label newclass">New Class</span>
  ```
- Add or remove "Waitlist":
  ```html
  <span class="label waitlist">Waitlist</span>
  ```
- Update teacher:
  ```html
  <span class="teacher tbd">Teacher Jamie</span>
  ```
- Update dates:
  ```html
  <span class="dates">1/15/25 – 5/15/25</span>
  ```

## Notes
- Day tint classes (optional): `.monday .tuesday .wednesday .thursday .friday`
- Class themes (background colors): `.blue .purple .green .orange`
- Labels use `.label` base class with variants: `.newclass .waitlist .virtual`
- Mobile-friendly: the table scrolls horizontally under 800px.
- If a row breaks alignment, check for **missing or extra `<td>`** in that row.