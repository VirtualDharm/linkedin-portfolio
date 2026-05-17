# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

A single-file creative outreach / portfolio page (`index.html`) built by Aman Jaiswal — a multi-screen interactive pitch targeting the founders of OFF/BEAT (Offbeat Studios). The site is deployed at `offbeatkartakyahai.in`.

## No Build Tooling

There is no build system, package manager, or framework. Everything lives in `index.html` — HTML structure, embedded `<style>`, and inline `<script>`. To preview: open `index.html` directly in a browser, or run a local server:

```bash
python3 -m http.server 8080
```

## Architecture

The page is a multi-screen SPA implemented with vanilla JS:

- **Screens** — `<div class="screen">` elements, only one is `.active` at a time (hidden via `display: none`)
- **Navigation** — `goTo(id)` removes `.active` from all screens and applies it to the target; `id` is a number (`1`–`4`) or the string `'final'`
- **Pitch reveal** — `revealPitch()` shows `#pitch` inside `#screen-final` and hides the trigger button

## Design Tokens (CSS Variables)

```
--black: #0d0d0d    background
--white: #ffffff
--muted: #888888    secondary text
--border: #2a2a2a
--pink:  #ff2d78    accent / CTA
--label: #666666    monospace labels
```

Fonts (Google Fonts): `Anton` (display/headings), `DM Sans` (body), `DM Mono` (labels, metadata).

## Screens

| ID | Content |
|----|---------|
| `screen-0` | Landing — "OFF/BEAT karta kya hai?" |
| `screen-1` | Theory 1: Culture company |
| `screen-2` | Theory 2: AI-native brand builder |
| `screen-3` | Theory 3: Culture-as-infrastructure |
| `screen-4` | Theory 4: GTM challenge |
| `screen-final` | Pitch reveal with two CTAs (LinkedIn / domain purchase) |
