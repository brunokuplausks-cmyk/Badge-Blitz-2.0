# Badge Blitz - Football Badge Quiz

Badge Blitz is a browser-based football badge identification game. Identify club and national team badges by choosing the correct name from four options before the 60-second timer runs out.

## Features

- 60-second timed rounds with four answer choices per badge
- Club, national team, and mixed quiz modes
- League filter for club questions
- Score, correct-answer streak, and best score for the current page session
- Mobile-friendly layout and keyboard shortcuts (`1` through `4`)
- 324 PNG badge images in the `badges/` directory

## Repository structure

```text
badge-blitz/
├── index.html       # Complete application: HTML, CSS, JavaScript, and badge mappings
├── README.md        # This file
└── badges/          # PNG badge images referenced by index.html
    └── *.png
```

## Run locally

No build step, package manager, or backend is required.

1. Download or clone the repository.
2. Keep `index.html` and the `badges/` folder in the same parent directory.
3. Open `index.html` in a modern browser.

If your browser restricts local files, serve the repository directory locally:

```bash
python -m http.server 8000
```

Then open `http://localhost:8000`.

## How to play

1. Choose a quiz mode and, for club games, optionally choose a league.
2. Click **Start game**.
3. Select one of four team names for each badge (or press `1`–`4`).
4. Score one point per correct answer. Try to beat your session best before time expires.
5. Use **Reset round** to start over or **Play again** after the final score screen.

## Deploy on GitHub Pages

1. Push `index.html`, `README.md`, and the entire `badges/` folder to your GitHub repository.
2. Open **Settings > Pages** in GitHub.
3. Under **Build and deployment**, choose **Deploy from a branch**, select your publishing branch and the `/ (root)` folder, then save.
4. Once GitHub Pages publishes, open the URL displayed in Pages settings.

All badge paths are relative (`badges/filename.png`), so the site works when hosted from a repository subpath as well as at the domain root.

## Add or replace badges

Badge images are referenced in the `badgeImages` mapping inside `index.html`. To add a new team, add its PNG file under `badges/`, define the team in the relevant JavaScript team list, and add the matching name-to-image entry in `badgeImages`. Keep spelling and capitalization of the team name consistent across both entries.

## Notes

- This is a static frontend-only game. No accounts or server-side score storage are included.
- The best score is kept in memory for the current page session; refreshing the page resets it.
- Badge artwork may be subject to third-party trademark and copyright rights. Check usage permissions before public or commercial distribution.
