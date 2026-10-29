# Portfolio — Masoud

Repository review date: 2026-10-29. These summaries describe source and documentation inspected at that date. They are not independent security, deployment, or performance certifications.

## PayOrder — public treasury prototype

**Problem:** Preparing Persian payment and receipt documents with mixed cash and cheque commitments.

**Implementation:** A standalone HTML/CSS/JavaScript application with Jalali date utilities, installment scheduling, document timelines, print layouts, local archives, and JSON backup exchange. PDF.js and Tesseract.js integrations are included for document input.

**Evidence:** [Source](https://github.com/msddipr1469/PayOrder/blob/main/index.html) and [demo instructions](https://github.com/msddipr1469/PayOrder#readme). Functions include `renderScheduleInputs`, `runRecalculate`, `saveCurrentOrder`, and `exportBackup`.

**Limits:** Browser localStorage retains at most 80 records on save. There is no server authentication or shared database. Extraction accuracy and calculations require separate validation. Use synthetic records for a portfolio demo.

## Benayar family — construction and project finance

**Problem:** Comparing land and construction scenarios and organizing project financial information through a Persian interface.

**Implementation:** Next.js/React applications with domain calculations, project workspaces, reports, membership controls, and backup workflows. CT-Benayar contains the broader pilot application; banayar is a related implementation, not an additional independent customer delivery.

**Private source evidence:** In CT-Benayar, `lib/domain/construction-estimate.ts`, `lib/domain/land-assessment.ts`, `lib/domain/project-finance.ts`, project-member APIs, and domain/browser tests. In banayar, `components/workspace/` and `lib/`.

**Supporting component:** banayar-core contains a Cloudflare Worker and administrative interface for the Benayar licensing workflow, with Ed25519 integration and QR request scanning. It is part of this product family.

**Limits:** Scenario results are not official valuations or permits. Current live deployment, access policies, migrations, and restore behavior were not independently tested in this portfolio review.

## Payment.M — internal treasury application

**Problem:** Organizing cash and cheque documents, invoices, archives, and payment follow-up in a Persian business workflow.

**Implementation:** Next.js/TypeScript source with Jalali validation, treasury rules, PDF invoice handling, print reports, archive operations, and server-side administration/archive modules.

**Private source evidence:** `lib/treasury.ts`, `lib/invoice.ts`, `lib/shared/adminStore.ts`, `lib/shared/archiveStore.ts`, `app/api/admin/route.ts`, `app/api/archive/route.ts`, and tests.

**Limits:** The README contains both newer network-operation notes and an older statement that server authentication/database support is absent. Source modules show server functionality, but the documentation needs reconciliation before making deployment claims. No operational records, host details, or credentials are included here.

**Independent home edition:** The private [generic-local branch](https://github.com/msddipr1469/Payment.M/tree/generic-local) has a Windows source installer, separate business data, local startup, and a fixed update branch. On 2026-10-29 its missing backup API was included in Git, 6 home-edition tests passed, TypeScript/build passed, and an isolated launch returned HTTP 200. The first installation requires internet; the actual home computer was not tested.

## ProductCompare — catalogue and product comparison

**Problem:** Reviewing catalogue information and comparing product options with traceable sources.

**Implementation:** Python/Django and PostgreSQL with a Persian RTL JavaScript interface, PDF/XLSX/ZIP ingestion, background processing, local English OCR, reviewable source references, and spreadsheet reports.

**Private source:** [ProductCompare](https://github.com/msddipr1469/ProductCompare). Includes the latest local application improvements and an installer for a fresh Windows home installation. Business databases, documents, credentials, and runtime files are excluded.

**Validation on 2026-10-29:** 32 tests passed on isolated PostgreSQL. A new empty database was initialized, migrations applied, and HTTP health and empty catalogue responses verified. Python/PostgreSQL internet downloads and installation on the actual home PC were not executed.

**Limits:** OCR and extracted specifications require human review. Comparison scores use recorded inputs and are not independent product-quality certification. The app is intended for local use.

## OrderBridge — purchase-request workflow

**Problem:** Coordinating purchase requests and staff/customer communication across business contexts.

**Implementation:** Next.js/React/TypeScript with normalized SQL migrations, PostgreSQL/PGlite support, scoped roles, catalog and order modules, conversations, spreadsheet exchange, background jobs, and backup modules.

**Private source evidence:** `server/orders.mjs`, `server/roles.mjs`, `server/excel.mjs`, `server/jobs.mjs`, `server/backup.mjs`, `server/migrations/`, and deployment documentation.

**Limits:** The project describes an office pilot and a commercial deployment path. Load, accounting acceptance, external deployment, and independent security validation remain environment-specific checks.

## TradeMsd1469 — AI chart-review prototype

**Problem:** Exploring chart images and recording trading observations in a Persian interface.

**Implementation:** Next.js/React/TypeScript, image input for multiple timeframes, a server-side Gemini API integration, chart annotation components, position-sizing UI, and a journal stored in localStorage.

**Private source evidence:** `app/api/analyze/route.ts`, `lib/gemini.ts`, `components/ChartAnnotationStudio.tsx`, `components/PositionSizeCalculator.tsx`, and `app/page.tsx`.

**Limits:** The analysis route contains hard-coded fallback responses. A successful HTTP response alone does not prove a live model analysis or current market data. Model access, output validity, and calculation accuracy require separate verification. This is an educational software prototype; no profitability or trading-performance claim is made.

## What this portfolio supports

The strongest demonstrated direction is Persian business application development: domain-specific interfaces, financial document workflows, data storage, reporting, and API integration. Several repositories contain test suites; their presence is evidence of testing work, not proof that all checks pass today.

Potential next projects include messaging bots and data pipelines. They are not counted as delivered work in this portfolio.

[Back to profile](README.md)
