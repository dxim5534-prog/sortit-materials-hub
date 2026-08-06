# Maintaining this site

*For whoever runs the hub. Not published - this file stays in the repository.*

## Can a non-developer change the topics and structure?

**Yes - through GitHub in a web browser, with no software installed and no command
line.** Everything below is done by clicking Edit on a file, changing text, and
clicking Commit. The site rebuilds and republishes itself in about two minutes.

The one thing that needs care is `mkdocs.yml`, because YAML is fussy about
indentation. Everything else is plain text.

Honest limit: this is **file editing, not an admin screen**. It is teachable in about
twenty minutes, but it is not the same as ticking a box. When the platform's Phase 1
arrives, sessions and materials move into a database with proper admin screens
(the `module`, `session` and `material` tables already exist in the schema) and this
file becomes history.

---

## The four things you will actually need to do

### 1. Add materials to an existing session

1. Go to the repository on github.com
2. Navigate to `docs/m3/<topic>/files/`
3. **Add file → Upload files** → drag the PDF and the editable source in → Commit
4. Open `docs/m3/<topic>/index.md`, click the pencil icon, add a row to the table:
   ```
   | Factsheet 3 - The Denominator Rule | [PDF](files/FS3.pdf) · [Word](files/FS3.docx) |
   ```
5. Commit. Done - live in ~2 minutes.

### 2. Rename a session

Two places, both text edits:

- The heading at the top of `docs/m3/<topic>/index.md`
- The label in `mkdocs.yml` under `nav:` - change only the text before the colon:
  ```yaml
  - Introduction to data analysis: m3/data-analysis-intro/index.md
    ^^^^^^^^^^^^^^^^^^^^^^^^^^^^ change this
  ```

**Do not change the folder name.** The folder is the web address. Renaming it breaks
every link already shared in WhatsApp. The displayed title and the address are
deliberately independent - so a session can be renamed freely.

### 3. Add a whole new session

1. In `docs/m3/`, create a folder with a short lowercase name, no spaces, describing
   the *topic* - not the lecture number (`sampling-methods`, not `lecture-11`).
   Lecture numbers change between cohorts; topics do not.
2. Inside it create `index.md` with a heading and a sentence.
3. Add one line to `mkdocs.yml` under the right day, matching the surrounding
   indentation exactly.

### 4. Set up a new cohort

Copy `docs/cohorts/2026/index.md` to `docs/cohorts/2027/index.md`, edit the times and
sessions, and add it to `nav:`. **Do not touch the topic pages** - they are shared by
every cohort. That separation is the whole point: the schedule changes yearly, the
materials keep their address forever.

---

## Rules that keep the site working

| Rule | Why |
|---|---|
| Folder names are permanent | The folder is the URL; shared links depend on it |
| Slugs describe the topic, never the session number | Numbering shifts between cohorts |
| Never delete a page | Empty it and point forward instead |
| Facilitator answer keys never go in `docs/` | Anything in `docs/` is public |
| New file version replaces the old at the same path | Old links keep working |

## If a change breaks the build

The site simply does not update - the old version stays live, so a mistake is never
visible to participants. Check the **Actions** tab on GitHub for the red run and read
the error. Almost always it is indentation in `mkdocs.yml`.

To undo: open the file's **History**, find the last good version, and revert.

## Running it locally (optional)

```bash
pip install -r requirements.txt
mkdocs serve      # then open http://127.0.0.1:8000
```

Edits appear instantly in the browser. Useful for bigger changes; unnecessary for
adding a file.
