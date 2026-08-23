# Books777 Arcade

This folder is ready to publish with GitHub Pages. The `CNAME` file already contains `books777.ra3.us`.

## Main Files

| File or folder | What it does |
| --- | --- |
| `index.html` | Home page. |
| `games.html` | Games menu. It auto-loads cards from `games-data.json`. |
| `games-data.json` | The editable game database. Add games here. |
| `add-game.html` | Helper page that generates a `games-data.json` entry. |
| `play.html` | Player page for local games inside the `games/` folder. |
| `external-play.html` | Player page for games hosted on another site. |
| `games/` | Put local HTML game files and folders here. |
| `images/` | Put thumbnails, cover images, and screenshots here. |

## Add Games With The Database

Edit `games-data.json`. Each game is one object inside the array.

Local single-file game:

```json
{
  "title": "My Game",
  "description": "A short description.",
  "image": "images/my-game.png",
  "tags": ["Action", "HTML"],
  "type": "local",
  "target": "my-game.html"
}
```

Local folder game:

```json
{
  "title": "HTML5 Game",
  "description": "A game exported as a folder.",
  "image": "images/html5game.png",
  "tags": ["Folder", "HTML5"],
  "type": "local",
  "target": "html5game/index.html"
}
```

Hosted game:

```json
{
  "title": "Hosted Game",
  "description": "A game hosted somewhere else.",
  "image": "images/hosted-game.png",
  "tags": ["Hosted", "External"],
  "type": "external",
  "target": "https://your-game-host.com/"
}
```

The games page updates automatically after you commit the changed `games-data.json`.

## Use The Add Game Helper

Open `add-game.html`, enter the game link and image, then copy the generated database entry.

Paste the entry into `games-data.json` between the square brackets:

```json
[
  {
    "title": "First Game",
    "description": "Already here.",
    "image": "images/first.png",
    "tags": ["Demo"],
    "type": "local",
    "target": "first.html"
  },
  {
    "title": "New Game",
    "description": "Paste new entries like this.",
    "image": "images/new-game.png",
    "tags": ["New"],
    "type": "local",
    "target": "new-game.html"
  }
]
```

Remember to put a comma between entries, but not after the final entry.

## Add A Folder Like `html5game`

GitHub creates folders when files exist inside them.

To upload a folder:

1. Open your repository on GitHub.
2. Choose **Add file -> Upload files**.
3. Drag the whole folder into the upload box.
4. Commit the upload.

For this site, exported game folders should go inside `games/`.

Example:

```text
games/html5game/index.html
games/html5game/data.js
games/html5game/assets/player.png
```

Then use this in `games-data.json`:

```json
"type": "local",
"target": "html5game/index.html"
```

## Hosted Games

For huge games, host the game on Netlify, itch.io, Cloudflare Pages, or Vercel, then add it as:

```json
"type": "external",
"target": "https://your-game-host.com/"
```

If an embedded hosted game shows a blank screen, that host is blocking iframe embeds. The player page includes an "Open game directly" button for that case.

## Publish Updates

Upload the changed files to GitHub and commit them. GitHub Pages will rebuild the site automatically.
