# Commercial Research Agent v2

Purpose:
Take a company URL and public internet evidence, then produce a structured outside-in Commercial Research Brief.

This version intentionally stops short of full GTM design. It is designed to compress the manual research and synthesis work that normally happens before an operator forms a GTM point of view.

## Inputs

Required:
- Company URL

Optional:
- Context
- Product / business-unit focus
- Buyer / persona focus

## Output

1. Company / Business Context
2. Product / Portfolio
3. Customers / Customer Evidence
4. Market / Competitive Context
5. Segmentation Clues / Likely ICPs
6. Buying Architecture
7. Public Evidence on Commercial Motion
8. Pricing / Packaging / Economics
9. Expansion / Cross-Sell Clues
10. Commercial Organization / Resources
11. Commercial Pressure Test
12. Specific Research Gaps / Unknowns
13. Draft Challenger Hypothesis
14. Executive Review

Major findings are framed as Fact, Inference, or Unknown with confidence.

## Run

1. `py -m pip install -r requirements.txt`
2. `py -m streamlit run app.py`
3. Paste your OpenAI API key into the sidebar.
4. Enter a company URL.
5. Click `Research Company`.

## Notes

- Uses OpenAI web search in the Responses API.
- Research quality depends on the amount and quality of public information available.
- The agent should never treat inaccessible internal metrics as public facts.
- The Challenger section is explicitly a draft hypothesis, not a final GTM conclusion.


## Operator heuristic layer

v3 adds a commercial reasoning layer derived from recurring operator patterns, including:

- segment attractiveness vs. account attractiveness
- repeatable operating archetypes
- customer proof as product-market evidence
- multiple GTMs across multi-product portfolios
- buying autonomy and buyer architecture
- land vs. expansion motions
- standardized complexity
- status quo as a competitor
- pricing tied to value creation
- commercial-resource scalability
- job postings as GTM evidence
- contradiction detection
- confidence discipline
- Challenger as a hypothesis layer rather than a predetermined answer

These heuristics are intended to shape how evidence is interpreted, not force prior conclusions onto new companies.


## v4 refinements

v4 keeps the same product boundary and improves the quality of the research brief:

- tighter compression and prioritization
- explicit named-competitor research
- clear separation of direct competitors vs. status quo / incumbent alternatives
- stronger weighting toward customer evidence, job postings, product changes, funding/stage, and partner/channel clues
- less homepage regurgitation
- sharper contradiction handling
- fewer generic internal-data unknowns
- shorter Challenger hypothesis
- Executive Review redesigned as a decision aid rather than a recap


## v5 changes
- Research broadly, report selectively; target ~25-30% less output.
- Long, citation-heavy evidence uses bullets instead of fragile Markdown tables.
- Research gaps move before synthesis.
- Back third now builds: gaps -> pressure test -> Challenger hypothesis -> executive commercial thesis.
- Executive Review is replaced by an Executive Commercial Thesis.
- Removed redundant final validation and "questions worth thinking about" sections.


## v6 changes
v6 keeps the v5 architecture and improves judgment discipline rather than adding scope.

- Dynamic outline: subsections are optional when they do not add signal.
- Information density replaces arbitrary length reduction as the optimization target.
- Removes default repetition between "Key findings" and section bodies.
- Adds an explicit evidence hierarchy so company marketing claims do not visually equal independent validation.
- Adds anti-false-precision rules for ICP thresholds, pricing, implementation timelines, and packaging.
- Tightens the handoff between Pressure Test -> Challenger -> Executive Commercial Thesis so each section must advance the prior analysis.


## v7 changes
v7 focuses on document quality and meeting-readiness while preserving the v6 research discipline.

- Replaces repetitive Fact/Inference/Confidence labels with natural professional prose; uncertainty is surfaced only when material.
- Consolidates the deliverable to 12 sections with a clearer front-to-back narrative.
- Simplifies customer evidence to customer + scope/use case + proof points, followed by a single Customer Base Analysis.
- Rewrites competition in a natural operator voice and removes "commercial implication" labels and obvious category statements.
- Makes ICP flow directly from customer-base evidence instead of restating it.
- Renames Commercial Pressure Test to Commercial Read.
- Reduces Challenger output to Current Positioning -> Teach -> Reframe.
- Rebuilds the ending around a concise Bottom Line designed for pre-meeting use.
- Updates UI examples to position the tool as a reusable commercial / GTM research agent rather than interview prep.
- Adds professional on-screen styling and a polished HTML export with print-friendly colors and formatting.


## v7.1 changes
v7.1 is a targeted cleanup of v7 rather than a redesign.

- Explicitly preserves research recall while keeping the more professional v7 writing style.
- Requires a pre-writing search for cloud marketplace pricing/procurement evidence and other high-value commercial datapoints.
- Prohibits "Commercial implication," "what this proves commercially," and similar AI/consulting meta-labels anywhere in the report.
- Reduces subsection-heading proliferation, especially in ICP / Priority Accounts.
- Adds a silent final editorial QA pass for repeated conclusions, generic statements, omitted concrete evidence, and leftover scaffolding.
- Keeps the 12-section v7 architecture, polished HTML export, and professional UI styling unchanged.


## v8.0 — employer-facing demo build
- Cleaner internal-tool UI and concise About explanation.
- API/model plumbing hidden when configured with environment variables or Streamlit secrets.
- Local API-key fallback appears only when necessary.
- Fixed model behind the scenes by default.
- `Build Commercial Brief` action.
- Public-source provenance and unique source-link count.
- Upgraded presentation-ready HTML export.
- Bottom Line no longer asks “what is this company really selling?”
- Explicit permission for multiple commercial motions where the evidence supports them.

### Launch
`py -m pip install -r requirements.txt`

`py -m streamlit run app.py`

For a clean demo, copy `.streamlit/secrets.toml.example` to `.streamlit/secrets.toml` and add the API key.


## v8.1 — final employer demo

This build adds an embedded Elevate Healthcare example so a reviewer can understand the output immediately without waiting for a live research run.

### Reviewer experience
1. Open the app.
2. Click **View Example Brief** for an immediate finished example.
3. Or enter any company URL and click **Build Commercial Brief**.

The deployed demo should have `OPENAI_API_KEY` configured in Streamlit secrets so no API setup is visible to the reviewer.


## v8.2 — frozen Human Agency demo
- No visible API-key or local-setup controls.
- Reads `OPENAI_API_KEY` from Streamlit secrets or the environment.
- Same clean interface locally and when deployed.
