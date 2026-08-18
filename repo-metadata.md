# Repository About text and topics

The intended **About** blurb and **topics** for each Eventa repository. GitHub
stores these in settings rather than in a file, so this is the reviewable copy —
apply it in the UI (⚙️ beside **About**) or with `gh repo edit`.

Descriptions are kept under ~120 characters so they are not truncated in
repository lists and search results.

---

### eventa-web

> Attendee portal, public event pages and organizer console for Eventa. React 19, Vite and Tailwind v4.

`react` · `typescript` · `vite` · `tailwindcss` · `react-router` · `event-management`

---

### eventa-api

> Eventa's backend — all business rules, the money path, and the only owner of the database schema.

`nestjs` · `typescript` · `postgresql` · `drizzle-orm` · `stripe` · `multi-tenant` · `rest-api`

---

### eventa-relay

> Publishes Eventa's transactional outbox to RabbitMQ. One table, one job, one replica.

`nestjs` · `rabbitmq` · `transactional-outbox` · `postgresql` · `event-driven`

---

### eventa-worker

> Eventa's async side effects — email, calendar sync, audit trail, and scheduled domain jobs.

`nestjs` · `rabbitmq` · `worker` · `email` · `event-driven` · `cron`

---

### eventa-docs

> SDLC documentation for Eventa — requirements, architecture, data model and the development guide.

`documentation` · `architecture` · `adr` · `sdlc` · `c4-model`

---

### eventa-ui-kit

> Static HTML and Tailwind UI kit — the visual source of truth that eventa-web ports 1:1.

`html` · `tailwindcss` · `ui-kit` · `design-system` · `prototype`

---

### eventa-infra

> Terraform, Helm and Argo CD for deploying Eventa.

`terraform` · `helm` · `argocd` · `kubernetes` · `infrastructure-as-code`

---

## Suggested repository settings

Consistent across all repos:

| Setting | Value | Why |
| --- | --- | --- |
| Default branch | `main` | |
| Merge button | **Squash only** | One commit per change keeps `main` readable |
| Auto-delete head branches | On | |
| Branch protection on `main` | Require PR + green CI | |
| Wikis / Projects | Off | Documentation lives in `eventa-docs`, one home only |
| Issues | On, except `eventa-ui-kit` | The kit is a frozen visual reference |

`eventa-api` additionally: protect `src/db/migrations/` with a CODEOWNERS rule —
it is the one directory where a mistake is not revertible by a deploy.
