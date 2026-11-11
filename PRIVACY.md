# Who Runs Your Web — Privacy Policy

**Last updated:** November 2026 (version 2.0.0)

Who Runs Your Web is a Chrome extension that shows which companies are behind the sites you visit, checks how well each site's connection is encrypted, and can optionally block ad and tracker requests. This policy explains what the extension touches, what stays on your device, and what leaves it.

**We do not sell your data, and we do not share it with data brokers or advertisers.**

## What the extension does

When you visit a website, the extension automatically:

- Reads the list of addresses the page loaded (the browser's own resource list) to work out which third-party companies are on the page. It reads host names only, never the content of the page, what you type, or your cookies.
- Asks our scanning service to check the site's TLS certificate and security headers (see "Data sent to our scanning service").
- Calculates scores and a plain-English summary from these checks. Some scores are estimates and are labelled as such.
- Stores the result on your device so you can review your own browsing over time.

## Data stored on your device

Scan results, including the sites you visited, the scores and the third-party companies found, are stored in your browser's extension storage (`chrome.storage.local`). The extension keeps up to 500 scans and at most 3 per site, newest first. This data:

- Stays on your device. We do not receive it.
- Can be viewed, exported and deleted at any time from the extension's dashboard.
- Is not accessible to us or to any third party unless you export it yourself.

Your blocking choices (which switches are on, which sites are paused) are stored the same way.

## Ad and tracker blocking (optional)

The extension can block ad and tracking requests. It is **off by default**. It uses Chrome's built-in rule engine (`declarativeNetRequest`) with lists bundled inside the extension (derived from EasyList and EasyPrivacy), plus per-company rules you choose. Chrome applies the rules itself, so the extension never sees the content of your traffic, and nothing is downloaded to update the lists. To show "Stopped N requests", the extension asks Chrome which of its own rules matched on a page. That count is stored on your device with the scan.

## Data sent to our scanning service

To check a site's TLS certificate and security headers, the extension sends the **host name** of the page (for example `www.example.com`) to our scanning service, hosted on Railway. It does not send the full address, the page content, form data, cookies, or any identifier such as an install ID. This is necessary for the check itself.

<!-- CONFIRM BEFORE PUBLISHING: what does the Railway service log or keep (request logs, IP addresses, retention)? State it here. If you have not checked, keep this paragraph limited to what the extension sends. -->

## Anonymous usage counts

So the developer can tell whether the extension is used and kept, it sends a small number of anonymous usage events. This is **on by default** and can be switched off at any time with the "Anonymous usage counts" switch in Settings & privacy. When it is on, the extension sends:

- A **random install ID**, generated on your device when you install. It is not linked to your name, email, browser account, or anything you browse.
- The **extension version**.
- An **event name**: "first open" (the first time you open the dashboard), "still active" (at most once a day), or "uninstall".

This is stored in our Supabase database and used only to count installs, active use and how long people keep the extension. It never includes any website, domain, score or browsing information. Our hosting providers may keep standard network logs (such as IP addresses) for a limited time as part of running their services; we do not copy them into our own records.

When you switch usage counts off, nothing further is sent and the uninstall page is no longer set up.

**On uninstall.** If usage counts are on, Chrome opens a short page when you remove the extension, asking what was missing. Answering is optional. Counting the uninstall happens when the page loads; if you submit a reason, it is stored with your install ID.

## Feedback you choose to send

The "What would you like to see?" link in the dashboard lets you send a message. If you use it, we receive the topic you pick, anything you type, the extension version, and an email address only if you choose to add one. Please do not include personal details or sites you visited. We use feedback only to decide what to build or fix, and we reply only if you gave an email address and asked for a reply.

## AI analysis (optional)

"Analyse my browsing" is optional and sends nothing unless you click it. When you do, the extension sends a summary of your recent scan history to our Supabase function, which passes it to OpenAI to write the plain-English insights. **That summary includes the domain names of sites you visited**, their scores, and the names of third-party domains found on them. It does not include full addresses, page content, or anything that identifies you. We do not store the request or the response.

## What we never collect

- Your browsing history as a list of sites. The only exception is the host name sent for each scan (see above), and the domain names in the AI summary if you click the button.
- Page content, form inputs, passwords, cookies, or anything you type on websites.
- Your location, your name or your account details.
- Anything for advertising or for sale. We do not sell, rent or trade data.

An earlier version of the extension offered an opt-in "anonymous reporting" feature. It has been removed. Any reports that were still waiting on your device are deleted when the extension updates, and nothing further is sent.

## Permissions

The extension asks Chrome for these permissions and uses each only for the purpose shown:

- **tabs**: to see which page a tab is on, so it can scan it, show the result, and reload it after you change a setting.
- **scripting**: to read the page's list of loaded resources (host names only).
- **storage**: to keep your history and settings on your device.
- **alarms**: a timer used for the once-a-day "still active" count.
- **declarativeNetRequest and declarativeNetRequestFeedback**: to block ad and tracker requests and to count what was blocked.
- **Access to all sites**: so the scan and the blocking work on whichever site you open.

## Third-party services

- **Railway** — hosts the scanning service that checks certificate and header data.
- **Supabase** — stores the anonymous usage counts and the feedback messages described above, and runs the function that passes your request to OpenAI for the optional AI analysis.
- **OpenAI** — writes the optional AI analysis (see above).

## Your control over your data

From the extension's dashboard you can, at any time:

- View all locally stored scan history
- Export it as a JSON file, and import a previous export
- Turn anonymous usage counts on or off
- Turn ad and tracker blocking on or off, pause it for one site or everywhere
- Clear your local scan history entirely

Removing the extension deletes everything it stores on your device.

## Changes to this policy

If this policy changes, the "Last updated" date will be revised, and material changes will be reflected in the extension's interface.

## Contact

Questions about this policy or how the extension handles data can be raised via [GitHub Issues](https://github.com/dchrysikou/who-runs-your-web-privacy/issues) or by email at whorunsyourweb@gmail.com.
