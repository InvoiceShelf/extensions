# InvoiceShelf extensions catalog

This repository publishes the **public extensions manifest** consumed by [InvoiceShelf](https://github.com/InvoiceShelf/InvoiceShelf). The app fetches `extensions.json` (default: raw URL on the `main` branch) to power the in-app **Modules** experience: browse, install, and update curated extensions.

**Default manifest URL:** `https://raw.githubusercontent.com/InvoiceShelf/extensions/main/extensions.json`

---

## Documentation

| Document | Description |
| -------- | ----------- |
| [**Catalog & publishing guide**](docs/CATALOG.md) | Manifest schema, ZIP layout, compatibility, release workflow, PR checklist |
| [**Contributing**](CONTRIBUTING.md) | How to propose changes and what reviewers look for |
| [**Entry template (JSON)**](docs/examples/extension-entry.template.json) | Copy-paste starter for a new `extensions` item |

---

## Quick facts

- **Curated list** — Extensions are **not** uploaded here as binary releases; each entry points to your own Git repository and a **direct HTTPS URL** to a versioned **ZIP** (typically a GitHub Release asset).
- **Open contribution** — Add or update your extension metadata via **pull request** to `extensions.json` on `main`.
- **License** — The JSON catalog in this repo is metadata; each extension’s **license** is declared per entry and applies to the extension package itself.

---

## Related links

- [InvoiceShelf](https://github.com/InvoiceShelf/InvoiceShelf) — application source
- [Developer guide](https://docs.invoiceshelf.com/developer-guide.html) — general development
- [Discord](https://discord.gg/eHXf4zWhsR) — community support
