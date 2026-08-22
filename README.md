# books777.ra3.us starter website

This folder is ready to publish with GitHub Pages. The `CNAME` file already contains `books777.ra3.us`.

## 1. Create the repository

1. Sign in to GitHub and choose **New repository**.
2. Name it `books777-site` (or any name you prefer).
3. Set it to **Public** and create it.
4. Choose **Add file → Upload files**.
5. Upload the *contents* of this folder: `index.html`, `CNAME`, `.nojekyll`, and `README.md`.
6. Commit the files to the `main` branch.

## 2. Turn on GitHub Pages

1. Open the repository's **Settings → Pages**.
2. Under **Build and deployment**, choose **Deploy from a branch**.
3. Select `main` and `/(root)`, then choose **Save**.
4. Under **Custom domain**, enter `books777.ra3.us` and save it. If it is already shown because of the `CNAME` file, leave it in place.

## 3. Point FreeDNS at GitHub

In FreeDNS, open **Subdomains** and create or edit this record:

| Field | Value |
| --- | --- |
| Type | `CNAME` |
| Subdomain/Host | `books777` |
| Domain | `ra3.us` |
| Destination | `YOUR-GITHUB-USERNAME.github.io` |

Replace `YOUR-GITHUB-USERNAME` with your exact GitHub username. Do not include `https://`, a slash, or the repository name.

If FreeDNS shows the full hostname in a single field, use `books777.ra3.us`.

## 4. Finish HTTPS

Return to **GitHub → repository Settings → Pages**. Wait for the DNS check to succeed, then enable **Enforce HTTPS**. DNS and the certificate can take time to finish updating.

## Customize the page

Edit `index.html`. Search for `EDIT:` to find the main text and links. The colors are grouped near the top under `:root`.
