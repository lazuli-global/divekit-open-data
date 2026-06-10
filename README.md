# <img src="assets/divekit/favicon.png" alt="Dive Kit" width="32" height="32" align="center" /> Project Dive Kit — Open Data & Standards

**Welcome to the open data, schemas, and public standards hub of the Dive Kit ecosystem.**
This repository powers [open.divekit.app](https://open.divekit.app) — the canonical home for all open, machine-readable resources maintained by the Dive Kit project.

---

## 🧭 Purpose

`lazuli-global/divekit-open-data` provides:

- **Public Datasets** – Canonical, versioned JSON datasets for dive certifications, agencies, cylinders, and dive signals.
- **Schemas & Standards** – JSON Schema definitions for validating and interoperating with Dive Kit's open data formats.
- **Visual Assets** – Openly licensed dive signal illustrations (CC BY 4.0), agency logos (third-party trademarks), and Dive Kit branding.
- **Documentation** – Design guidelines, contributor guidelines, and open-data governance notes.

Our goal is to make diving data **accessible, standardized, and developer-friendly**, so apps, researchers, and training platforms can all share a common foundation.

---

## 📁 Repository Structure

```
divekit-open-data/
├── datasets/
│ ├── certifications.json
│ ├── agencies.json
│ ├── cylinders.json
│ ├── dive-signals.json
│ └── LICENSE.md
│
├── schemas/
│ ├── certifications/
│ │ └── dive-certifications.schema.v1.0.0.json
│ ├── agencies/
│ │ └── agencies.schema.v1.0.0.json
│ ├── cylinders/
│ │ └── cylinders.schema.v1.0.0.json
│ ├── dive-signals/
│ │ └── dive-signals.schema.v1.0.0.json
│ └── LICENSE.md
│
├── assets/
│ ├── dive-signals/       # CC BY 4.0 licensed signal illustrations
│ │ ├── hand/core/
│ │ ├── hand/technical/
│ │ ├── hand/fish-id/
│ │ ├── light/
│ │ ├── buddy-contact/
│ │ └── LICENSE.md
│ ├── agency-logos/       # Third-party trademarks
│ │ └── ...
│ ├── divekit/              # Dive Kit brand assets
│ │ ├── logo.png
│ │ ├── logo-circle-light.png
│ │ ├── logo-circle-dark.png
│ │ └── favicon.png
│
├── docs/
│ ├── DATASETS.md
│ ├── COLORS.md
│ └── LICENSE.md
│
├── scripts/
│ ├── validate.sh
│ └── test-local.sh
│
├── index.html
├── 404.html
├── CONTRIBUTING.md
├── LICENSE.md
└── CNAME (→ open.divekit.app)

```

---

## 🧩 Key Resources

| Resource                        | Description                                                        | URL                                                                                                   |
| ------------------------------- | ------------------------------------------------------------------ | ----------------------------------------------------------------------------------------------------- |
| **Dive Certifications Dataset** | Comprehensive global database of scuba certifications and agencies | [View JSON →](https://open.divekit.app/datasets/certifications.json)                                    |
| **Dive Certifications Schema**  | JSON Schema for validating certification data                      | [View Schema →](https://open.divekit.app/schemas/certifications/dive-certifications.schema.v1.0.0.json) |
| **Agencies Dataset**            | List of recognized certifying agencies                             | [View JSON →](https://open.divekit.app/datasets/agencies.json)                                          |
| **Agencies Schema**             | JSON Schema for validating agencies data                           | [View Schema →](https://open.divekit.app/schemas/agencies/agencies.schema.v1.0.0.json)                  |
| **Cylinder Database**           | Specifications for common scuba cylinders                          | [View JSON →](https://open.divekit.app/datasets/cylinders.json)                                         |
| **Cylinder Schema**             | JSON Schema for validating cylinder data                           | [View Schema →](https://open.divekit.app/schemas/cylinders/cylinders.schema.v1.0.0.json)                |
| **Dive Signals Dataset**        | Diver communication signals with names, meanings, and artwork      | [View JSON →](https://open.divekit.app/datasets/dive-signals.json)                                      |
| **Dive Signals Schema**         | JSON Schema for validating dive signal data                        | [View Schema →](https://open.divekit.app/schemas/dive-signals/dive-signals.schema.v1.0.0.json)          |
| **Dive Signal Illustrations**   | CC BY 4.0 vector artwork for every signal in the dataset           | [View Illustrations →](https://github.com/lazuli-global/divekit-open-data/tree/main/assets/dive-signals) |
| **Agency Logos**                | Collection of scuba diving agency logos                            | [View Logos →](https://github.com/lazuli-global/divekit-open-data/tree/main/assets/agency-logos)        |
| **Dataset Documentation**       | Beginner-friendly guide to understanding and contributing          | [View Guide →](https://open.divekit.app/docs/DATASETS.md)                                               |
| **Docs**                        | Design guidelines and documentation                                | [View Docs →](https://github.com/lazuli-global/divekit-open-data/tree/main/docs)                        |

---

## 🧠 How to Use

### For Everyone

If you're new to working with data or just want to understand what's in these datasets, check out our [Dataset Documentation](https://open.divekit.app/docs/DATASETS.md) for a beginner-friendly guide.

### For Developers

You can consume the datasets directly from the web:

```bash
curl https://open.divekit.app/datasets/certifications.json
```

Validate them against the corresponding schema:

```bash
npx ajv validate \
  -s https://open.divekit.app/schemas/certifications/dive-certifications.schema.v1.0.0.json \
  -d https://open.divekit.app/datasets/certifications.json
```

### For Designers / Educators

Use the dive signal illustrations from [`assets/dive-signals`](https://github.com/lazuli-global/divekit-open-data/tree/main/assets/dive-signals)
in briefing cards, slides, posters, or your own apps. They are licensed **CC BY 4.0**: free for any use,
including commercial, as long as you credit "Dive signals by Project Dive Kit — https://divekit.app".

Agency logos in [`assets/agency-logos`](https://github.com/lazuli-global/divekit-open-data/tree/main/assets/agency-logos)
are third-party trademarks and should be used for reference purposes only.

---

## ✅ Validation

Before submitting changes, you can validate the datasets locally:

```bash
./scripts/validate.sh
```

This script will:

- ✅ Validate schema files against JSON Schema specifications
- ✅ Validate each JSON dataset file against its referenced schema
- ✅ Check for duplicate IDs within datasets
- ✅ Report detailed errors if validation fails

**Requirements:**

- [Bun](https://bun.sh) (recommended) or Node.js
- [jq](https://jqlang.github.io/jq/) (JSON processor)

All pull requests are automatically validated via GitHub Actions.

---

## 🤝 Contributing

We welcome contributions of:

- New or corrected certification data
- Updated equivalencies or limits
- Additional recognized agencies
- Translations or metadata
- Documentation improvements

📚 **New to contributing?** Start with our [Dataset Documentation](docs/DATASETS.md) for a step-by-step guide on how to add or update data.

For technical details, see [`CONTRIBUTING.md`](CONTRIBUTING.md) for workflow and validation rules.

All JSON datasets must pass schema validation via CI before merging.

---

## 🧾 License

Unless otherwise noted:

| Type                   | License                                                   | Notes                                            |
| ---------------------- | --------------------------------------------------------- | ------------------------------------------------ |
| **Datasets & Docs**    | [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) | Free to share/remix with attribution             |
| **Dive Signal Illustrations** | [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) | Credit "Dive signals by Project Dive Kit — https://divekit.app" |
| **Schemas & Code**     | [MIT](https://opensource.org/licenses/MIT)                | Free to use in software projects                 |
| **Agency Logos**       | Third-party trademarks                                    | Owned by respective agencies, reference use only |
| **Dive Kit Brand Assets** | All rights reserved                                       | Dive Kit trademark, permission required for use     |

See [LICENSE.md](LICENSE.md) for full details.

---

## 🗓️ Versioning & Governance

Each dataset and schema is versioned semantically (`v1.0.0`, `v1.1.0`, …).
Breaking changes will increment the major version.

All changes are tracked via pull requests and validated in CI.
Community suggestions are discussed in [Discussions](https://github.com/lazuli-global/divekit-open-data/discussions).

---

## 🧭 Mission

> Dive Kit Open exists to unify how the diving world represents, shares, and understands its data — safely, transparently, and for everyone.

---

**Maintained by:** [Project Dive Kit](https://github.com/lazuli-global)
**Canonical URL:** [https://open.divekit.app](https://open.divekit.app)
