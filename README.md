# X Mobile Social Simulator

A single-page, static X-style social media simulator.

The app lives in `outputs/index.html` and stores all user-created data in the browser's `localStorage`.

## Local Preview

From this folder:

```bash
python3 -m http.server 8765 -d outputs
```

Then open:

```text
http://localhost:8765
```

## Project Structure

```text
outputs/
  index.html
  assets/
    *.png
index.html
vercel.json
README.md
.gitignore
```

The root `index.html` redirects to `outputs/index.html`, so GitHub Pages and Vercel can open the app from the project root.

## Upload to GitHub

If Git is installed:

```bash
git init
git add .
git commit -m "Initial X simulator"
git branch -M main
git remote add origin https://github.com/liushuoxi123-wq/L.git
git push -u origin main
```

If `git` is not available on your Mac, install Apple's Command Line Tools first:

```bash
xcode-select --install
```

Then run the Git commands above.

You can also upload manually on GitHub:

1. Create a new repository on GitHub.
2. Choose **Add file** > **Upload files**.
3. Upload this whole folder's contents, including `outputs/`, `.gitignore`, `README.md`, `index.html`, and `vercel.json`.
4. Commit the upload.

## Deploy on Vercel

1. Go to [vercel.com](https://vercel.com).
2. Sign in with GitHub.
3. Click **Add New Project**.
4. Import your GitHub repository.
5. Framework preset: **Other**.
6. Build command: leave empty.
7. Output directory: leave empty.
8. Click **Deploy**.

Vercel will serve the root `index.html`, which redirects to the app in `outputs/index.html`.

## Data Persistence

The simulator saves edits in browser `localStorage`. This means:

- Refreshing keeps your data in the same browser.
- Opening the site on another device starts with the default fake data.
- To share edited data across devices later, add an export/import feature or a backend.
