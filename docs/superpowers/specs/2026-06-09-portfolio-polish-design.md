# Portfolio Polish — Design

**Date:** 2026-06-09
**Goal:** Make the portfolio site land with recruiters for job applications. Positioning: ~70% Customer Success leadership, ~30% product/PM ambition, with the AI projects as product evidence.
**Scope decision:** Polish the existing dark slate/teal design. No visual identity change. Resume hosted as a PDF on the site.

## Content changes

### Hero
- Add a static role line under the name: "Senior Enterprise Customer Success Manager · Healthcare SaaS".
- Typed tagline strings rewritten to carry the 70/30 story (CS outcomes first, building/product second).
- Bio rewritten to lead with concrete facts ($750K+ ARR, enterprise healthcare, QBRs) while keeping the casual voice, then bridge to AI building and product thinking.
- Contact email standardized to cameron@thedeesfamily.com (matches resume and chatbot).
- Resume button serves `/resume.pdf` (exported from the Google Doc) instead of a Google Doc edit URL.

### Stats bar
- Keep all four stats including the "∞ Tabs Open at Once" joke (user request).

### What I Bring
- Replace the generic "Stakeholder Alignment" tile with a "Product Thinking" tile (PM bootcamp, structured product feedback, RICE/agile) to carry the 30% product story.
- Strengthen the AI Integration tile with the work-side CS AI adoption initiative.

### Projects
- Rewrite card descriptions as problem → what was built → outcome.
- Add small tech/skill meta tags to each card.

### Posts / Testimonial / Footer
- Posts and testimonial unchanged. Footer gains contact links.

### Chatbot knowledge base (`api/cameron-info.md`)
- Professional summary and FAQs aligned to the 70/30 positioning so the bot and the page never contradict each other.
- Stale duplicate `cameron-info.md` at repo root deleted; `vercel.json` `includeFiles` updated to `api/cameron-info.md` to match what `chat.js` actually reads.

## Design changes
- Bump body text sizes site-wide (bio, cards, tiles from 0.83–0.9rem to 0.9–0.95rem); drop the italic quote styling on the bio.
- Larger h1 on desktop.
- Slightly stronger hero overlay for contrast.
- Fix mobile hero bug: the photo wrapper stays 210px wide while the image shrinks to 140px; size the wrapper in the media query instead.
- `prefers-reduced-motion` support: skip particles, typed effect (static fallback text), scroll reveals, and counters.

## Technical changes
- Compress images: `profile.png` (1.6MB, 1254px) → resized JPEG; `hero-bg.jpg` (497KB) → recompressed. Update references including og:image.
- SEO: add canonical URL and JSON-LD Person schema.
- Add `.gitignore` (`.superpowers/`, `.DS_Store`).

## Out of scope
- Per-project case-study pages.
- Any change to employment dates (resume says Swell CX from April 2021; chatbot KB says April 2023 — flagged to user to reconcile).

## Verification
- Serve locally, check desktop + narrow viewport rendering, reduced-motion behavior, all links, and that the PDF opens.
- Commit but do not push (push auto-deploys via Vercel); user reviews first.
