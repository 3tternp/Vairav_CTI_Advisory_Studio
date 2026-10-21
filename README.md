# Vairav CTI Advisory Studio

Standalone browser-based workspace for producing reviewable cyber-threat advisories.

Published site: `https://3tternp.github.io/Vairav_CTI_Advisory_Studio/`

The studio is intentionally independent from the SOC Executive Report Studio. It has its own source history, deployment, testing and Microsoft 365 configuration, so changes to advisory production cannot alter report parsing or executive-report exports.

## Use

Open the published site, begin with a source URL or pasted analyst notes, validate the generated draft, then enable exports only after the analyst-review acknowledgement.

- Supports editable advisory text, vulnerability records and references.
- Produces Word, Markdown, PNG and PDF outputs.
- Offers an optional, interactive Microsoft 365 delivery workflow after tenant administrator setup.
- Does not use an AI service, remote proxy, persistent browser storage or a client-recipient repository.

## Verification boundary

The application produces an analyst-review draft. Validate current vendor guidance, product exposure, version ranges, exploitation claims and recipients before sharing a report. The supplied NGINX example is dated and must not be treated as live intelligence.

## Development and validation

Serve the repository over HTTP(S), rather than opening files directly. Run the included test modules with Node.js and the required local JSZip dependency:

```text
node advisory-template-tests.mjs
node cti-signature-tests.mjs
node m365-tests.mjs
```

See [ADVISORY-README.md](ADVISORY-README.md), [CTI-TEMPLATE.md](CTI-TEMPLATE.md), and [MICROSOFT365-SETUP.md](MICROSOFT365-SETUP.md) for operating and setup details.
