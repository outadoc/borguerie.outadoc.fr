# Borguerie Center (static)

Static version of the site, deployed to GitHub Pages by `.github/workflows/pages.yml`.
The original PHP site lives in `../legacy`.

- `public/`: assets copied verbatim (CSS, images, mp3s, player…)
- `templates/`: HTML templates, taken from the legacy `index.php`
- `pubdates.json`: publication date of each mp3 (git does not keep file mtimes, which the PHP version relied on). New mp3s that are missing from it are dated by their commit.

## Build

```sh
python3 static/build.py
python3 -m http.server -d static/_site 8000
```

To add an episode, drop `borg_<N>.mp3` into `public/mp3/` (and optionally add its date to `pubdates.json`).
