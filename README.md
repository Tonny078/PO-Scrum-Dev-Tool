# Agile Workspace Tools

Two free, single-file workspaces for the people who run agile teams — one for the **Scrum Master**, one for the **Product Owner**.

No install. No account. No server. No tracking. Each tool is a single `.html` file: download it, double-click it, and it works. Your data stays on your own machine.

Built by **Tonny Sluijs**. Free to use for everyone.

---

## The two tools

| File | For | What it does |
|---|---|---|
| **`ScrumMaster-Toolv01.html`** | Scrum Masters | Sprints with burndown and velocity, an impediment register that counts days, ceremony agendas with a timebox timer, a Daily Scrum log, team capacity and health, a living Definition of Done, and a Scrum quick reference |
<img width="1917" height="942" alt="image" src="https://github.com/user-attachments/assets/4334d3a4-acf5-41dc-b241-642bd1b46c66" />

| File | For | What it does |
|---|---|---|
| **`ProductOwner-Toolv01.html`** | Product Owners | Kanban boards, a decision log that keeps the *why*, a quarterly roadmap, a value/effort backlog, goals with key results, retrospectives, notes and a document register |
<img width="1919" height="938" alt="image" src="https://github.com/user-attachments/assets/81baa1e9-bdef-41ce-86e2-f97477acfed6" />


| File | For | What it does |
|---|---|---|
| **`Developer-Toolv01.html`** | Frontend, Backend, Fullstack | Several Kanban boards (one per project), a snippet and command library with one-click copy, a register of services and their ports and URLs, architecture decision records, a tech-debt list, checklists with a git and HTTP reference, notes and links |
<img width="1919" height="944" alt="image" src="https://github.com/user-attachments/assets/6f49b679-0d08-438a-833d-ea94d097f177" />

They are independent. Use one, or all three — each keeps its own data and they never overwrite each other, even in the same browser or the same folder.

---

## Quick start

1. Go to the green **Code** button above → **Download ZIP**, and unzip it. (Or clone the repo.)
2. Double-click the tool you want. It opens in your browser.
3. A one-time setup asks **where your data should live**. Pick either option — you can switch later in Settings.

That is the whole installation.

> **Tip:** right-click the file → *Open with* → your preferred browser, then pin the tab. Chrome and Edge users can also use *⋮ → Cast, save and share → Install page as app* to give it its own window and taskbar icon.

---

## Where your data is stored

You choose on first run:

**Option A — in this browser** (works everywhere)
Saved instantly to the browser's local storage. Nothing to set up. The catch: it is tied to that one browser profile, and clearing site data deletes it. **Export a backup now and then.**

**Option B — in a folder on your computer** (Chrome or Edge)
Each section becomes its own readable JSON file — `sprints.json`, `impediments.json`, `boards.json`, and so on. Put that folder in OneDrive, Dropbox or a git repo and you have versioned, portable, human-readable data.

Folder storage uses the File System Access API, so it needs Chrome or Edge, and the page must be served over `http://` rather than opened as a `file://` path. If you want it:

```bash
cd path/to/this/folder
python -m http.server
# then open http://localhost:8000/ScrumMaster-Toolv01.html
```

Nothing is ever uploaded anywhere. There is no backend, no analytics and no network request of any kind — you can verify that in your browser's Network tab, or by reading the file.

### Backups

**Settings → Backup copy → Export** downloads the whole workspace as one JSON file. **Import** merges it back by id, updating what it recognises and never deleting what it does not. Safe to run against a workspace that already has data.

---

## The Scrum Master tool

**Overview** puts the Sprint Board first, then everything standing in the team's way.

- **Sprints & Metrics** — a Sprint has a goal, dates and a forecast. The **burndown records itself**: every change snapshots what is left today, so the chart fills in as the Sprint runs (any day can be corrected by hand). **Velocity** is a bar per closed Sprint with an average line; closing a Sprint freezes its number so history cannot drift afterwards. Also cycle time, throughput and available person-days.
- **Impediments** — oldest first, with an age badge that turns amber then red past your threshold. "Nobody is chasing this" is called out in as many words. Raise one in a single click from a blocked card or a standup blocker. Cleared ones stay on the record with how long they took, because the same wall tends to come back.
- **Ceremonies** — the five Scrum events, pre-loaded with the Scrum Guide timeboxes and an agenda you tick off while facilitating. The **timebox timer** runs in the top bar and keeps running while you move around the tool.
- **Daily Scrum log** — pre-fills from your roster, rotates the facilitator automatically, and has a parking lot for the deep-dives. Any blocker becomes a real impediment in one click.
- **Team** — availability percentages, planned absence deducted from Sprint capacity, who is away today, and a mood check drawn as a colour trend per person.
- **Playbook** — your Definition of Done, Definition of Ready and working agreements (starter versions included), plus a Scrum quick reference and 14 facilitation techniques with a line on when to use each.
- **Refinement** — the queue before Planning. Rank it by dragging, size it in points, and check each item against your Definition of Ready. Items show "3/6 ready"; pulling in an unready one asks you to say so out loud.
- **Sprint Board** — story points, blocked cards with a one-click impediment, **WIP limits** that turn red when exceeded, stale-card warnings, and automatic start/finish stamping that feeds cycle time.
- Plus a **Decision Log**, Retrospectives with owned actions, Releases, Notes and Documents.

### Multiple boards, including a private one

