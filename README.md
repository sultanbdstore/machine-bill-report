# Machine Usage Bill Report Maker

Drop your regular loan-machine Excel (AST, Well Lord, Appear, Printing, BHDP sheets) and get the
month-wise inter-unit **machine usage bill**: dashboard, bill summary, per-unit bill statement,
monthly matrix, running machines and a data-check log. Download a formatted Excel or print any page.

* Fridays and factory-closed holidays are **not billed**; Hindu festivals (factory open) **are billed**.
* Machines not yet returned keep being billed month after month until the return date is entered.
* Runs 100 % in the browser – the Excel file never leaves the computer. No server, no install.

## Use
1. Open the GitHub Pages link (see below) or double-click `index.html`.
2. Drop the Excel file, pick the report month, press **Make report**.
3. **Download Excel report** / **Print this tab**.

On a phone or PC you can "Install app" / "Add to Home screen" (it is a PWA and works offline after the first visit).

## Holidays (year-wise)
* If a year has no holiday dates, the tool **auto-generates** it: fixed national days (21 Feb, 26 Mar, 14 Apr,
  1 May, 5 Aug, 16 Dec, 25 Dec) + **estimated** Eid-ul-Fitr / Eid-ul-Azha (6-day vacation), Ashura,
  Eid-e-Miladunnabi, Shab-e-Qadr. Estimates can be 1 day off and exclude extra government vacation days.
* When the official list is announced, add it under **Holidays** on the page, **or** add a sheet named
  `HOLIDAYS` to your register with columns `Date | Holiday | Closed? (1 = closed, 0 = factory open)`.
  It replaces the estimate for that year automatically.
* Hindu festivals (Durga Puja, Janmashtami) need no entry – factory open means billed.

## Excel format expected
Sheet names like `Loan to AST`, `Loan from Well Lord`, `Loan to Appear`, `Loan To Printing`,
`Send To Bhdp ...` (Loan/Send + To/From + unit). Each sheet needs a heading row with `DATE` and two `QTY`
columns (out / returned). Dates may be real dates or text like `24.05.17`. Check **Checks & import log**
every month: it shows lines read per sheet and lists any row that could not be read.

## Logo
The page shows a default logo. To use your own: open **Logo** on the page and upload a PNG/JPG (saved in that browser), **or** upload your picture to GitHub as `logo.png` next to `index.html` (shows for everyone, on top of the page and on every bill). For the installed-app icon replace the files in `icons/` (`icon-192.png`, `icon-512.png`, `icon-512-maskable.png`).

## Settings
Rates per machine-day, holidays and date corrections are stored in the browser (localStorage) of the device used.

## Publish on GitHub Pages
1. Create a new repository (e.g. `machine-bill-report`) and upload all files of this folder
   (`index.html`, `manifest.webmanifest`, `sw.js`, `.nojekyll`, `icons/`, `README.md`).
2. Repository **Settings → Pages → Build and deployment → Source: Deploy from a branch → Branch: `main` / `(root)` → Save**.
3. After a minute the tool is live at `https://<your-user-name>.github.io/machine-bill-report/`.
4. To update the tool later, replace `index.html` and change `CACHE='mc-bill-v1'` in `sw.js` to `mc-bill-v2` so phones refresh.

## Files
| File | Purpose |
|---|---|
| `index.html` | The whole tool (no libraries, no internet needed) |
| `manifest.webmanifest`, `sw.js`, `icons/` | Installable offline app (PWA) |
| `logo.png` | Your logo (replace this file with your own picture) |
| `.nojekyll` | Tells GitHub Pages to serve files as they are |
