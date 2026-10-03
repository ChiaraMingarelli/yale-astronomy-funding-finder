# Yale Astronomy Funding Finder

Grants, fellowships, observing and computing time, postdoc postings and student programs for the eight research areas of the Yale Department of Astronomy.

- **Live page (updated automatically):** https://claude.ai/artifact/RQiQz6mdBSReK9w6D6SaJg
- **On GitHub Pages:** https://chiaramingarelli.github.io/yale-astronomy-funding-finder/
- **This repository:** a self-contained copy you can read, download or host yourself.

## Use it

`index.html` is a single file with all its data built in. Open it in a browser, or publish it with GitHub Pages (Settings → Pages → Deploy from branch → `main`, folder `/`).

On a self-hosted copy everything works for everyone, including:

- filters by research area, career stage, status, type and deadline window
- a **New** tag on programs added in the last 7 days ("New this week", or search for `new`)
- tick boxes to export only the programs you care about as a calendar file (`.ics`, with reminders 6 and 4 weeks before each deadline) or a CSV
- per-program **Google Calendar**, **Outlook** and **Apple Calendar** links

## Data

`data/programs.json` has 384 programs, each taken from the funder's own page. Main fields: `n` name, `f` funder, `c` type, `s` status (open, rolling, watch, closed), `d` next deadline, `dt` deadline note, `a` award, `e` eligibility and notes, `u` official link, `stages` (ug, gr, pd, fj, tt, ten), `added` date added, `checked` date last checked, `unv` anything that could not be confirmed.

`engine/export_astro.py` builds the page's data from the shared catalog (rows tagged `ast`); `engine/astro_classify.py` assigns the eight research areas. `engine/export_mod.js` is the export and calendar-link code inlined in the page.

This copy is rebuilt from the shared catalog and pushed here automatically every day at about 1 pm Eastern. The catalog is rechecked every Monday, new postings are added on the other days of the week, and the tips are kept current daily. Deadlines move, so check the funder's page before you commit to a date.

## License

The code (the scripts in the page and in `engine/`) is released under the [MIT License](LICENSE). The catalog (`data/programs.json`), the data embedded in the page and the page text are released under [CC BY 4.0](LICENSE-DATA), so you can reuse them with credit to Chiara Mingarelli. Program details come from each funder's own page; check there before relying on a date.
