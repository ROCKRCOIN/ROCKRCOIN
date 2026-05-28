# David Clancy

**Founder & Solo Architect — ROCKRLite**

Building **ROCKRLite**: an **AI-native** live-experience creation and auction platform on the custom **ROCKRCOIN (RKS)** blockchain. The platform removes upfront cost, legal risk, and financial risk from experience creators ("Creators") by handling the full lifecycle — creation, auction, settlement — on-chain, for every genre and type of live experience: Education, The Arts, Community, Sport, High Street Retail and Health.

**AI is woven through the platform via a pluggable factory architecture**, not bolted on — scoping ROCKRCOIN Protocol Issuance, Creator's structural inputs, venue requirements, production-scale classification, frequency shape, content enhancement, entity extraction, and ID validation — every provider swappable behind a clean interface (`IDataService`, ORCID, SerpApi/Google Scholar). The roadmap extends this into marketing automation and a full **AI-driven live tutorial course** experience: automated **course-material generation**, learner **personalisation**, and **assessment** — all delivered inside the same capsule-based architecture, with AI providers remaining pluggable per ROCKR instance.

---

## Scale

Current `main`, post Phase 0 + Phase 1 of the multi-agent build:

**~69,000 lines of application code across 939 files**

| Layer | Count |
|---|---|
| React components | 231 |
| Custom hooks | 72 |
| Pluggable services | 57 |
| Utilities | 44 |

---

## Architecture

The 9 production routes undersell the surface area. Each route is a step in a carousel composed of multiple **capsules**, and each capsule carries its own bottom sheets, validation, AI integration, and i18n. Flat route count, deep component tree — **231 React components** implementing a reusable **9-step carousel + capsule pattern**.

The hard part is built once. Profile creation/switching, the ROCKRCOIN auction module, and accounts all replicate this proven structure, so each new app surface ships at a fraction of the original cost. **Built to accelerate with a team.**

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
