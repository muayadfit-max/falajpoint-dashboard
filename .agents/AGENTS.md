# FalajPoint Dashboard Workflow Rules

## Handling Status Updates
When the user provides a status update in the chat for a specific company (e.g., "Update status for Oman Fertilizer Company: Called on 2026-07-09..."), you must:
1. Locate the company in `index.html` within the `companiesData` object.
2. Add or update the `statusNote` field for that company with the exact text provided by the user (including the date if provided).
3. Use your code editing tools (e.g., `multi_replace_file_content` or `replace_file_content`) to update the file.
4. Commit and push the changes to GitHub with a message like "Updated status for [Company Name]".
