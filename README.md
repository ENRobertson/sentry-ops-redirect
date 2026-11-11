# sentry-ops.com forwarding page

This repository holds one page. It forwards the bare address sentry-ops.com to the Sentry Operations™ website at https://www.sentry-ops.com.

Why it exists: the website's host can only take the www address while the domain's DNS stays where it is. This page covers the bare address until the domain moves.

## What is here

- index.html: the forwarding page. It sends the browser to the same path on www.sentry-ops.com.
  Its first lines carry a content policy (a Content-Security-Policy meta line). The policy lets the page run its one script and use its one style block, and nothing else. Each is named by its SHA-256 hash.
- 404.html: the same page, so any other path on the bare address is forwarded too.
- CNAME: tells GitHub Pages this site answers at sentry-ops.com.
- .nojekyll: tells GitHub Pages to publish the files as they are.

## If the script or the style block changes

The hashes in the content policy must change with them, in index.html and 404.html alike. A wrong hash blocks the script, and the page then falls back to forwarding every path to the home page.

To get a hash, put the exact text between the tags (script or style, line breaks included) in a file and run: `openssl dgst -sha256 -binary FILE | openssl base64`. The policy takes it as `'sha256-...'`.

GitHub Pages can't send response headers, so this page can't carry the main site's full set (no HSTS, no nosniff, no frame rule). The policy in the page is the part that can be done here. The full set comes when the domain moves and the bare address sits on the main host.

## Rules

- Nothing else belongs here. No company papers, no secrets, no other pages.
- Nothing that collects data. No cookies, analytics, tracking, forms or outside files.
- Changes are pushed only when Elliott Robertson says "push".
