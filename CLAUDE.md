# Zoho Quote Tool — working rules for Claude

Product: SmartShield Homes' quote and contract tool on Zoho, replacing D-Tools.
Owner and decision-maker: Brett Price. Brett is not a coder; he understands architecture and makes every product decision. Never improvise past him.

The documents are the source of truth. The code is disposable and must be rebuildable from the documents alone.

## Systems
- Zoho CRM (Quotes, Deals, Products, Price Books, custom modules)
- Zoho Books / Zoho Inventory (catalog master, invoices, purchase orders, receipts, stock)
- Zoho Sign, Zoho Writer, Zoho Creator, Zoho Analytics (all in Zoho One)
- D-Tools: source of the catalog export only; being retired

Which of these are in scope is decided in `docs/01` (scope session), not here.

## Start of every chat
1. Read this file, then the latest `claude/status-*.md` in the Claude project "Dealer Quote Tool in Zoho" and the roadmap whiteboard linked in it.
2. Before doing anything: say what will be done, where it fits, and why. Show the destination up front.
3. No live change to any system (Zoho CRM, Books, Inventory, Sign, Writer, Creator, Analytics, Catalyst, or any other) without Brett's explicit OK. Read-only checks are allowed.

## Lifecycle order (never skip ahead)
1. Scope → `docs/01`.
2. Requirements sessions, one functional area each. Earlier designs (including the handoff doc in the Claude project) are prompts only: list proposed rules numbered; Brett confirms / changes / strikes each. Write only what Brett decided, with IDs `REQ-AREA-NNN`, plus decision-log rows.
3. Acceptance tests: given / when / then, each citing its REQ IDs; every requirement has at least one; coverage checked by script.
4. Gap list (only when code already exists): read-only, Pass / Gap / Cannot tell, grouped into sized work packages.
5. Design documents (data model, integrations, service interface, screens, architecture, security), written and approved before any build. Existing Zoho field names may be checked read-only and proposed for reuse; Brett decides.
6. Build: code in this repo only, from the documents, with automated tests passing; versioned releases.
7. Release: Brett deploys; verified live; `control/release-log.md` updated.

## Intake
When Brett reports a bug or asks for something: stop, write a backlog item with acceptance criteria in `control/backlog.md`, show it, and wait for approval before changing any document or code. A rule nobody has decided is a design question for Brett, never a patch.

## Phrases
- "Hotfix": the only fast path. Backlog row, release-log row and document update follow immediately.
- "Log it": backlog only; build nothing.
- "Knowledge base question: …": draft one article from approved rules only, as a pull request.
- "Roadmap" / "where are we?": update the roadmap whiteboard and answer from it.

## Pull requests
- Code, documents and tests live only in this repo and reach Brett as pull requests. Never paste code into chat as the deliverable; never build from zips or files on Brett's laptop.
- Open every pull request against `main`, one at a time. Never stack pull requests.
- Before adding a commit to a pull request, check it is still open; if merged, open a new one.
- Record decisions as `control/decision-log.md` rows in the same pull request. Specs are rewritten, never appended.
- After a merge, confirm `main` holds what was expected.
- Tell Brett plainly what the pull request contains, that merging means approval, and that nothing live changes.

## Architecture rules
Not decided yet. Set in `docs/08` once Brett approves the architecture. (Earlier handoff proposed: everything in Deluge inside Zoho, no outside server or JavaScript; to be confirmed.)

## Brand
Outputs use Arial and SmartShield brand blue #2F4988.

## Credentials
Never put credentials in the repo, documents or chat; never read, repeat or use them even when a tool shows them.

## Style with Brett
Numbered lists; full names for people and accounts; plain words; short answers; one clear recommendation when there are options.
