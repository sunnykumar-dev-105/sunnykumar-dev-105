# Selected Engineering Work

This page provides context behind projects mentioned on [my GitHub profile](./README.md). It distinguishes **implemented or validated work** from **architecture, research, and ongoing development**. Private employer code, sensitive data, and undocumented internal contracts are not published here.

## 1. Healthcare workflow integration — professional work (private source)

**Problem:** Turn workflows in a session-based clinical software environment into dependable services while minimizing the risk of inaccurate patient identification, stale authentication, and unsafe diagnostics.

**My engineering contribution**
- Worked with Python API services and asynchronous application behavior.
- Used browser-authenticated sessions and application-generated requests to interact with workflows more reliably than repeated visual clicking.
- Implemented and validated defensive parsing of XML-based responses, patient-matching rules, and encounter-history retrieval.
- Investigated failures using count-based, privacy-preserving diagnostics and controlled comparisons with observed application behavior.
- Worked on session readiness, concurrency control, containerized deployment, health checks, and regression-testing discipline.

**What was verified:** Patient-search and encounter-history read workflows were live validated. Reliability fixes were checked against failing and previously working scenarios.

**Work in progress / excluded from claims:** Expanded session-broker resilience and appointment mutation workflows should not be represented as fully deployed production capabilities.

**What this demonstrates:** State management, integration research, safe API boundaries, debugging methodology, and reliability engineering in a sensitive domain.

## 2. WOVO LOVE — privacy-first relationship product (application source private)

**Problem:** Model intentional introductions, temporary actions, privacy-safe discovery, and accessible mobile experiences without relying on an endless swipe-feed design.

**My engineering contribution**
- React Native, Expo, TypeScript mobile-product work and reusable screen-state handling.
- Supabase/PostgreSQL-backed architecture, authentication boundaries, and product-rule modeling.
- Implemented and validated aspects of intro lifecycle behavior, Pass/Undo handling, privacy-aware presentation, responsive layouts, and accessibility.
- Emphasized server-authoritative state, automated contract checks, device QA, and controlled Git changes.
- Participated in database-backed safety architecture and transactional/idempotency design reviews.

**Status note:** Important discovery, presentation, and contract work reached validated milestones. The complete moderation, messaging, and interaction ecosystem was **not** all production-launched.

**Related public artifact:** [Landing-page prototype](https://github.com/sunnykumar-dev-105/wovo-love-landing) — separate from the private mobile product.

## 3. Sustainability and environmental technology

I have worked on research-led software projects addressing resource monitoring, sustainability education, and structured ESG/BRSR-related information.

- **Postal sustainability:** Flutter-based applications and business-reporting explorations for electricity, water, fuel, and environmental metrics. [ESG app](https://github.com/sunny1921/esg-app) · [BRSR/mobile project collection](https://github.com/sunny1921/mobile_computing)
- **Research publication:** [*From Theory to Action: ESG App for Sustainable Education*, IEEE ICCCNT 2024](https://doi.org/10.1109/ICCCNT61001.2024.10725998).
- **Recognition:** National Winner, Smart India Hackathon **2023** and **2024**.

These public repositories are hosted under an earlier account. The linked code reflects historical projects, not necessarily my current preferred architecture or tooling.

## 4. FHAIDA CRM — real-estate operations

Worked on CRM functionality for leads, properties, tasks, and related operational workflows using a Flutter-centered stack.

**Public reference:** [FHAIDA CRM](https://github.com/sunny1921/FHaiDA_CRM). Product documentation and source belong to an earlier project checkpoint; they are not a claim of a current hosted production system.

## 5. SKY ONE — environmental learning game

Created an environmental-awareness learning game. Its code and playable build are **not yet published on GitHub**. Screenshots, gameplay details, and a verified source release can be added if available and cleared for public sharing.

---

### Engineering approach

1. **Understand:** Study the business workflow and identify the true constraints.
2. **Design:** Define authority, data contracts, failure handling, and measurable acceptance criteria.
3. **Implement:** Choose the simplest reliable technology that fits the problem.
4. **Validate:** Test failure modes and behavior, not only successful paths.
5. **Improve:** Use observed evidence, careful changes, and regression protection.

For professional enquiries: **[sunny.builds.dev@gmail.com](mailto:sunny.builds.dev@gmail.com)**.
