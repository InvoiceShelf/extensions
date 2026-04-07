# PDF templates manifest (`templates.json`)

InvoiceShelf loads this file (default: raw URL on `main`) to list **installable PDF invoice and estimate templates** in **Admin → Modules**, alongside extensions. Installation uses the same download / unzip / copy / complete flow as modules; files are written to `storage/app/templates/pdf/{invoice|estimate}/`.

**Default URL:** `https://raw.githubusercontent.com/InvoiceShelf/extensions/main/templates.json`

Configure per instance with `INVOICESHELF_TEMPLATES_MANIFEST_URL` in `.env` (see InvoiceShelf `config/invoiceshelf.php`).

---

## Root shape

```json
{
  "templates": [
    {
      "slug": "my-invoice-modern",
      "type": "invoice",
      "template_name": "ModernDark",
      "name": "Modern Dark",
      "description": "Minimal invoice layout.",
      "version": "1.0.0",
      "author": "You",
      "license": "MIT",
      "tags": ["minimal"],
      "compatibility": { "min_version": "1.3.0", "max_version": "99.0.0" },
      "repository": "https://github.com/you/module-invoice-modern",
      "download_url": "https://github.com/you/module-invoice-modern/releases/download/v1.0.0/ModernDark.zip",
      "cover": "https://raw.githubusercontent.com/you/module-invoice-modern/main/preview.png"
    }
  ]
}
```

---

## Field reference

| Field | Required | Description |
| ----- | -------- | ----------- |
| `slug` | Recommended | Stable id (kebab-case). |
| `type` | **Yes** | **`invoice`** or **`estimate`**. |
| `template_name` | **Yes** | Blade **basename** without `.blade.php` (e.g. `ModernDark`). Must match a file inside the ZIP. |
| `name` | Yes | Display name. |
| `description` | Recommended | Short summary. |
| `version` | Yes | Must match the release you ship; compared to the stored catalog version after install. |
| `author` | Recommended | Author or org. |
| `license` | Recommended | SPDX or common id. |
| `tags` | Optional | string array. |
| `compatibility` | Recommended | `min_version` / `max_version` for InvoiceShelf app version. |
| `repository` | Recommended | Source URL. |
| `download_url` | Yes | Direct HTTPS URL to a **ZIP** archive. |
| `cover` | **Yes** | HTTPS URL to a **screenshot** (PNG or JPG) shown in Admin → Modules. Entries without `cover` are rejected by InvoiceShelf. |
| `module_name` | Optional | Override auto-generated install id (`PdfTemplate_*`). Prefer default unless you have a collision. |

---

## ZIP package contents

The archive must contain at least:

- One file named **`{template_name}.blade.php`** anywhere in the tree (nested folders allowed).

Optionally:

- **`{template_name}.png`** next to the Blade file (preview thumbnail in template picker).

Example:

```text
invoice/
  ModernDark.blade.php
  ModernDark.png
```

The installer copies into:

- `storage/app/templates/pdf/invoice/ModernDark.blade.php` (when `type` is `invoice`)
- `storage/app/templates/pdf/invoice/ModernDark.png` (if present)

For `type: "estimate"`, use the `estimate/` folder in storage instead.

---

## Publishing

Open a pull request against this repository updating `templates.json`, following [CONTRIBUTING.md](../CONTRIBUTING.md). Keep **`download_url` immutable per version** (versioned GitHub Release assets recommended).

See also: [CATALOG.md](CATALOG.md) (extensions manifest).
