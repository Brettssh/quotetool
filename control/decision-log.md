# Decision log

Append-only. One row per decision. Never edit or delete a row; record a reversal as a new row.

| Date | Decision | Why | Who |
|---|---|---|---|
| 2026-11-18 | Start the Zoho Quote Tool as a documented lifecycle project in repo Brettssh/quotetool, Claude project "Dealer Quote Tool in Zoho" | Documents become the source of truth; code rebuildable from them | Brett Price |
| 2026-11-18 | The 2026-11-15 handoff design is treated as prompts for requirements sessions, not as approved requirements | Every rule must be confirmed by Brett before it is written | Brett Price |
| 2026-11-18 | Architecture direction: security through Zoho; Deluge inside Zoho wherever possible; Zoho Catalyst (any language) only when a process must run outside Zoho apps. Replaces the handoff's "Deluge only, no outside server" proposal | Keep one security model (Zoho); Catalyst covers what Deluge cannot | Brett Price |
