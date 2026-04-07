# Contributing to the extensions catalog

Thank you for helping grow the InvoiceShelf extension ecosystem.

## Pull requests

1. **Fork** this repository and create a branch from `main`.
2. **Edit** `extensions.json` — add a new object under `extensions` or update an existing entry (see [docs/CATALOG.md](docs/CATALOG.md)).
3. **Validate** JSON (IDE or `jq empty extensions.json`).
4. **Open a PR** with a clear title, e.g. `Add extension: my-slug` or `Update payments to 1.2.0`.
5. Ensure **`download_url` returns HTTP 200** and a valid ZIP without authentication (verify in a browser or with `curl -I`).

### PDF templates (`templates.json`)

1. Edit **`templates.json`** (see [docs/TEMPLATES.md](docs/TEMPLATES.md)).
2. Add **`cover`** — a **required** HTTPS URL to a screenshot (store cards and InvoiceShelf validation).
3. Add **`packages/pdf-templates/*.zip`** and **`previews/*.png`** to this repo when hosting native or third-party packs here.

## What maintainers check

- [ ] Valid JSON; root object includes an `extensions` array.
- [ ] Required fields present; `slug` unique; `version` matches the packaged release.
- [ ] `download_url` is HTTPS, versioned, and publicly accessible.
- [ ] `compatibility.min_version` / `max_version` align with InvoiceShelf versions you support.
- [ ] `repository` points to the canonical source (issue tracker, license).
- [ ] `cover` URL loads (required for `templates.json`; recommended for `extensions.json`).
- [ ] No secrets, tokens, or private URLs in the manifest.

## Questions

Open a [discussion or issue](https://github.com/InvoiceShelf/extensions/issues) on this repository, or ask on [Discord](https://discord.gg/eHXf4zWhsR).
