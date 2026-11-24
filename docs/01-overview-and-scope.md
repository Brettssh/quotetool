# 01 · Overview and scope

Status: In review · Owner: Brett Price · Decided in scope session 1, 2026-11-24

## Product
SCOPE-01. A quote and contract tool inside Zoho that replaces D-Tools for proposals. It covers quote → contract → billing. Materials planning and handling belong to the separate product myPlan (see "Boundary with myPlan").

## Users
SCOPE-02. SmartShield Homes staff only: sales/design, project managers, bookkeeper, and others who quote or bill. Each user signs in with their own Zoho account.
SCOPE-03. Expected user count: 5 to 7.

## Customers and contracts
SCOPE-04. Contract customers are builders and homeowners. A job (house) can have a builder contract only, a homeowner contract only, or both.
SCOPE-05. Jobs with no builder (for example, a direct homeowner retrofit or service work) are in scope and have one homeowner contract.

## In scope
SCOPE-06. **Quoting:** catalog, price books per builder or tier, accessories and labor added automatically, base quotes with revisions, change orders, configurators (lighting first), proposals e-signed in Zoho Sign.
SCOPE-07. **Contract and billing, including change orders:** the Deal is the contract; draw schedule; invoices created from the Deal's draws; each accepted change order adds to the contract value and carries its own draws; contract summary for the customer.
SCOPE-08. **Material handoff to myPlan:** when a contract is accepted, the quote tool hands myPlan the job's material demand (item, quantity, room, job date); each accepted change order updates it. Which Zoho record carries the handoff is open (SCOPE-26).
SCOPE-09. **Reports:** in scope; contents defined in their own requirements session.
SCOPE-10. **Vendor catalog feeds:** keeping catalog prices and product data current from vendors without D-Tools. The feeds update the one item catalog in Zoho Books / Inventory. Routes known today:

| Vendor | Route |
|---|---|
| Lutron | Pricing file downloaded from Lutron online (MyProjects) |
| Sony | Spreadsheet |
| Sonos | Spreadsheet |
| Sanus | Spreadsheet |
| ADI | ADI API |
| Silmar | To be decided |
| Amazon | Manual entry |
| Home Depot | Manual entry |

## Boundary with myPlan
myPlan (repository Brettssh/myvan, Claude project "myVan Material Planning") is the material planning product.

SCOPE-11. **The quote tool owns:** quoting, change orders, the Deal as contract, draws, billing, contract reports, vendor catalog feeds.
SCOPE-12. **myPlan owns:** material planning, purchase orders, receiving, kitting and Staging, pickup and delivery, leftovers, van stock.
SCOPE-13. **Handoff:** the material handoff (SCOPE-08) is the only hand-off between the two products; myPlan re-plans when it changes. The record that carries it is open (SCOPE-26).
SCOPE-14. **Billing comes only from the Deal's draws.** The handoff record is never used for billing.
SCOPE-15. **Shared data:** the item catalog in Zoho Books / Inventory is the one master for both products; items are matched by exact SKU / item_id only.

## Systems
SCOPE-16. In scope: Zoho CRM, Zoho Books / Zoho Inventory, Zoho Sign, Zoho Writer, Zoho Analytics, and Zoho Catalyst where Deluge cannot do the job.
SCOPE-17. D-Tools: a one-time export of products, labor hours and accessories; afterwards D-Tools is used only for catalog updates until the vendor catalog feeds replace it.

## Out of scope
SCOPE-18. Everything SCOPE-12 gives to myPlan, including a net BOM by room and kits.
SCOPE-19. Accounting setup in Zoho Books (chart of accounts, tax setup) stays as it is; the tool creates invoices and the handoff record and reads payments only.
SCOPE-20. Other company products stay separate for now: Alarm.com, the Field Reference tool, the lighting design tool.
SCOPE-21. No customer portal: customers receive PDFs and Zoho Sign emails.
SCOPE-22. No crew scheduling or time tracking.

## Delivery
SCOPE-23. Delivered in phases, each usable on its own: (1) quote and contract, including the handoff to myPlan; (2) vendor catalog feeds. D-Tools is retired for proposals after phase 1 (after one real job runs side by side with the old process) and fully once phase 2 is live.

## Deferred and open
SCOPE-24. Configurators in Zoho Creator or CRM guided selling: deferred to design.
SCOPE-25. Silmar catalog route: to be decided.
SCOPE-26. **Which record is the job's source of truth and carries the handoff — open, decided before either product goes further on it.** Options: (1) Zoho Sales Order, as myPlan uses today; (2) a job record owned by the products (CRM or myPlan's job tables), with Sales Orders created downstream only for fulfillment; (3) the CRM Deal plus a Job record read directly by myPlan. Concern raised by Brett: Zoho guard rails and limits on Sales Orders. Next: read-only investigation of Sales Order limits and of how deeply myPlan depends on Sales Orders, then a one-page comparison with a recommendation. The decision is recorded in both repositories.
