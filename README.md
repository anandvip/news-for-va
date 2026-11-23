# news-for-va

VA Graphics Dispatch: daily and weekly news editions curated in Kurukshetra by VA Graphics (made with Google Gemini).

Live: https://anandvip.github.io/news-for-va/

## Structure

- `index.html` is the landing page. It shows featured stories from the latest daily and weekly editions, the newest edition's highlights, Daily / Weekly tabs, a date picker, and side lists of every edition grouped by month.
- `daily/YYYY-MM-DD.html` holds one file per daily edition, named by the date of the issue.
- `weekly/YYYY-MM-DD.html` holds one file per weekly edition, named by the last day the week covers.
- `editions.json` lists every edition (date, type, title, url, headline, summary, featured stories). The landing page reads it.

Each edition page keeps Gemini's design and has a small nav bar at the top with Home, All daily/weekly editions, and Previous / Next edition links.

## Adding a new edition

1. Save the edition file as `daily/YYYY-MM-DD.html` or `weekly/YYYY-MM-DD.html`.
2. Copy the nav bar block (right after `<body>`) from an existing edition into the new file, set its Previous / Next links, and update the Next link on the edition before it.
3. Add an entry at the top of `editions.json`, with 2-3 real headlines and one-line summaries taken from the edition.
4. Paste the same entry into the inline fallback copy near the bottom of `index.html` (`<script type="application/json" id="editions-data">`), so the page also works when opened from disk.

Nothing is overwritten, so links to older editions keep working.
