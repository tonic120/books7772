# Books777 Arcade

This folder is ready to publish with GitHub Pages. The `CNAME` file already contains `books777.ra3.us`.

## Site files

| File or folder | What it does |
| --- | --- |
| `index.html` | Main home page for Books777 Arcade. |
| `games.html` | Dedicated games menu with game cards and pictures. |
| `play.html` | Game player page with the hover sidebar menu. |
| `external-play.html` | Player page for games hosted on another website. |
| `games/` | Put your HTML game files here. |
| `images/` | Put game thumbnails or pictures here. |
| `CNAME` | Keeps the custom domain connected to GitHub Pages. |

## Add a new game

1. Put your game file in the `games` folder.
   Example: `games/my-game.html`
2. Put your picture in the `images` folder.
   Example: `images/my-game.png`
3. Open `games.html`.
4. Duplicate one of the `<a class="game-card">` blocks.
5. Change the card link, image, title, tags, and description.

Example card:

```html
<a class="game-card" href="play.html?game=my-game.html&title=My%20Game">
  <img class="game-thumb" src="images/my-game.png" alt="My Game thumbnail">
  <div class="game-body">
    <div class="game-meta">
      <span class="pill">Action</span>
      <span class="pill">HTML</span>
    </div>
    <h2>My Game</h2>
    <p>A short description of the game.</p>
    <span class="game-action">Launch game</span>
  </div>
</a>
```

Use a simple file name for games, like `my-game.html`. The player page accepts game files inside the `games` folder.

## Game sidebar

Game cards should open through `play.html`, like this:

```html
play.html?game=my-game.html&title=My%20Game
```

That loads the game inside the player page. When the mouse moves to the left side of the screen, the sidebar opens with links back to the games menu and home page.

## Load a game hosted somewhere else

If a game is too large for GitHub Pages, host it on another static/game host first. Good options are itch.io, Netlify, Cloudflare Pages, or Vercel.

After the game is live, copy its HTTPS URL. Then add a card in `games.html` that opens `external-play.html`.

Example:

```html
<a class="game-card" href="external-play.html?url=https%3A%2F%2Fyour-game-host.com%2F&title=My%20Hosted%20Game">
  <img class="game-thumb" src="images/my-game.png" alt="My Hosted Game thumbnail">
  <div class="game-body">
    <div class="game-meta">
      <span class="pill">Hosted</span>
      <span class="pill">External</span>
    </div>
    <h2>My Hosted Game</h2>
    <p>This game is hosted somewhere else but loaded inside Books777 Arcade.</p>
    <span class="game-action">Launch hosted game</span>
  </div>
</a>
```

The `url=` part must be URL-encoded. For example:

```text
https://your-game-host.com/
```

becomes:

```text
https%3A%2F%2Fyour-game-host.com%2F
```

If the embedded game shows a blank screen, the other host is blocking iframe embeds. In that case, use the "Open game directly" button or move the game to a host that allows iframe embedding.

## Light and dark mode

The site starts in dark mode with blue accents. Visitors can press the light mode button, and the choice is remembered on their device.

## Publish updates

Upload the contents of this folder to your GitHub repository and commit the changes. GitHub Pages will rebuild the site automatically.

If you add new game or image files later, upload those new files and the edited `games.html`.
