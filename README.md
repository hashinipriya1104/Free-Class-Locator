# Free Class Locator

Free Class Locator helps students find available classrooms between lectures using the supplied 10 SRM class timetables.

## Features

- Floor-by-floor room availability grid
- Free, occupied, and tight-window room states
- Day and start-time selection
- Duration filter from 1–4 hours
- Floor filter
- AC-only filter
- Team-size and room-capacity matching
- Natural-language room search
- Optional Gemini-assisted search intent parsing
- Light and dark themes
- Responsive mobile layout

## Example searches

```text
I need an AC room on the ground floor for my team for the next 2 hours
```

```text
Quiet room for 8 students
```

```text
Any free room for 1 hour
```

The local parser understands floor names, AC requirements, team size, and duration. If a Gemini key has already been saved by the Classline dashboard, the page can use Gemini 2.5 Flash to refine the search intent.

## Run locally

The page has no build step or dependencies.

```bash
python3 -m http.server 4173
```

Open:

```text
http://localhost:4173/free-class-locator.html
```

## GitHub Pages

1. Create or open a GitHub repository.
2. Upload `free-class-locator.html` and `readme_free.md` to the repository root.
3. Open **Settings → Pages**.
4. Select **Deploy from a branch**.
5. Choose the `main` branch and the `/root` folder.
6. Save the Pages deployment.

## Gemini API key

The page works without Gemini using its local search parser. If Gemini is enabled, the key is read from the browser's local storage and is not hard-coded into the HTML file.

For a public GitHub Pages website:

- Restrict the Gemini API key by HTTP referrer.
- Limit the key to the Gemini API.
- Never commit a live API key to GitHub.
- Rotate a key if it has been exposed publicly.

## Data assumptions

- Room names and class sections are based on the supplied SRM timetable PDFs.
- Monday through Friday are treated as teaching days.
- The default demo state is Monday at 13:30.
- Room occupancy is represented using the timetable venues and scheduled blocks from the supplied sections.
- A room is available only when it remains free for the complete requested duration.

## File

| File | Purpose |
| --- | --- |
| `free-class-locator.html` | Standalone GitHub Pages room locator |
| `readme_free.md` | Documentation for the room locator |
