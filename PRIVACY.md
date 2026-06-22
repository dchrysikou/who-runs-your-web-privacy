
# Who Runs Your Web — Privacy Policy

**Last updated:** June 2026

Who Runs Your Web is a Chrome extension that checks the TLS security, encryption strength, and third-party tracking exposure of websites you visit. This policy explains exactly what data the extension touches, what stays on your device, and what — if anything — ever leaves it.

## What the extension does

When you visit an HTTPS website, the extension automatically:

- Checks that site's TLS certificate and connection security via our backend scanning service
- Detects which third-party domains (trackers, analytics, fonts, ad networks, etc.) loaded on that page
- Calculates Trust, Harvest Defence, and Quantum Readiness scores based on these checks
- Stores the result locally in your browser so you can review your own browsing exposure over time

## Data stored on your device

All scan results — including the domain you visited, the scores calculated, and the third-party connections detected — are stored locally in your browser's extension storage (`chrome.storage.local`). This data:

- Never leaves your device by default
- Is fully under your control — viewable, exportable, and deletable at any time from the extension's dashboard
- Is not accessible to us, to the extension developer, or to any third party, unless you explicitly choose to export it yourself

## Data sent to our scanning service

To check a site's TLS certificate and security headers, the extension sends the **domain name** (not the full URL, and never any page content, form data, or personal information) to our scanning API, hosted on Railway. This is necessary to perform the security check itself — no scan can happen without it. This request is not logged or stored by us beyond what's needed to return the result to your browser.

## Optional anonymous aggregate reporting

The extension includes an **opt-in, off-by-default** feature that lets you contribute anonymized data toward a public picture of internet infrastructure concentration. This feature:

- Is **disabled by default**. Nothing is ever sent unless you actively turn it on in the extension's dashboard.
- Can be turned off at any time, with immediate effect.
- When enabled, sends only the following per scan, in batches (never in real time, never one at a time):
  - The detected hosting/CDN provider (e.g. "Cloudflare"), if disclosed by the site
  - The Trust, Harvest, and Quantum scores
  - The *categories* of third-party trackers detected (e.g. "advertising," "analytics") — never the specific tracker domain names
- **Never includes:** the domain or URL you visited, any timestamp tied to your visit, your IP address, or any other identifier. There is no way to reconstruct your browsing history, or even a single visited site, from this data.
- Is stored in a dedicated database used only to build aggregate, public statistics about infrastructure concentration across the web — not to profile individual users, because individual users cannot be identified from this data.

## What we never collect

The extension does not collect, transmit, or have access to:

- Your browsing history as a list of visited sites (beyond the single domain needed to perform each scan, which is not logged)
- Page content, form inputs, passwords, or any data you enter on websites
- Your IP address, location, or any device/account identifiers
- Any data from sites you visit that isn't directly related to TLS security or third-party detection

## Third-party services

The extension's backend uses:

- **Railway** — hosts the TLS scanning service that checks certificate and header data
- **Supabase** — hosts the anonymous aggregate reporting database (only used if you opt in) and the AI-powered pattern analysis feature
- **OpenAI** — powers the optional "Analyse my browsing" feature, which summarizes your own locally-stored scan history into plain-English insights. This request includes only the scores and tracker categories from your own scan history, sent at your explicit request when you click "Analyse my browsing" — never your domain names, URLs, or any other identifying information.

## Your control over your data

You can, at any time, from the extension's dashboard:

- View all locally stored scan history
- Export your full scan history as a JSON file
- Import previously exported data
- Turn anonymous reporting on or off
- Clear your local scan history entirely

## Changes to this policy

If this policy changes, the "Last updated" date above will be revised, and material changes will be reflected in the extension's user interface.

## Contact

Questions about this policy or how the extension handles data can be raised via [GitHub Issues](https://github.com/dchrysikou/trust-scanner-extension/issues).
