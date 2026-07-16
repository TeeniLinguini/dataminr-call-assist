# Dataminr Call Assist

A single-page call prep tool for Dataminr SDRs and AEs. Pick the industry, pick the role on the call, get the value proposition and case studies back in seconds.

See it in action: https://teenilinguini.github.io/dataminr-call-assist/

## What it does

Two clicks and a rep has what they need before a call or email:

- **Industry** — News, Public Sector & Defense, or Corporate Strategy & Security
- **Role** — three tiers per industry, grouped by what that person actually cares about, not by job title alone
- **Output** — an opening line (three variations to cycle through), a 10 second value prop, a 30 second value prop, and linked case studies

The value props follow a persona / peers / how they use it / how they benefit structure, then assemble into a single sentence a rep can say in their own words. It's a reference, not a script.

## Structure

Everything lives in one file, `index.html`. No build step, no dependencies beyond Google Fonts.

- `DATA` (in the `<script>` block) holds all copy: one object per industry, each with three role tiers, three opening lines per tier, both value prop versions, and a case studies array with real links.
- Everything else is rendering. Selecting an industry or role just re-reads `DATA` and rewrites the results panel.

## Editing content

To update or add copy, find the relevant tier inside `DATA` and edit the fields directly:

```js
{
  id: "practitioner",
  title: "Breaking News & Social Editor",
  sub: "Desk / Practitioner",
  persona: "breaking news and social editors",
  peers: "Sky News, the Daily Mail",
  openers: [ "...", "...", "..." ],
  ten: { use: "...", benefit: "..." },
  thirty: { use: "...", benefit: "..." }
}
```

To add or swap a case study, edit the `caseStudies` array for that industry:

```js
{ name: "Company Name", line: "One line outcome.", url: "https://..." }
```

No other file needs to change.

## Deploying to GitHub Pages

1. Push this repo to GitHub.
2. In the repo, go to **Settings → Pages**.
3. Under **Build and deployment**, set **Source** to `Deploy from a branch`.
4. Set **Branch** to `main` (or whichever branch holds this code) and folder to `/ (root)`.
5. Save. GitHub will publish at `https://<username>.github.io/<repo-name>/`.

Pages usually takes a minute or two to go live after the first push.

## Notes

- Case study links point to live pages on dataminr.com. If Dataminr updates or retires a case study, the link may need to be swapped.
- Fonts (Space Grotesk, Inter, IBM Plex Mono) load from Google Fonts over HTTPS. No local font files needed.
- Built as an internal sales reference. Not affiliated with or hosted by Dataminr.
# dataminr-call-assist
