# TaskMate

A lightweight, shared task manager for two — built as a single-page web app and backed by Supabase.

---

## Features

- **Shared task lists** — tasks are assigned to defined people, with colour-coded cards for each person
- **Add, edit & delete tasks** — full CRUD via a clean bottom-sheet modal
- **Due dates** — set deadlines per task; overdue tasks are flagged with a warning banner and badge
- **Complete tasks** — tap the circle to mark a task done; completed tasks are grouped under a collapsible section
- **Auto-cleanup** — completed tasks older than 14 days are automatically purged
- **Real-time sync** — task list refreshes every 30 seconds; sync status shown via a colour indicator in the header
- **Dark / Light mode** — one-click theme toggle, persisted in `localStorage`
- **Responsive design** — works comfortably on mobile and desktop

---

## Tech Stack

| Layer | Technology |
|-------|-----------|
| Frontend | Vanilla HTML, CSS & JavaScript (single file) |
| Fonts | [Syne](https://fonts.google.com/specimen/Syne) · [Outfit](https://fonts.google.com/specimen/Outfit) via Google Fonts |
| Backend / Database | [Supabase](https://supabase.com) (PostgreSQL + REST API) |
| Hosting | [Netlify](https://netlify.com) |

---

## Getting Started

### Prerequisites

- A [Supabase](https://supabase.com) project with a `tasks` table
- (Optional) A [Netlify](https://netlify.com) account for deployment

### Supabase Table Schema

Create a table called `tasks` with the following columns:

| Column | Type | Notes |
|--------|------|-------|
| `id` | `int8` | Primary key, auto-increment |
| `title` | `text` | Task description |
| `date` | `date` | Due date (nullable) |
| `assignee` | `text` | `lasni` or `hishan` |
| `done` | `bool` | Defaults to `false` |
| `created_at` | `timestamptz` | Defaults to `now()` |

### Configuration

Open `index.html` and update the Supabase credentials near the top of the `<script>` block:

```js
const SUPABASE_URL = 'https://your-project.supabase.co';
const SUPABASE_KEY = 'your-publishable-anon-key';
```

### Running Locally

No build step required — just open `index.html` in a browser:

```bash
git clone https://github.com/dulara-lasni/taskmate.git
cd taskmate
open index.html   # or double-click the file
```

### Deployment

The repo is set up to deploy automatically via Netlify. Connect the repository in your Netlify dashboard and it will publish on every push to `main`.

---

## Project Structure

```
taskmate/
└── index.html   # Entire app — markup, styles & logic in one file
```

---

## License

This project is for personal use by the owner. 
