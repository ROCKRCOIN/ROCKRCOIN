David Clancy — founder and chief architect of ROCKR, and Principal Investigator of a formal-verification programme carried by two research vehicles: ROCKR Proof Labs Ltd (London) and ROCKR Preuves (Dordogne, France).

The programme proves, by theorem, the half of every transaction that nobody has yet proved — who is entitled to be there, once, as themselves — for a settlement system that binds value to authenticated human presence. Model Zero, a Lean 4 model of that system, states four whole-system theorems: attested transfer; issuance only against authenticated activity; erasure with asset preservation; conservation with halt semantics. Status: 18 of 18 statements proved, core Lean only, Apache 2.0. Nothing is yet proved of running code; the proof boundary is being pushed from model to implementation.

The system the model describes settles ROCKRCOIN (RKS), a digital utility asset issued only against authenticated live activity and held only by verified humans, on an identity-first Cosmos SDK chain. ROCKRLite is the application: an AI-native platform for creating, allocating and settling live experiences of every kind — education, the arts, community, sport, high-street retail, health — with every AI and identity provider pluggable behind a published interface, so that each ROCKR instance chooses its own. Seven published institutional studies (four cities, three banks) show each place with and without the settlement layer.

Working method: AI drafts specifications, proofs and code; the Lean kernel checks every proof regardless of how it was found; a named human rules every design question; per-step provenance notes record which was which.

Repositories: rockr-proof-labs (Model Zero and the verified components) · ROCKRCOIN (the application and whitepaper). Programme: rockrprooflabs.org · rockrpreuves.fr.
| Layer | Count |
|---|---|
| React components | 231 |
| Custom hooks | 72 |
| Pluggable services | 57 |
| Utilities | 44 |

---

## Architecture

The 9 production routes undersell the surface area. Each route is a step in a carousel composed of multiple **capsules**, and each capsule carries its own bottom sheets, validation, AI integration, and i18n. Flat route count, deep component tree — **231 React components** implementing a reusable **9-step carousel + capsule pattern**.

The hard part is built once. Profile creation/switching; the ROCKRCOIN auction module; ROCKRCOIN, RUIMA account balance management; all replicate this proven structure, so each new app surface ships at a fraction of the original cost. **Built to accelerate with a team.**

---

## AI Integration

AI is a first-class, pluggable layer — every provider sits behind a factory interface so it can be swapped per ROCKR instance without touching the calling code.

**Live today**
- Scope ROCKRCOIN Protocol Issuance; the Creator's structural inputs; venue requirements; production-scale classification; frequency shape; content enhancement; entity extraction; ID validation.
- **Identity** — pluggable ID validation (IDV) behind a provider interface.
- **Pluggable data providers** — `IDataService` interface with ORCID and SerpApi (Google Scholar) integrations already wired in.
- **Production-hardened** — dual-source field locking, profile deduplication, and duplicate-call prevention.

**Planned**
- **Marketing automation** — AI-driven promotion and reach for ROCKR live auctions.
- **AI-driven live-experience-centred courses / journeys.**

All of the above remains provider-agnostic: the factory pattern means a ROCKR instance can plug in its own AI backend.

---

## Engineering Discipline (Enforced)

- **Strict separation of concerns** — business logic lives in **hooks only**; components never call services directly.
- **Size budgets** — components ≤200 lines · hooks ≤250 · services ≤200. A component creeping past budget signals a refactor through context, never an inline exception.
- **Pluggable services via factory pattern** — IDV, AI data sources, and fiat escrow all swap behind interfaces.
- **No cross-step coupling** — step dependencies flow through shared context or explicit props, never direct imports.
- **Multi-instance open-source model** — organisations run their own ROCKR instances with pluggable services.
- **GDPR / wallet independence** — profile deletion erases personal data but never touches wallet contents.
- **Production-first, no mocks** — golden-path E2E gate before every commit.

---

## Stack

**Frontend** React · Next.js · TypeScript · Tailwind · shadcn/radix
**Backend & infra** Supabase (auth + database) · Vercel
**Blockchain** Custom ROCKRCOIN blockchain
**AI** Pluggable provider layer (factory pattern) · `IDataService` · ORCID · SerpApi / Google Scholar
**Identity** Pluggable IDV (Shufti Pro)
**Internationalisation** EN / FR / ES
**Testing** Playwright E2E

---

*ROCKRCOIN — The Rainbow Digital Utility Asset.*
