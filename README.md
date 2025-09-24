# Hornedo Middle School Hub

This repository serves as a simple forwarder to the Hornedo Middle School Google Sites pages.

## Purpose

This repository provides redirects to different Hornedo Middle School sites:

- Main site: https://sites.google.com/episd.org/hornedohubjr/home
- Teachers site: `/teachers` → https://sites.google.com/episd.org/hornedotornados/home

## Deployment

This site is configured to be deployed via GitHub Pages. The main site redirect is handled by JavaScript in `index.html`.

### Cloudflare Redirect Rules

The teachers site redirect is handled by a Cloudflare redirect rule with the following conditions:

```
(http.request.full_uri wildcard r"https://*.hornedohub.com/teachers") or
(http.request.full_uri wildcard r"http://*.hornedohub.com/teachers") or
(http.request.full_uri wildcard r"http*://teacher*.hornedohub.com/*")
```

This rule performs a 301 redirect to `https://sites.google.com/episd.org/hornedotornados/home`.