# Daymark · Rating Journal

A standalone, static daily-rating journal designed to publish on **GitHub Pages**. No frameworks, build tools, server, or paid hosting are required.

## Publish using GitHub Pages

1. On GitHub, create a **public** repository (for example `daymark`).
2. Upload the contents of this folder **to the repository root**: `index.html`, `.nojekyll`, `.gitignore`, and `README.md`. If you received a ZIP, **extract it before uploading**; GitHub won't use a ZIP as the website.
3. Commit the files to the `main` branch.
4. Open your repository's **Settings → Pages**.
5. Under **Build and deployment**, choose **Deploy from a branch**, then select `main` and `/(root)`, and save.
6. After deployment, visit `https://YOUR-USERNAME.github.io/REPOSITORY-NAME/` (replace both placeholders).

If your repository is named exactly `YOUR-USERNAME.github.io`, its homepage will instead be `https://YOUR-USERNAME.github.io/`.

## Keep your existing ratings and notes

Your journal data is saved by the browser, using `localStorage`:

- Data key: `daymark-rating-journal-v1` (preserved from the previous release).
- Display preferences key: `daymark-rating-journal-preferences-v2` (preserved).
- Ratings, notes, light/dark mode, and out-of-10/percent formats all continue working.
- **Deploying an updated website does not erase existing data stored at the same published URL in the same browser.**
- **Switching from an old locally opened HTML file or another website address to GitHub Pages does not automatically transfer your entries**, because browsers keep storage separate for different origins. In the old site select **Export backup (.json)**, then on the hosted site select **Import backup (.json)**.
- Import replaces existing entries on the destination site, so export anything important there first.
- GitHub Pages does not sync your journal across devices. Export and import backups to move it, or add an online database/authentication service in a future version.

## Privacy

GitHub Pages serves the **website source** publicly, but it does not receive your notes or ratings from the browser. **Do not upload your personal JSON backup files into your public GitHub repository.** Other people who visit the same URL get an empty, separate journal in their own browser. Clear-site-data/private browsing can erase local journal data; keep periodic backups in a safe location.

## How averages are calculated

- **Month:** average of all days with ratings in that month.
- **Year:** average of monthly averages for months with at least one rated day, with each rated month weighted equally.
- Unrated days and months are excluded.
- Optional personal month and year ratings are separate from calculated averages.

## Updating

Replace `index.html` in the same repository (and keep the same GitHub Pages URL). Existing browser-saved data will stay available because the storage keys are unchanged.

## Files

- `index.html`: entire website, CSS and JavaScript included.
- `.nojekyll`: disables the Jekyll processing step, keeping the site as a plain static website.
- `.gitignore`: discourages accidentally committing backup JSON files when working locally.
- `README.md`: these setup and migration instructions.
