# training
Open online resource for training materials

## Layout

- `quarto/` — website source (`index.qmd`, `about.qmd`) and the training
  material under `quarto/material/training_material/<year>-<city>/`.
- `docs/` — the rendered site. GitHub Pages publishes from this folder, so it
  has to be committed.
- `quarto/_site/` — local build output. Git-ignored; do not commit it.

Training material must live in `quarto/material/`, not in `docs/material/`.
Quarto deletes files it does not know about from its output directory, so a
copy kept only under `docs/` would be destroyed on the next render.

## Building the site

```
quarto render quarto
cp -r quarto/_site/* docs/
```

If files were renamed or removed, delete `docs/material/` first so that stale
copies do not linger:

```
rm -rf docs/material
quarto render quarto
cp -r quarto/_site/* docs/
```

Then commit and push to main (or preferably, open a PR).

Could be automated with Github Actions later.
