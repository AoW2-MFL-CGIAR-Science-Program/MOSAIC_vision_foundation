# MOSAIC — Vision & Foundations: live document

**It is already live here:**
**https://aow2-mfl-cgiar-science-program.github.io/MOSAIC_vision_foundation/**

- Repo: https://github.com/AoW2-MFL-CGIAR-Science-Program/MOSAIC_vision_foundation
- The Microsoft Form (https://forms.cloud.microsoft/e/wcgeFbHJCM) is embedded in
  Section 13, and the CGIAR logo is embedded in the file, so `index.html` is fully
  self-contained.
- Responses collect in that form's **Responses** tab (export to Excel there). The page
  stores nothing itself.

Share the live link above with leadership and the focal points.

> **Heads-up — the link is public.** Anyone with the URL can view it (no CGIAR login).
> Fine for a vision/validation document; do not put sensitive data here.

---

## How to update the document later

You (account `lizciat`) have admin on the repo. To publish a change:

**Option 1 — command line (from this folder):**

    git add index.html
    git commit -m "Update document"
    git push

The live page refreshes within ~1 minute.

**Option 2 — GitHub website:** open the repo → click `index.html` → pencil icon →
paste the new content / upload → **Commit changes**.

To change the cover status label, edit `var STATUS_LABEL = "For validation";` near the
top of the `<script>` in `index.html` (e.g. to `"Final"`).

---

## Reference: how it was set up (already done)

There were two steps: **(A) embed the response form** and **(B) host on GitHub Pages**.
Both are complete; this section is kept for the record.

---

## A. Embed the Microsoft Form (so people can respond)

The page currently shows a dashed placeholder box in Section 13 that reads
"The Microsoft Form embeds in this spot." Replace it with your real form:

1. **Create the form.** Go to https://forms.office.com (sign in with your CGIAR
   account) → **New Form**. Title it e.g. *MOSAIC — Vision & Foundations: your validation*.
   Add the five asks. For each one, the simplest pattern is two questions:
   - a **Choice** question: *Agree* / *Needs discussion*
   - a **Long answer** text question: *Comment (optional)*

   The five asks are:
   1. **The framing** — connect & give coherence, not a repository that re-hosts everything.
   2. **The user sequence** — CGIAR research community first; partners & governments second.
   3. **The 2026 scope** — delineation, gap analysis, minimum spatial package, 1–2 use cases; no central repository this year.
   4. **The principles** — the seven guiding principles in Section 5 are the right ones.
   5. **Boundaries with other platforms** — the Climate Data Hub / GARDIAN / Digital Twin relationship is correctly drawn.

   (Optionally add a first question for the respondent's **name and centre** so you
   know who said what.)

2. **Get the embed code.** In the form, click **Collect responses** (or **Share**) →
   the **`</>` Embed** option → **Copy**. You'll get an `<iframe ...>` snippet whose
   `src` ends in `&embed=true`.

3. **Paste it into `index.html`.** Open `index.html` in a text editor and find this
   block in Section 13 (search for `RESPONSE FORM`):
   - **Delete** the `<div id="formPlaceholder"> ... </div>` placeholder block.
   - **Uncomment** the `<iframe id="mosaicForm" ...>` that sits just above it (remove
     the `<!--` before it and the `-->` after it) and replace
     `PASTE_YOUR_MICROSOFT_FORM_EMBED_URL_HERE&embed=true` with the `src` value from
     your copied embed code. Keep the trailing `&embed=true`.

   Save. Open `index.html` in a browser to confirm the form appears in Section 13.

> Note: Microsoft Forms only embeds on pages served over **https** (GitHub Pages is
> https, so this works once hosted). When you open the file locally with `file://`,
> the form may show a blank frame — that's expected; it will display once the page is
> live.

---

## B. Host it on GitHub Pages (so it has a shareable link)

All in the browser — no command line needed.

1. Create a free account at **https://github.com** (skip if you have one).
2. Click **+ → New repository**. Name it e.g. `mosaic-vision`, set it to **Public**
   (private repos need a paid plan for Pages), and click **Create repository**.
3. On the new repo page, click **Add file → Upload files**, drag in **`index.html`**,
   then **Commit changes**.
4. Go to **Settings → Pages**. Under *Build and deployment*: Source = **Deploy from a
   branch**, Branch = **main**, folder = **/ (root)**. Click **Save**.
5. Wait about a minute, then refresh the Pages settings page. It will show your live
   address:

       https://<your-username>.github.io/mosaic-vision/

6. Open that link to check it, then share it with leadership and the focal points.

To update the document later, repeat step 3 (upload the new `index.html`, commit) —
the live page refreshes within a minute.

---

## Things worth knowing

- **The link is public.** Anyone with the URL can view the page (the GitHub repo
  being public does not require viewers to have GitHub accounts). This is fine for a
  vision/validation document, but it is **not** behind a CGIAR login. If it must stay
  inside the tenant, host the Word version in SharePoint instead and share that.
- **Responses live in the form, not the page.** All Agree / Needs-discussion answers
  and comments collect in your Microsoft Form's **Responses** tab (export to Excel
  there). The page itself stores nothing.
- **Changing the status label.** Near the top of the `<script>` in `index.html` there
  is `var STATUS_LABEL = "For validation";`. Change it to `"Final"` (etc.) and the
  cover pill updates.
- **PDF.** Use the browser's *Print → Save as PDF*. The nav rail and progress bar drop
  away automatically; the embedded form prints as a static panel (it is not fillable
  in a PDF — the form link is how people respond).
