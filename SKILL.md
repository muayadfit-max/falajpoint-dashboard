# FalajPoint Business Development Research Skill

**Purpose**  
Turn any target company name into high-quality, actionable business development intelligence for FalajPoint (100% Omani chemical engineering advisory firm) and visualize everything inside **one single reusable interactive dashboard**.

**Core Principle (Non-Negotiable)**  
You **MUST** always work with the single master file:  
**`/home/workdir/artifacts/falajpoint-bd-dashboard.html`**  

Never create a new HTML file for each company. Always append or update the company inside the existing dashboard. This keeps all research in one place with consistent UX, diagram engine, and interactivity.

---

## The Mandatory 3-Step Workflow

### STEP 1: Deep Company Research (LinkedIn-First)

You are a business development researcher for FalajPoint.

Follow this exact 3-phase flow for every company:

**PHASE 1: LINKEDIN RECONNAISSANCE**  
- Search the company LinkedIn page directly.  
- Record: follower count, page status (ACTIVE / MODERATE / THIN / NONE), recent post topics & frequency, hiring signals, leadership visibility, employee sentiment.  
- Note specific examples from the last 10–20 posts.

**PHASE 2: DEEP RESEARCH**  
After LinkedIn, investigate:  
- Company website (professionalism, clarity, certifications, blog activity)  
- Public records (Oman Chamber, Ministry registrations, PDO/JSRS vendor status if relevant)  
- Google/news mentions, Google reviews, any Glassdoor/employee signals  
- Industry context, competitors, regulatory pressures in Oman/GCC  
- Recent news, expansions, partnerships, tenders

**PHASE 3: 8-STEP ASSESSMENT**  
Synthesize into the exact structure used in the dashboard:

1. **COMPANY SNAPSHOT** (3–4 sentences)  
2. **LINKEDIN CHECK** (status, followers, activity, hiring, sentiment)  
3. **DEEPER RESEARCH FINDINGS** (website, records, industry, signals, news)  
4. **LIKELY BOTTLENECKS** — Label each as `[EVIDENCED]` or `[HYPOTHESIS]` with reasoning. Prioritize the top 3 most actionable.  
5. **FALAJPOINT FIT** — Map bottlenecks to these services:  
   - Independent Chemical Selection & Advisory  
   - Feasibility Assessment & Technical Due Diligence  
   - Process Improvement & Optimization  
   - Coating & Surface-Treatment Advisory  
   - Water Treatment & Industrial Effluent Advisory  
   - Oilfield & Refinery Chemicals Advisory  
   - ICV & Omanisation Advisory  
   - Chemical Compliance & Regulatory Advisory  
   - Formulation & Product-Development Feasibility  
   - Technical Mentoring & Engineering Capacity  
6. **WHO TO APPROACH** — Target roles + specific people found on LinkedIn (name + link or “Not found”) + best entry method.  
7. **VISIT OPENING** — 3–4 sentence natural, conversational pitch that references something real you discovered.  
8. **OBJECTION HANDLING** — 2–3 sentence answer to “Why FalajPoint instead of a big consultancy?” tailored to this company (ICV, vendor-neutral, agility, or credibility angle).

Also record: Priority (HIGH/MED/LOW), Confidence (High/Medium/Low), Website, exact location, headcount estimate.

**Rules for Step 1**  
- Start with LinkedIn. Never invent facts. Mark inferences clearly as `[HYPOTHESIS]`.  
- Be specific — reference actual posts, hiring patterns, website content.  
- If data is thin, state it honestly.

---

### STEP 2: Organize into the 6 Dashboard Sections

Condense the research into exactly these six sections. Keep language concise and sales-oriented.

1. **Contact Details**  
   All phones, emails, WhatsApp, website, LinkedIn company page, best contact channels and times.

2. **Location**  
   Full physical address + practical access notes (gate, parking, nearest landmarks, best visiting hours).

3. **Key Bottlenecks** (Top 3 only)  
   For each: short title + `[EVIDENCED]` or `[HYPOTHESIS]` + one-sentence reasoning. Use the most important ones from Step 1 Phase 3 #4.

4. **Key Contacts** (Ranked 1–3)  
   Name, exact title, LinkedIn link (or “Not found”), best way to reach them, and why they matter.

