# Project Tracker

Plan a project as a Gantt chart: tasks with durations and dates, links for what has to wait for what, and tracking for how much is done.

## Try it

**[Open Project Tracker → petravanta.github.io/project-tracker](https://petravanta.github.io/project-tracker/)**

1. **+ Task** adds a task with a name, an earliest start and a duration. **+ Milestone** adds a single day with no duration, like a launch or a deadline. A new task starts out on its own, linked to nothing, from today (or the project's start if that's later).
2. **Link tasks.** Drag the dot at the end of a bar onto the task that has to wait for it, or tick *Waits for* in the task's editor (with an optional number of days to wait after it). A task that waits for others starts once they have all finished, so moving or lengthening one task moves everything after it.
3. **Place and size them.** Drag a bar to move it to another day, or drag its right end to change how long it takes. A task can't be dragged earlier than the tasks it waits for allow.
4. **Track completion.** Tick the circle next to a task to mark it done, or set its progress in steps of 5%. The bar fills to match, and the summary shows how much of the whole project is done (weighted by duration), how that compares with where the plan says you should be today, and which tasks are overdue.

## What it does

- **Zoom** from days through weeks, months and quarters to years, for projects that run from a few days to many years. Use **−** and **+**, pick a scale from the menu, or **Fit** to see the whole project at once (Ctrl or ⌘ with the scroll wheel, or a trackpad pinch, zooms too). Weekends are shaded when days are wide enough to see, and today is marked.
- **Count days** (in *Settings*, per project): **Every day** (the default) counts weekends too, which suits recovery plans, courses of treatment and anything else that doesn't stop for the weekend. **Weekdays only** counts Monday to Friday, starts tasks on a weekday and shades weekends on the chart. Each task's editor says which one its project uses.
- **Reorder tasks** by dragging the handle at the left of a row, with a mouse or a finger, or focus the handle and use the up and down arrow keys.
- **Groups** (**+ Group**) hold tasks, milestones and other groups. A group's bar spans everything in it and shows its combined progress; ticking a group marks everything in it done. The arrow beside a group's name folds it away, and links to hidden tasks then point at the group's row. To put a task in a group, drag it by its handle onto the group's row (the group lights up) and let go, or to just below the group's row to put it first, pick the group under *In group* in its editor, or focus the handle and press the right arrow key (left takes it back out). Dragging a row to the left as you move it also takes it out of its group. Groups can't be linked themselves: link the tasks inside them.
- **Critical path** highlights the tasks and links that would push the finish date back if they slipped. Every other task shows how many days it could slip.
- **As many projects as you like**, from the picker in the header. Each has its own name, start date and weekend setting.
- Installs on a phone (Chrome: *Install app*; iPhone: *Share → Add to Home Screen*) and opens offline.
- Light and dark themes, the shared **All apps** link and theme switch, and a phone-first layout, as the [shared standards](https://github.com/petravanta/general/blob/main/STANDARDS.md) describe.

It is deliberately simple and single-user: no resources, no costs, no sharing.

## Your data

Nothing is uploaded. Projects are kept in your browser (`localStorage`). **Settings → Export backup** downloads every project as one JSON file, and **Import backup** merges one back in. **Settings → Connect Google Drive** keeps a copy in `Project Tracker data.json` in your own Drive, using the `drive.file` permission so the app only ever sees that one file, and merges it with the browser copy on connect and whenever the app comes back into view. All of this follows the *User data* section of the shared standards. Drive uses the shared OAuth client for `https://petravanta.github.io` (`GOOGLE_CLIENT_ID` in the script).

## Running it

It is a single static file, `index.html`, with no build step and no built-in data. Serve the folder (`python3 -m http.server`) and open it. GitHub Pages serves it from `main`, root folder.