Keep as many boards as you like — one per team, plus a private board for your own work. When you create a board you can untick **"Cards here count towards the Sprint"**, and that board's cards stay out of the burndown, the velocity and the cycle time. Your personal to-dos never distort the team's numbers.

### Keyboard shortcuts

| Key | Does |
|---|---|
| `/` | Jump to search |
| `n` | New task |
| `i` | Raise an impediment |
| `s` | Run or continue today's standup |
| `t` | Start a 15-minute timebox |
| `b` | Sprint Board |
| `g` | Overview |
| `?` | Show this list |
| `Esc` | Close a dialog or panel |

---

## The Product Owner tool

- **Taskboard** — Kanban with drag-and-drop, custom columns and colours, priorities, assignees, due dates and tags.
- **Decision Log** — the heart of it. Record the problem, the options you rejected *and why*, who approved it, and the reasoning. Every later edit is added to that record's history, so six months on you can see not just what was decided but how the thinking moved.
- **Roadmap** — milestones grouped by quarter, with countdowns and overdue flags.
- **Backlog** — park ideas with a business value and effort estimate, drag to re-rank, and promote the best ones onto the board.
- **Goals** — objectives with key results; progress is calculated from the ticks, not typed.
- **Retrospectives**, **Notes** with reminder dates, a **Documents** register, and a **Risk monitor**.

---

## The Developer tool

Built for Frontend, Backend and Fullstack developers, and deliberately free of ceremony — no sprints, no burndowns, no standups. Just the things you actually lose time to.

- **Boards** — one per project or repo, switched from a dropdown. Cards carry a work **type** (feature, bug, chore, refactor, spike, docs), an estimate, the **branch name** (copyable in one click — the thing you retype all day) and a link to the **PR or issue**, opened straight from the card. Plus WIP limits that turn red when exceeded, blocked cards with a reason, and stale-card warnings.
- **Snippets** — the code you rewrite from memory every few months: the debounce, the awkward SQL join, the regex that took an hour. Filter by language, one click copies it back out.
- **Commands** — your own cheatsheet, grouped by git / docker / npm / database / deploy. The flags you re-google, one click from the clipboard.
- **Stack** — every service with its local port and its staging and production URLs, plus repo and docs links. The end of "what port does that run on again?". It warns you, in the form, never to put credentials in it.
- **Decisions** — architecture decision records: the problem, what you chose, **what you turned down and why**. Every edit is kept in that record's history. This is the answer to "why on earth is this like this?" two years later.
- **Tech Debt** — the shortcuts you know about, with severity, effort, where they live and **what they cost you**. It turns "the code is a mess" into a list you can negotiate time for. Any item can be pushed onto a board as a refactor card; a blocked card can be logged as debt in one step.
- **Checklists** — your pull request, code review and release checklists (seeded on first run), plus a built-in reference: git rescue commands, HTTP status codes with what they *actually* mean, semver rules and conventional commit types.
- **Flow** — cycle time, work in progress, blocked count and a chart of what you finished per week for the last eight weeks. Measured from real card movement, not self-reported.
- **Focus timer** — a session clock in the top bar that keeps running while you move around the tool.
- Plus **Notes** and **Links**.

Shortcuts: `/` search · `n` new task · `s` new snippet · `c` new command · `d` new decision · `f` focus session · `b` boards · `g` overview · `?` the full list.

---

## Good to know

- **Everything is optional.** Empty sections stay out of your way and explain what they are for when you first open them.
- **Light and dark**, following your system setting or pinned in Settings.
- **The alert bell** collects what actually needs you — whichever tool you are in: blocked and stale cards, aging impediments or tech debt, a Sprint ending with work left, ceremonies due today, decisions left hanging, overdue items and note reminders.
- **Nothing is uploaded, ever.** All three tools work fully offline, including on a plane.
- **Print** — `Ctrl/Cmd + P` gives a clean printout with the navigation stripped out.

## Browser support

| | Browser storage | Folder storage |
|---|---|---|
| Chrome, Edge | ✅ | ✅ (served over `http://`) |
| Firefox, Safari | ✅ | ❌ — use browser storage plus exports |

Any reasonably current browser runs the tools. Folder storage is the only feature that needs Chrome or Edge.

## Running more than one

Each tool has its own storage namespace (`sm.`, `po.` and `dev.`), its own IndexedDB database and its own export file, so they can share a browser and a folder without ever touching each other. A Scrum Master who also writes code can keep the Scrum Master tool and the Developer tool open in two tabs, and neither will notice the other.

## Under the hood

Plain HTML, CSS and JavaScript in one file each — around 4,000 to 5,500 lines including the styling. **Zero dependencies** — no framework, no build step, no `node_modules`, no CDN. Nothing to audit but the file itself, and nothing to break when a package updates. The charts are hand-written SVG and the icons are inline paths.

To change something, open the file in any editor. The script is laid out in numbered sections — utilities, icons, storage, state, render, views, actions — and each screen is one function that returns HTML.

## Contributing

Issues and pull requests are welcome. Please keep the two ground rules that make these tools what they are: **one file per tool**, and **no dependencies**.

## Licence

Free to use, copy, modify and share, for any purpose, personal or commercial — no attribution required and no strings attached.

If you are cloning this to make it your own, the MIT licence is a good fit; add a `LICENSE` file with your own name as the copyright holder.

---

*Built by Tonny Sluijs. If these save you time, that is the whole point.*

---

*Built by Tonny Sluijs. If these save you time, that is the whole point.*