5. **Visit Protocol**  
   Step-by-step practical plan: how to get the meeting, what to bring, exact opening question (from Step 1 #7), duration, follow-up.

6. **Sales Strategy**  
   Recommended positioning, the best angle for this specific company, the natural opening pitch, and the objection-handling paragraph tailored to their situation.

---

### STEP 3: Update the Single Master Dashboard (Most Important)

**You must output the COMPLETE updated HTML file content.**

**Process:**
1. Open/read the current `/home/workdir/artifacts/falajpoint-bd-dashboard.html`
2. Locate the `companiesData` JavaScript object (near the top of the `<script>` section).
3. Add a new key (or update existing) using the **exact schema** below.
4. Output the **full HTML** with your new/updated company included.
5. Tell the user: “Replace the existing `falajpoint-bd-dashboard.html` with this new version. All previous companies remain accessible in the dropdown.”

**Never** create a second HTML file. Never change the visual layout, CSS, JS interactivity, or modal logic — only add data inside `companiesData`.

#### Exact Schema to Follow When Adding a Company

```js
"Company Legal Name LLC": {
    name: "Company Legal Name LLC",
    industry: "Specific Industry (e.g. Fertilizer Blending & Agro-Chemicals)",
    location: "Full address, City, Governorate, Oman",
    headcount: "~XX employees",
    website: "https://...",
    status: "Thoroughly researched" | "Limited data",
    priority: "HIGH" | "MED" | "LOW",
    confidence: "High" | "Medium" | "Low",
    lastUpdated: "2026-07-01",

    snapshot: "3-4 sentence overview of what they do, size, ownership, growth stage and recent direction.",
    
    linkedin: {
        status: "ACTIVE" | "MODERATE" | "THIN" | "NONE",
        followers: "number",
        activityLevel: "description of posting frequency and topics",
        keyFindings: "specific examples from posts",
        hiringSignals: "what roles and what it signals",
        leadershipSentiment: "tone and visibility of leaders/employees"
    },
    
    deeperResearch: {
        website: "...",
        publicRecords: "...",
        industryContext: "...",
        customerEmployeeSignals: "...",
        recentNews: "..."
    },
    
    sections: {
        contactDetails: {
            teaser: "Short 1-line summary for the diagram box",
            fullHtml: "Rich HTML content for the modal (phones, emails, notes...)"
        },
        location: {
            teaser: "Short practical location summary",
            fullHtml: "Detailed address + access notes in HTML"
        },
        keyBottlenecks: {
            teaser: "Concise summary of top issues",
            items: [   // exactly 3
                { title: "...", type: "EVIDENCED" | "HYPOTHESIS", reasoning: "..." },
                ...
            ]
        },
        keyContacts: {
            teaser: "Top person summary",
            people: [
                { rank: 1, name: "...", title: "...", linkedin: "url or 'Not found'", bestEntry: "...", contactInfo: "..." },
                ...
            ]
        },
        visitProtocol: {
            teaser: "Short visit plan summary",
            steps: ["Step 1...", "Step 2...", ...]   // or fullHtml
        },
        salesStrategy: {
            teaser: "Positioning summary",
            fullHtml: "Opening pitch + objection handling + best angle in rich HTML"
        }
    },
    
    fullReport: {
        step1: "...",   // snapshot
        step2: "...",   // LinkedIn check
        step3: "...",   // deeper findings
        step4: [ {title, type, detail}, ... ],
        step5: "...",   // FalajPoint fit
        step6: "...",   // who to approach
        step7: "...",   // visit opening quote
        step8: "..."    // objection handling
    }
}
```

**After adding the data**, test mentally that:
- The diagram boxes will show nice teasers
- Clicking boxes opens rich modals
- “View Full 8-Step Research Report” shows clean formatted content
- The company appears in the top dropdown

---

## Usage by the AI Agent

When the user says “Research [Company Name]” or “Add [Company] to the dashboard”:

1. Run **Step 1** thoroughly (use web_search, browse_page, x_keyword_search etc. as needed).
2. Run **Step 2** to create the six clean sections.
3. Run **Step 3** — read the current dashboard file, add the new company object following the schema exactly, and output the **complete updated HTML**.
4. Instruct the user to save the output over the existing file.

This guarantees one beautiful, growing command center instead of dozens of fragmented HTML files.

---

## File Location

Master Dashboard: `/home/workdir/artifacts/falajpoint-bd-dashboard.html`

The dashboard already contains one high-quality example company (“Sohar AgriChem LLC”) so you can see exactly how the data renders. Use it as your template for new entries.

**Remember**: Quality > quantity. One deep, well-structured company entry is far more valuable than several shallow ones.

---

*Skill created for consistent, professional, and unified business development intelligence at FalajPoint.*