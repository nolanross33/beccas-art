---
description: Add new artwork image(s) to the gallery and deploy
---

Look in the /images folder for any image files (.png, .jpg, .jpeg) that are NOT yet referenced anywhere in index.html.

For each new image found:
1. Infer or ask what category it fits: "portrait" (pets), "architecture" (buildings), or "other" — match the existing data-category values and filter buttons already in index.html.
2. Insert a new gallery-item block into the gallery grid in index.html, copying the exact same markup structure as the existing gallery items (including the gallery-overlay svg), with clear, descriptive alt text based on the filename and category.
3. Place it before the closing </div> of the gallery grid, right before the About section.

Once all new images are wired in:
1. Run `git add -A`
2. Run `git commit -m "Add new artwork to gallery"` (adjust the message to describe what was actually added)
3. Run `git push`
4. If the push fails with a divergent-branches error, run `git pull --no-rebase` (accept the default merge commit message if an editor opens), then `git push` again.

Report back a short summary of what was added and confirm the push succeeded.
