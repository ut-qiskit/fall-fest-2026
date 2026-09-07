# Qiskit Fall Fest 2026 at UT Austin

Event site for Qiskit Fall Fest 2026 at The University of Texas at Austin, hosted by the
IEEE Nanotechnology Council student chapter and co-hosted with the Texas Quantum
Institute. November 16–20, 2026. Poster session Monday, Qiskit challenge running
online all week, IBM Quantum talk and results Friday.

Single static page. No build step, no dependencies.

---

## Status

Live at **https://ut-qiskit.github.io/fall-fest-2026/**

The registration and poster abstract forms are wired in. Still to fill in as you confirm
them: the speaker's name and whether the Friday talk is streamed, and the room for the
Monday poster session (currently "room announced to registrants").

## Publishing on GitHub Pages

```bash
git init
git add .
git commit -m "Qiskit Fall Fest 2026 site"
git branch -M main
git remote add origin https://github.com/<org-or-user>/<repo>.git
git push -u origin main
```

Then in the repo: **Settings → Pages → Source: Deploy from a branch → `main` / `/ (root)` → Save.**

The site goes live at `https://<org-or-user>.github.io/<repo>/` within a minute or two.
Use that URL on the IBM form.

**Publish under the org, not your personal account.** If the IEEE chapter has a GitHub
org, create the repo there so the site outlives your term as organizer. If the chapter
already owns a domain, add a `CNAME` file containing just the hostname and point a DNS
`CNAME` record at `<org>.github.io`.

## Editing the live site without the terminal

Go to the file on github.com, click the pencil icon, edit, and click Commit changes.
GitHub redeploys within a minute. Good for fixing a typo from a phone.

`.nojekyll` is included so GitHub serves the files as-is rather than running them
through Jekyll.

---

## Files

```
index.html      the whole site: HTML, CSS, and one small script
assets/
  qiskit-*.svg          Qiskit pictogram, official kit
  ibm-quantum*.png      IBM Quantum logotype, official kit
  ieee-nano.png         IEEE Nanotechnology Council lockup
  tqi.png               Texas Quantum Institute lockup, for light backgrounds
  tqi-reversed.png      same lockup in white, transparent, for dark backgrounds
  favicon.png
.nojekyll
```

## Editing

Everything lives in `index.html`. The sections are marked with comment banners
(`HERO`, `THE WEEK`, `TRACKS`, `CTA`, `PARTNERS`, `FAQ`). Colors and spacing are CSS
custom properties in the `:root` block at the top. Change `--purple` or `--orange`
there and it updates everywhere.

**Once IBM confirms the speaker**, two things change. Add their name, photo, title, and
a two-sentence bio as a new block between the week section and the tracks section. Then
replace the "Speaker and format confirmed closer to the date" line in the talk card under
`<!-- TRACKS -->`, and the answer to "Can I take part remotely?" in the FAQ, with whether
the talk is in person or streamed.

**Once rooms are booked**, replace "room announced to registrants" in the details table
with the actual building and room.

## Notes on the logos

`assets/` contains files from IBM's official Qiskit and IBM Quantum brand kits. Keep the
clear space around them, do not recolor them, and do not put the IBM Quantum logotype on
a background that reduces contrast. Reversed white versions of the IBM Quantum and Texas
Quantum Institute lockups are included for use on dark backgrounds if you add any, and
are also handy for slides and printed posters.

Qiskit and IBM Quantum are trademarks of IBM. This is a student-organized event and is
not an official IBM event. The footer says so, which is what IBM asks host sites to do.
