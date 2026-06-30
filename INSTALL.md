# Setup — Fat Tail Book

## Step 1: Install Quarto (one time)

Download and run the Windows installer from:
https://quarto.org/docs/download/

Version 1.5+ recommended. Verify: `quarto --version`

## Step 2: Preview locally

```
cd "C:\Users\chouf\Vibe coding\FatTailBook"
quarto preview
```

Opens at http://localhost:4444 with live reload on file save.

## Step 3: Build PDF + HTML

```
quarto render
```

Output goes to `_site/` (HTML) and the root directory (PDF).

## Step 4: Publish to GitHub Pages (one time setup)

1. Create a new GitHub repository named `fat-tail-book` (public)
2. Push this folder to the `main` branch:
   ```
   git init
   git add .
   git commit -m "feat: initial book scaffold"
   git remote add origin https://github.com/shoufnado/fat-tail-book.git
   git push -u origin main
   ```
3. In GitHub repository Settings → Pages → Source: select "GitHub Actions"
4. The workflow in `.github/workflows/publish.yml` runs automatically on every push
5. Book is live at: https://shoufnado.github.io/fat-tail-book

## Step 5: Update the book

Edit any `.qmd` file → commit → push → GitHub Actions rebuilds and deploys automatically.
No manual steps needed after initial setup.

## GitHub Issues for peer engagement

Readers who find errors or want to comment open an issue at:
https://github.com/jmchoufani/fat-tail-book/issues

The `repo-actions: [issue]` line in `_quarto.yml` adds a "Report an issue" link
to every page automatically — no configuration needed.

## Adding a Chicago author-date CSL file (for citations)

Download `chicago-author-date.csl` from:
https://github.com/citation-style-language/styles/blob/master/chicago-author-date.csl

Save it as `FatTailBook/chicago-author-date.csl` — Quarto uses it automatically.
Without it, Quarto falls back to its default citation style (still functional).
