# n8n Workflow Templates

A small, curated collection of [n8n](https://n8n.io) workflow templates — each one ready to import, with a clean documentation page and an **interactive, read-only preview** of the workflow canvas.

📖 **Browse the templates:** **https://timgranlundmarsden.github.io/n8n-workflow-templates/templates/daily-digest/**

Every template lives in its own folder under [`templates/`](templates/) and ships with:

- **`workflow.json`** — the exportable n8n workflow, with all personal data (credential IDs, sheet IDs, emails, tokens) replaced by placeholders.
- **`index.html`** — a GitHub Pages documentation page that explains the flow, lists what you need, walks through setup, and embeds the workflow as a live [`<n8n-demo>`](https://www.npmjs.com/package/@n8n_io/n8n-demo-component) widget.

---

## Templates

| # | Template | What it does | Docs |
|---|----------|--------------|------|
| 01 | **[Daily Digest — Read Later → Inbox](templates/daily-digest/)** | Pulls saved articles from Raindrop.io, scrapes them with Firecrawl, summarises with an LLM via OpenRouter, and emails a categorised daily digest. <img width="3599" height="1862" alt="image" src="https://github.com/user-attachments/assets/fcffadf7-eb76-4417-9d18-b2777fa08db2" /> | [Open page ↗](https://timgranlundmarsden.github.io/n8n-workflow-templates/templates/daily-digest/) |

_More templates coming — each added as a new numbered folder._

---

## Using a template

1. Open the template's documentation page (linked above) to understand the flow and prerequisites.
2. Download its `workflow.json` (the page has a download button, or grab it from the folder).
3. In n8n, go to **Workflows → Import from File** and select the JSON.
4. Connect the required credentials and replace any `REPLACE_WITH_YOUR_…` placeholders.
5. Run once with the manual trigger to test, then activate.

Each page documents the specific accounts, API keys and credentials that template needs.

---

## A note on the read-only preview

The documentation pages embed the official n8n web component to render the workflow canvas:

```html
<script src="https://cdn.jsdelivr.net/npm/@n8n_io/n8n-demo-component/n8n-demo.bundled.js"></script>
<n8n-demo workflow="...url-encoded workflow json..."></n8n-demo>
```

Because the component must fetch its JSON over HTTP(S), the live preview renders on the published GitHub Pages site (not when opening `index.html` directly from disk). The page degrades gracefully to a download link if the preview can't load.

---

## Repository layout

```
n8n-workflow-templates/
├── index.html           # homepage — lists all templates
├── README.md
├── LICENSE
└── templates/
    ├── index.html       # redirects back to the homepage
    └── daily-digest/
        ├── index.html      # GitHub Pages documentation + live preview
        ├── workflow.json    # importable, PII-free workflow
        └── img/             # screenshots used on the page (e.g. example output)
```

---

## License

See [LICENSE](LICENSE).
