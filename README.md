# PHOQUS reviewer navigator — GitHub Pages bundle

Unlisted hosting of the interactive navigator. `index.html` carries
`<meta name="robots" content="noindex, nofollow">`, so search engines will not
index it; access is only by the direct link printed in the proposal PDF.

## Publish (one-time)
    gh repo create phoqus-navigator --public --source . --push
    gh api repos/{owner}/phoqus-navigator/pages -X POST -f build_type=legacy -f "source[branch]=main" -f "source[path]=/"
or on github.com: create a public repo `phoqus-navigator`, push these files,
then Settings > Pages > Deploy from branch > main / root.

URL: https://USERNAME.github.io/phoqus-navigator/

## Update the navigator later
    cp PHOQUS_reviewer_navigator.html index.html
    git commit -am "Update navigator" && git push
(Pages redeploys in ~1 min.)

Notes
- Do not add this URL to any public page; it is only in the proposal PDF.
- `robots.txt` has no effect on a project page (it must sit at the domain root),
  so the noindex meta tag inside index.html is what keeps it out of search.
- For extra obscurity, use a repo name with a random suffix (e.g.
  phoqus-navigator-k3f7) — the URL follows the repo name.
