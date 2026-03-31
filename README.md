# East Lake Softball Boosters

Website for East Lake High School Softball Boosters, hosted on GitHub Pages.

## How to Update the Site

All site content is managed through **`data.json`**. Edit that file and push to GitHub — the site updates automatically.

### Updates

The `updates` array contains announcements shown at the top of the page. Each item has a `text` field that supports HTML.

```json
{
  "text": "Plain text or <strong>bold</strong> with <a href=\"https://example.com\">links</a>"
}
```

- **Add an update** — add a new object to the array
- **Remove an update** — delete the object from the array

### Links

The `links` array populates the Links section. Each item has a `url` and `label`.

```json
{
  "url": "https://example.com",
  "label": "Example Link"
}
```

For local files (like PDFs), use a relative path:

```json
{
  "url": "files/sponsorship.pdf",
  "label": "2026 Sponsorship Details"
}
```

- **Add a link** — add a new object to the array
- **Remove a link** — delete the object from the array
- **Reorder links** — change the order of objects in the array

### Schedule

The `schedule` array populates the game schedule table. Each item has `date`, `time`, `event`, and `location`.

```json
{ "date": "March 31", "time": "7:00 PM", "event": "Clearwater High School", "location": "East Lake High School" }
```

- Games with `location` set to `"East Lake High School"` automatically get a 🏠 icon and bold location
- Games where `event` contains `"High School"` or `"Preparatory"` automatically link to MaxPreps
- Today's game is highlighted in yellow
- Day of the week is appended automatically

## Local Development

To preview the site locally:

```bash
python3 -m http.server 8080
```

Then open http://localhost:8080 in your browser. Opening `index.html` directly as a file will not work because the browser blocks `fetch()` on `file://` URLs.
