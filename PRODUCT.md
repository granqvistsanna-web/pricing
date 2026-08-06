# Product

<!-- impeccable:product-schema 1 -->

## Platform

web

## Users

A small consulting studio — the owner plus a few colleagues — pricing their own client work. Each person quotes from their own browser; there is no shared account or team workspace. Users know their own rate card and cost base; they are not learning what a margin is, they are checking one.

## Product Purpose

Turn hours into a defensible price, and tell the user whether that price is worth taking. Two moments matter:

1. **Writing the proposal.** Considered, offline, at a desk. The output is text pasted into a document or email — the "Copy for client" and "Copy internal" outputs are the deliverable, not the screen.
2. **Sanity-checking a deal.** A price is roughly agreed; the user checks it against their margin floor before committing.

Success is a number the user can defend in a client conversation and a margin verdict they trust enough to say no on.

## Positioning

Priced for a Swedish consultancy specifically: SEK base, moms, USD as the second currency for foreign clients, and an admin-percentage model for the unbilled hours around the billed ones. Generic pricing calculators model none of this. The margin floor is the point of the tool — the price is arithmetic, the verdict is the product.

## Operating Context

- Quoting happens alongside a proposal document or email; the app's job ends at the clipboard.
- Rate cards differ per engagement type — presets exist so "standard" and "friends & family" are one selection apart.
- Foreign-client work is quoted in USD against a live FX rate, with a manual override for when a contract fixes the rate.
- Team members pass rate cards around by exporting and importing JSON. Nothing syncs.

## Capabilities and Constraints

**Confirmed capabilities**

- Three quote modes: hourly, project (with a risk buffer), retainer (months × monthly hours, with a retainer discount).
- Two directions: forward (hours → price) and from-budget (client's stated number → what fits inside it, ex or ink moms).
- Rate card of labelled hourly lines, each with its own currency.
- Fees and defaults: startup fee, admin %, default risk %, moms %.
- Margin floor: internal cost per hour and target margin %, producing a pass/warn/fail verdict on every quote.
- Saved quotes (save, duplicate, delete), presets for the settings block, JSON export/import, and an export nudge tied to unsaved changes.
- Live USD→SEK rate from `api.frankfurter.dev`, with a manual override.
- A three-step first-run setup that collects rates, fees, and cost basis before the calculator is usable.
- Two clipboard outputs: a client-facing breakdown and an internal one that includes cost and margin.

**Durable constraints**

- **The Swedish tax and currency model is fixed.** SEK is the base; fees and internal cost are stated in SEK with no second base. Moms is the VAT model. USD is the one foreign currency. This is not a generic multi-currency tool and must not be generalised into one.
- Data lives in this browser's localStorage under `pricing.v2`. No accounts, no server, no sync. The FX call is the only network request.
- The repository is public; committed defaults are zeroed so no real rates or costs ship in the file.

**Open decisions**

- A shared team rate card is *not* being built. Export/import is the sharing mechanism for now. Recorded so later work does not assume browser-only storage is permanent, and does not quietly build sync either.
- Stack is open: the current single `index.html` with no build step is convenience, not doctrine. A build step or framework is permitted if the work justifies it. Do not add tooling without a reason.
- Currency handling for team members quoting outside Sweden is undefined.

## Brand Commitments

None established. The current visual treatment is an unbriefed default, not an identity the user has committed to.

## Evidence on Hand

- `index.html` — the entire application, including engine, UI, and a self-test block.
- No customers, testimonials, benchmarks, pricing claims, or case studies exist for this tool. It is an internal instrument, not a marketed product. Future work must not invent social proof, usage numbers, or third-party endorsement for it.
- Real rate and cost figures live only in users' browsers and must never be committed.

## Product Principles

1. **The verdict outranks the arithmetic.** Anyone can multiply hours by a rate. The margin check is the reason to open this instead of a spreadsheet, and it should never be something the user has to go looking for.
2. **Design for the desk, not the call.** These users are composing a proposal, not improvising under pressure. Deliberation, comparison, and legibility beat speed.
3. **The clipboard is the output.** The screen is a workbench; what leaves the tool is text. Both copy formats are first-class product surfaces, not afterthoughts.
4. **Swedish specificity is the moat.** Moms, admin percentage, SEK base. Every pull toward generality makes the tool worse at the only job it has.
5. **The user's numbers are theirs.** Local storage, public-safe defaults, and an export path that works. No mechanism that quietly moves a rate card off the machine.

## Accessibility & Inclusion

No product-specific requirement established beyond ordinary standards. Note the domain reality: this is a dense numeric interface used for money decisions, so tabular figures, unambiguous currency labelling, and a margin verdict that does not rely on colour alone are functional requirements, not decoration.
