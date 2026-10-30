# ONMX Treasury Vesting (GitHub Pages)

Static public page for the **725,000,000 ONMX** Treasury Reserve & LP **8-year linear** vesting schedule (Magna, powered by Kraken).

## Package contents

| File | Purpose |
| --- | --- |
| `index.html` | Single-file site: schedule, countdown, tranche table, interactive vesting curve with hover tooltips (date + exact vested amount) |
| `.nojekyll` | Tells GitHub Pages to serve files as-is (skip Jekyll) |
| `README.md` | This setup note |

## Edit the schedule (one place)

Open `index.html` and find the **`CONFIG`** block near the bottom `<script>`:

```js
const VESTING_START_ISO = "2026-11-01T00:00:00.000Z"; // UPDATE when Magna production start is public
const VESTING_YEARS = 8;
const TREASURY_RESERVE = 725_000_000;
```

Change `VESTING_START_ISO` (and amounts if needed) — countdown, curve, and tooltips all recompute from those constants.

## Setup: push → enable Pages → public URL

1. Create a new GitHub repository (public if you want a free `*.github.io` URL without a Pro plan caveat for private repos).
2. Upload or push this folder to the repo root (so `index.html` is at the repository root, or under `/docs` if you prefer the docs folder source).
3. In the repo: **Settings → Pages**.
4. Under **Build and deployment → Source**, choose **Deploy from a branch**.
5. Branch: `main` (or `master`), folder: **/ (root)** — or `/docs` if you put the files there.
6. Save. After a minute or two the site is live at:

`https://<username>.github.io/<repo-name>/`

Example: user `onchainmatrix`, repo `treasury-vesting` → `https://onchainmatrix.github.io/treasury-vesting/`

## Notes

- Hover (or drag on touch) the curve for TokenUnlocks-style tooltips: **date + exact vested ONMX**.
- Magna **Treasury Reserve & LP** vesting is **Live** on BNB Chain: `0x3B76052ee5f726FE1daC596e9ad4ea6C76E26520` (holds 725M ONMX).
- Set `VESTING_START_ISO` to Magna’s authoritative schedule start when confirmed; countdown + curve recompute from that constant.
