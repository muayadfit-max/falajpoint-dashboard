# FalajPoint Dashboard Workflow Rules

The whole dashboard is one file: `index.html` at the repository root. All company data lives in the `companiesData` object inside its `<script>`. Never create a second HTML file.

## Adding a New Company
When the user says "Research [Company]" or "Add [Company] to the dashboard":
1. Follow the `falajpoint-bd-research` skill (`.agents/skills/falajpoint-bd-research/SKILL.md`) step by step, and use the `social-selling` skill (`.agents/skills/social-selling/SKILL.md`) for the contacts, visit protocol and sales speech.
2. Add the company as the **first** entry in `companiesData`, using the skill's schema exactly, with all seven sections: `resources`, `contactDetails`, `keyBottlenecks`, `location`, `keyContacts`, `visitProtocol`, `salesStrategy`, plus `fullReport` (step1–step8).
3. Use an existing company (e.g. Sharakah) as the formatting template. Do not change CSS, layout or JavaScript logic; only add data.
4. Open the page and check there are no errors, the company appears in the dropdown, and every card opens.
5. Commit and push with a message like "Added [Company Name] to dashboard".

## Handling Status Updates
When the user provides a status update in the chat for a specific company (e.g., "Update status for Oman Fertilizer Company: Called on 2026-07-09..."), you must:
1. Locate the company in `index.html` within the `companiesData` object.
2. Add or update the `statusNote` field for that company with the exact text provided by the user (including the date if provided).
3. Update the company's `lastUpdated` date to today.
4. Use your code editing tools to update the file.
5. Commit and push the changes to GitHub with a message like "Updated status for [Company Name]".

## Company Status Colors (`registrationStatus`)
- `"Registered"` → 🟢 green
- `"Proposal Processed"` → 🔵 blue (a proposal has been submitted / is being processed)
- `"Pending"` → 🟡 yellow
- `"Not Yet Registered"` (or empty) → 🔴 red

## Archiving or Restoring a Company
To archive a company, add its exact `companiesData` key to the `archivedCompanyNames` list in `index.html`; to restore it, remove it from that list. Do not delete company data unless the user explicitly asks to remove the company. Commit with a message like "Archived [Company Name]".

## Adding Resources (links, presentations, Drive folders, videos)
Add an entry to the company's `sections.resources.links` array (`title`, `type`, `url`, `description`) and update the `resources.teaser` count, e.g. "2 Resources: Meeting Presentation + RFP Folder".

## Going Live
The live website updates from the `main` branch. If the change was pushed to a different branch, tell the user it still needs to be merged into `main` before it shows on the website.

## Privacy: Keep the Dashboard Out of Search Engines
The dashboard contains private business intelligence and must never be indexed. Always keep the `<meta name="robots" content="noindex, ...">` tags in `index.html` and the `X-Robots-Tag` header in `vercel.json`. Do NOT add a `robots.txt` that disallows crawling: it would stop Google from seeing the noindex instruction.
