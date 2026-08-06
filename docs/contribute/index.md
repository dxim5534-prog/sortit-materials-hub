# How to add your materials

Every session in this programme has its own page. Adding your materials means
putting files onto that page.

## The simplest way: just send the files

Send whatever you have to the hub maintainer:

- Slides (PowerPoint or PDF)
- Handouts, factsheets, worksheets
- Any datasets or exercise files
- A sentence or two describing what the session covers

That is enough. The files get added to your page and published the same day.

## What gets published, and what does not

| Published on the site | Kept off the site |
|---|---|
| Slides, factsheets, worksheets | Facilitator guides |
| Participant activity sheets, card packs | Answer keys and quiz answers |
| Practice datasets | Anything with a planned surprise in it |

Facilitator-only material is distributed directly instead, so participants cannot
find it in advance.

## Two things that help a lot

**Send the editable file as well as the PDF.** The PDF is what participants read on a
phone; the Word or PowerPoint source is what lets the material be adapted, corrected or
translated into Tetum later.

**Say what changed.** If you send a revised version, one line about what changed is
enough. Each page shows a version date, and old versions are kept.

## If you would rather do it yourself

The site is a [MkDocs](https://www.mkdocs.org/) project on GitHub. Pages are plain
markdown files under `docs/`, and files live in a `files/` folder beside each page.
Push to `main` and the site rebuilds and publishes itself in about two minutes.
