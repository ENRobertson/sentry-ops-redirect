# sentry-ops.com forwarding page

This repository holds one page. It forwards the bare address sentry-ops.com to the Sentry Operations™ website at https://www.sentry-ops.com.

Why it exists: the website's host can only take the www address while the domain's DNS stays where it is. This page covers the bare address until the domain moves.

## What is here

- index.html: the forwarding page. It sends the browser to the same path on www.sentry-ops.com.
- 404.html: the same page, so any other path on the bare address is forwarded too.
- CNAME: tells GitHub Pages this site answers at sentry-ops.com.
- .nojekyll: tells GitHub Pages to publish the files as they are.

## Rules

- Nothing else belongs here. No company papers, no secrets, no other pages.
- Nothing that collects data. No cookies, analytics, tracking, forms or outside files.
- Changes are pushed only when Elliott Robertson says "push".
