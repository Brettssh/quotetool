# Decision log

Append-only. One row per decision. Never edit or delete a row; record a reversal as a new row.

| Date | Decision | Why | Who |
|---|---|---|---|
| 2026-11-18 | Start the Zoho Quote Tool as a documented lifecycle project in repo Brettssh/quotetool, Claude project "Dealer Quote Tool in Zoho" | Documents become the source of truth; code rebuildable from them | Brett Price |
| 2026-11-18 | The 2026-11-15 handoff design is treated as prompts for requirements sessions, not as approved requirements | Every rule must be confirmed by Brett before it is written | Brett Price |
| 2026-11-18 | Architecture direction: security through Zoho; Deluge inside Zoho wherever possible; Zoho Catalyst (any language) only when a process must run outside Zoho apps. Replaces the handoff's "Deluge only, no outside server" proposal | Keep one security model (Zoho); Catalyst covers what Deluge cannot | Brett Price |
| 2026-11-24 | Scope approved as docs/01 SCOPE-01 to SCOPE-26 (scope session 1) | Fixes what the product covers before requirements sessions | Brett Price |
| 2026-11-24 | A job can have a builder contract, a homeowner contract, or both; jobs with no builder are in scope | Real job mix is builder-only, homeowner-only, or both | Brett Price |
| 2026-11-24 | Vendor catalog feeds are in scope as phase 2; D-Tools retired for proposals after phase 1 and fully once feeds are live | D-Tools is still needed for vendor catalog updates until feeds replace it | Brett Price |
| 2026-11-24 | Configurators: Zoho Creator vs CRM guided selling deferred to design | Needs a read-only check of CRM capability first | Brett Price |
| 2026-11-24 | Architecture rule 4: nothing hard-coded; all parameters and setup in editable tables; environment variables only for access tokens and secrets | Changes without code releases | Brett Price |
| 2026-11-24 | Do not merge with myPlan. Quote tool owns quoting, change orders, Deal as contract, draws, billing, reports, vendor feeds; myPlan owns material planning, POs, receiving, kitting/Staging, pickup/delivery, leftovers, van stock | myPlan already built and tested the materials side and excludes quotes and billing | Brett Price |
| 2026-11-24 | The material handoff to myPlan is the only link between the products; which record carries it (Sales Order, own job record, or Deal + Job) is an open design decision (SCOPE-26); billing comes only from the Deal's draws | Concern over Zoho Sales Order guard rails and limits; needs investigation before deciding | Brett Price |
| 2026-11-24 | One item catalog in Zoho Books / Inventory shared by both products; items matched by exact SKU / item_id only | Avoid two catalogs; matches myPlan REQ-ACC-008 | Brett Price |
