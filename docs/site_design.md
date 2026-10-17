# USQCD Genesis Site Design

## Document status

- **Project:** Lattice QCD at the Intelligence Frontier: a USQCD Genesis Mission
- **Repository:** `usqcd/usqcd-genesis`
- **Status:** Working design for discussion
- **Created:** 2026-10-17
- **Audience:** Project leadership, site maintainers, collaboration administrators, and developers

This document is the initial design and operating plan for the USQCD Genesis
website and collaboration portal. It records confirmed decisions separately from
proposals and open questions. It is intended to evolve through pull requests as
the collaboration establishes its governance and reporting processes.

The funded proposal is the authoritative source for the scientific scope,
milestones, metrics, deliverables, participating personnel, and required DOE
reporting. Proposal material must be reviewed for public release before it is
quoted or reproduced on the public site.

## 1. Vision

The site should present the project as a high-profile, technically ambitious DOE
Genesis Mission collaboration while also giving the collaboration practical
infrastructure for managing its work.

It has two related purposes:

1. **Public presence.** Explain the strong interaction, lattice QCD, the role of
   artificial intelligence, and the project's goals in clear language; showcase
   papers, talks, software, data, people, institutions, and progress.
2. **Collaboration operations.** Provide authenticated tools for membership,
   preprint numbers, publication tracking, milestones, metrics, reporting,
   announcements, and administrative workflows.

The working public identity is:

> **Lattice QCD at the Intelligence Frontier**  
> A USQCD Genesis Mission

The public experience should be visually distinctive and scientifically
credible. The operational experience should be simple enough to remain useful
for the full lifetime of the award.

## 2. Confirmed decisions

The following decisions have already been made:

- The source repository is the public GitHub repository
  `usqcd/usqcd-genesis` under the USQCD organization.
- GitHub will hold source code, database migrations, public content, and project
  documentation. Secrets and private collaboration records will never be stored
  in the repository.
- The proposed production frontend platform is Vercel Pro.
- The initial managed backend is the Supabase Free plan, with a future option to
  upgrade or migrate to a self-hosted institutional instance.
- The collaboration will use a paid Slack workspace for routine communication.
- The supplied USQCD Genesis logo will be used as the primary visual brand.
- The site will have both a public-facing section and an authenticated
  collaboration section.
- The authenticated section will eventually support preprint numbers, automated
  publication discovery, member administration, milestone and metric tracking,
  report preparation, and collaboration messaging.
- Public pages must remain usable if the backend is temporarily unavailable.

## 3. Design principles

### 3.1 Public first

The public site is a lasting scientific record, not a decorative wrapper around
an administrative portal. Its principal pages should be pre-rendered or cached
so that they remain fast and available during a Supabase interruption.

### 3.2 One authoritative home for each kind of information

- GitHub: source, public content, technical decisions, and change history
- Supabase: structured collaboration records and permissions
- Slack: discussion, alerts, and routine announcements
- Institutional document service: working documents, meeting materials, and
  restricted files
- OSTI/PAMS and related DOE services: required federal submissions

Information may be summarized or linked elsewhere, but should not acquire two
conflicting authoritative versions.

### 3.3 Reporting by construction

Outputs and activities should be captured when they occur, together with the
award, milestone, workstream, people, institutions, dates, and evidence needed
for later reporting. Annual reporting should be an export and review process,
not a reconstruction exercise.

### 3.4 Humans approve consequential automation

Automated systems may discover publications, suggest member matches, prepare
messages, and flag deadlines. A responsible collaborator must approve public
records, broad Slack announcements, roster changes, and formal report content.

### 3.5 Portability and graceful degradation

Core data will use ordinary PostgreSQL tables and versioned migrations. The
architecture must permit migration away from Supabase or Vercel. Public pages
must degrade gracefully when authenticated services are unavailable.

### 3.6 Minimum necessary private data

The project will collect only information needed to operate the collaboration
and report its work. Public profiles, photographs, and contact details require a
clear publication status and, where appropriate, consent.

## 4. Audiences

### Public audiences

- Scientists in nuclear and particle physics
- Researchers in artificial intelligence and high-performance computing
- DOE program staff and reviewers
- Prospective collaborators and early-career researchers
- Journalists, policymakers, students, and interested members of the public

### Authenticated audiences

- Collaboration members
- Workstream and technical leads
- Publication and preprint coordinators
- Project leadership
- Site and database administrators

The public writing should assume scientific curiosity but not prior expertise in
lattice gauge theory. Authenticated tools may use the terminology of the funded
project and its reporting requirements.

## 5. Information architecture

### 5.1 Public site

The proposed primary navigation is:

1. **Home**
   - Mission statement and primary visual
   - Concise explanation of the project
   - Featured outputs, news, and progress
   - Clear routes into the science, people, and results
2. **The Science**
   - The strong interaction and quantum chromodynamics
   - Why lattice QCD is needed
   - How computation turns the theory into predictions
   - A glossary and progressively deeper explanations
3. **The Intelligence Frontier**
   - The scientific and computational goals of the funded work
   - How AI and lattice QCD reinforce one another
   - Research themes or workstreams derived from the proposal
   - Anticipated impact without overstating uncompleted work
4. **People**
   - Project leadership
   - Participating scientists, with approved photographs and biographies
   - Early-career researchers
   - Participating universities, national laboratories, and NVIDIA
5. **Results**
   - Papers and preprints
   - Talks and presentations
   - Software releases
   - Datasets and other research products
   - Filters by year, workstream, institution, and output type
6. **News**
   - Project announcements
   - Research highlights
   - Events and major releases
7. **About**
   - Project overview and leadership structure
   - Participating institutions
   - DOE Genesis Mission context
   - Contact information and required acknowledgments
8. **Member sign-in**
   - Entry to the authenticated collaboration portal

Claims such as the number of Phase 2 awards must be verified against a current
DOE source before publication.

### 5.2 Authenticated collaboration portal

The portal is expected to grow in phases. Its eventual navigation is:

1. **Dashboard**
   - Relevant deadlines, outstanding actions, and recent activity
   - Progress summaries appropriate to the user's role
2. **Preprints**
   - Request and issue a unique preprint number
   - Reserve, complete, amend, or withdraw a record without reusing a number
   - Link the record to arXiv, INSPIRE, DOI, authors, workstreams, and DOE status
3. **Publications and outputs**
   - Review automatically discovered candidates
   - Add or correct records manually
   - Track acknowledgment, accepted manuscript, OSTI, data, and software status
4. **Milestones and metrics**
   - View definitions, owners, due dates, targets, evidence, and current status
   - Record updates with an audit trail
   - Preserve reporting-period snapshots
5. **People and institutions**
   - Maintain membership, roles, workstreams, affiliations, ORCID identifiers,
     profile visibility, and photograph permissions
6. **Reporting**
   - Assemble period-specific publications, products, participants, progress,
     milestone evidence, risks, and narrative inputs
   - Export structured data and human-readable report drafts
7. **Communications**
   - Draft and preview announcements
   - Post approved messages to appropriate Slack channels
   - Retain a searchable record of system-generated announcements
8. **Documents and links**
   - Curated links to the authoritative institutional document store, calendar,
     award documents, policies, templates, and meeting records
9. **Administration**
   - Roles, permissions, integration health, audit records, imports, and settings

## 6. Visual and content direction

### 6.1 Brand

The supplied USQCD Genesis logo is the starting point for the visual identity.
The site should use a clean vector master and maintain approved horizontal,
stacked, dark-background, light-background, monochrome, and small-icon variants.

The brand system should draw from the logo's relationship between lattice QCD,
neural networks, and the Genesis mark. Supporting graphics may show structure
emerging from fields, networks, or lattice geometry, but should not compete with
the logo or imply scientific results that do not exist.

### 6.2 Tone

- Confident and precise, without promotional exaggeration
- Accessible to non-specialists without diluting the science
- Focused on people, scientific questions, and concrete outputs
- Clear about work in progress versus achieved results

### 6.3 Photography

The people page should use consistent portrait treatment while respecting the
varied quality of source photographs. Each photograph record should include
credit, alt text, publication permission, source, and an optional expiration or
replacement note. The layout must work when a member has no photograph.

### 6.4 Accessibility and responsive behavior

The target is WCAG 2.2 AA. Keyboard navigation, visible focus, meaningful heading
structure, sufficient color contrast, reduced-motion support, descriptive link
text, alternative text, and accessible charts are launch requirements. The site
must work well on phones, tablets, laptops, and wide displays.

## 7. Proposed technical architecture

The initial implementation is expected to use:

- **Application:** Next.js with TypeScript
- **Hosting and deployment:** Vercel Pro
- **Database:** PostgreSQL supplied by Supabase
- **Authentication:** Supabase Auth, initially using GitHub OAuth
- **Authorization:** PostgreSQL grants and Row Level Security, backed by explicit
  collaboration roles in the database
- **File storage:** Supabase Storage for profile photographs and application
  records that do not belong in the institutional document system
- **Scheduling:** Supabase Cron or Vercel Cron, with one scheduler designated as
  authoritative for each job
- **Communication integration:** A narrowly scoped Slack app or incoming webhook
- **Public content:** Version-controlled Markdown or MDX where practical
- **Styling and component system:** To be selected after a visual prototype
- **Testing:** Unit, integration, accessibility, and browser-level tests

These technology choices remain subject to a short implementation review before
application scaffolding begins.

### 7.1 Logical structure

```text
GitHub repository
  |-- application source
  |-- public content
  |-- database migrations
  |-- tests and documentation
  `-- deployment configuration
          |
          v
Vercel
  |-- public Next.js site
  |-- authenticated Next.js portal
  |-- server-only API operations
  `-- preview deployments
          |
          v
Supabase
  |-- PostgreSQL data
  |-- authentication
  |-- row-level authorization
  |-- selected file storage
  `-- scheduled ingestion or maintenance jobs
          |
          +--> arXiv and INSPIRE-HEP
          +--> Slack
          +--> ORCID and ROR
          `--> reporting exports and DOE submission tracking
```

### 7.2 Availability boundary

Public explanatory content and the public shells of output pages should be built
or cached by Vercel. A Supabase outage may make newly changed dynamic information
temporarily stale, but should not remove the principal public pages.

The authenticated portal may display a clear maintenance state when Supabase is
unavailable. Ingestion jobs must remember the last successful checkpoint and
backfill missed periods after service is restored.

## 8. Authentication and authorization

GitHub sign-in establishes identity; it does not by itself grant access. The
application will authorize a signed-in person by matching the verified identity
to an active collaboration member record.

Proposed roles are:

- **Member:** Read internal information and maintain permitted portions of their
  own profile
- **Output editor:** Review and maintain papers, talks, software, and datasets
- **Workstream lead:** Maintain the milestones and evidence assigned to a
  workstream
- **Project leadership:** Review collaboration-wide progress and reporting
- **Administrator:** Manage people, roles, integrations, and system settings
- **Service worker:** Non-human identity restricted to a particular scheduled or
  integration task

A person may hold more than one role. Roles must be granted explicitly and logged.
The Supabase server secret must never be exposed to browser code; privileged
operations must execute on a trusted server or secured function.

Future identity options may include ORCID linking or institutional identity, but
should not be added until there is a demonstrated need.

## 9. Core data model

The schema should use stable internal identifiers and preserve the source and
history of externally derived data. Expected entities include:

- `people` and `profiles`
- `institutions`, including ROR identifiers and institution type
- `memberships`, with start and end dates
- `roles` and `role_assignments`
- `workstreams` and `workstream_memberships`
- `milestones`, `milestone_updates`, and `milestone_evidence`
- `metric_definitions`, `metric_observations`, and reporting snapshots
- `preprints` and number-allocation events
- `publications`, identifiers, authorships, and project attribution
- `talks`, `software_releases`, `datasets`, and other outputs
- `news_items` and public-feature settings
- `reporting_periods`, report sections, exports, and approvals
- `announcements` and delivery records
- `integration_runs`, candidate matches, failures, and checkpoints
- `audit_events`

Structured records should carry creation, update, source, and review metadata.
Deletion should be reserved for erroneous or legally required removal; normal
membership and output history should use status changes and end dates.

## 10. Preprint-number workflow

The preprint system must guarantee that two concurrent requests cannot receive
the same number. Number allocation will therefore be a database transaction, not
a counter held in application memory.

Proposed workflow:

1. An authenticated member supplies a provisional title, contact author, output
   type, and relevant workstream.
2. The server validates active membership and the required fields.
3. A database transaction allocates the next number and creates an immutable
   allocation event.
4. The requester and publication administrators receive confirmation.
5. Authors later add arXiv, DOI, journal, INSPIRE, acknowledgment, and OSTI data.
6. Withdrawn or duplicate entries retain their number and history; numbers are
   never silently reused.

The exact number format, rollover policy, eligible output types, and correction
rules are open governance decisions.

## 11. Publication and output tracking

A daily scheduled process should query arXiv and INSPIRE-HEP and create candidate
records for human review. Matching signals may include:

- Authenticated ORCID identifiers
- arXiv and INSPIRE author identifiers
- Curated name variants
- Collaboration name or acknowledgment text
- Known project institutions
- Links from an issued preprint number

The system must record why a candidate was matched and must not publish a weak
match automatically. Reviewers can accept, reject, merge, or defer candidates.
Manual corrections must survive later imports.

Deduplication should prefer persistent identifiers such as DOI, arXiv ID,
INSPIRE record ID, and OSTI ID. A preprint and its journal article should normally
be versions of one intellectual output rather than two reported achievements.

Software, datasets, talks, workshops, and other products will use parallel manual
or semi-automated workflows.

## 12. Milestones, metrics, and DOE reporting

The initial milestone and metric catalog will be extracted from the funded
proposal and reviewed by project leadership before import. Each item should have:

- Stable identifier and exact approved wording
- Public or internal visibility
- Workstream and accountable owner
- Reporting periods and due dates
- Target, unit, and measurement method when applicable
- Current state and confidence
- Narrative update
- Supporting evidence and links
- Risks, dependencies, and mitigation
- Complete update history

Reporting-period snapshots must preserve what was known and approved when a
report was submitted, even if live records later change.

For each research output, the portal should be capable of tracking:

- DOE award number and correct acknowledgment
- Accepted-manuscript availability
- E-Link or OSTI submission status and identifier
- DOE PAGES discoverability when applicable
- Data deposition and DOI
- Software release, archive, DOI, and DOE CODE status
- Related milestones, metrics, institutions, and people

The application will assist with preparation and completeness checks, but formal
submission remains in the designated DOE systems, including PAMS, E-Link, DOE
PAGES, DOE Data Explorer, and DOE CODE unless DOE supplies an approved integration.

## 13. Slack and collaboration communications

Slack is the primary routine communication channel. The website integration may:

- Announce reviewed papers, talks, software, and datasets
- Confirm issued preprint numbers in an appropriate channel
- Remind responsible people about upcoming or overdue milestones
- Request completion of missing reporting fields
- Post periodic activity summaries
- Deliver approved leadership announcements

Messages should be drafted from structured data, previewed, approved where the
audience is broad, and recorded with delivery status. The Slack credential must
be narrowly scoped, stored as a deployment secret, and rotatable without a code
change.

A basic email distribution list is still advisable for contractual notices,
emergencies, and people who are temporarily inactive in Slack.

## 14. Documents, calendar, and meetings

The project should select one existing institutional platform for collaborative
documents and meeting materials. The site will provide a curated directory and
contextual links rather than duplicate the files.

A shared project calendar should be the authority for collaboration meetings,
reviews, reporting deadlines, workshops, and major events. Public events may be
displayed on the site through an approved feed; internal details should remain
authenticated.

## 15. Research identity, software, and data preservation

- Collect authenticated ORCID identifiers rather than inferring them by name.
- Identify institutions with ROR IDs while retaining the display name required
  by the collaboration.
- Use GitHub releases for selected public software products.
- Use Zenodo where appropriate to archive public releases and issue citable DOIs.
- Track DOE CODE and DOE Data Explorer obligations separately from optional
  third-party preservation.
- Record licenses, repositories, archival identifiers, related publications,
  contributors, and supported milestones for software and data products.

## 16. Security and privacy

Minimum requirements include:

- Row Level Security and least-privilege database grants
- Server-only handling of privileged credentials
- Multi-factor authentication for service administrators
- At least two collaboration-controlled administrators for each critical service
- No credentials, tokens, database dumps, or private records in Git
- Protected production configuration and reviewed database migrations
- Audit events for role changes, roster changes, preprint allocation, milestone
  edits, reporting approvals, and broad announcements
- Rate limiting and input validation on state-changing endpoints
- Dependency monitoring and prompt security updates
- Documented incident response and credential rotation
- Clear privacy and photograph-consent practices
- Periodic review and removal of access for departed members

GitHub organization membership and collaboration membership are related but
distinct. Neither should silently grant the other.

## 17. Backups and continuity

The Supabase Free plan does not provide the managed backup guarantees expected
of a paid production plan. Before the portal contains authoritative data, the
project should implement encrypted, regularly tested PostgreSQL exports to an
institution-controlled destination. Supabase Storage objects require their own
backup procedure.

The project should document:

- Backup frequency and retention
- Responsible people and offboarding procedure
- Restore instructions and periodic restore tests
- Domain and DNS ownership
- Recovery codes and service ownership
- Migration procedure from hosted Supabase to another PostgreSQL service
- Operation during a backend or Slack outage

Occasional backend downtime is acceptable, but silent data loss is not.

## 18. Deployment and development workflow

Proposed environments are:

- **Local:** Developer application and local/test services
- **Preview:** Per-pull-request Vercel deployment using non-production data
- **Production:** Protected main branch deployed to the project domain

Expected workflow:

1. Create a focused branch.
2. Make source, migration, test, and documentation changes together.
3. Run formatting, linting, tests, and `npm run build` after significant changes.
4. Open a pull request and review its preview deployment.
5. Require review for security-sensitive code and schema changes.
6. Merge to `main` to deploy production.
7. Verify health and maintain a straightforward rollback path.

Production secrets will be configured in the relevant service dashboards. A
versioned `.env.example` may document variable names but must never contain real
values.

## 19. Quality requirements

### Performance

- Fast initial public-page rendering on ordinary mobile connections
- Appropriate image sizing and modern formats
- Server and browser caching with explicit freshness behavior
- Pagination and indexed database queries for growing output collections

### Search and discovery

- Descriptive page titles and metadata
- Stable URLs for people, outputs, software, and news
- Structured scholarly metadata where applicable
- XML sitemap and useful social-sharing previews

### Testing

- Unit tests for identifiers, matching, permissions, and formatting
- Database tests for constraints, allocation concurrency, and Row Level Security
- Integration tests for ingestion and Slack message preparation
- Browser tests for critical authenticated workflows
- Automated accessibility checks plus manual keyboard and screen-reader review
- Production build after every significant implementation change

### Observability

- Health and error logging without leaking private data
- Visible status for scheduled imports and their last successful checkpoints
- Alerts for repeated ingestion, authentication, or delivery failure
- Cost and usage alerts in Vercel and Supabase

## 20. Delivery phases

### Phase 0: Foundation and design

- Confirm requirements, ownership, licensing, domain, and visual direction
- Extract public science themes, milestones, and metrics from the proposal
- Establish the GitHub organization workflow and service ownership
- Produce public-site wireframes and a data classification

### Phase 1: Public site

- Implement the visual system and responsive public navigation
- Publish reviewed science, mission, leadership, and institution pages
- Add initial people, paper, talk, and software presentations
- Deploy production through Vercel

### Phase 2: Authenticated foundation

- Configure Supabase, migrations, GitHub sign-in, roles, and audit logging
- Implement member and institution administration
- Implement preprint-number allocation
- Establish backup and restore procedures

### Phase 3: Outputs and reporting

- Add arXiv and INSPIRE ingestion with a human review queue
- Track talks, software, datasets, acknowledgments, and OSTI status
- Import approved milestones and metrics
- Build reporting-period views and exports

### Phase 4: Collaboration operations

- Add Slack integration and announcement approval
- Add shared calendar and document index
- Add deadline reminders and completeness checks
- Refine administrative delegation and onboarding/offboarding

### Phase 5: Evaluation and refinement

- Test annual reporting end to end
- Review accessibility, security, data quality, and operating cost
- Decide whether Supabase should remain on the Free plan, upgrade, or move to
  institutional hosting
- Consider a read-only Metabase reporting service only if leadership needs more
  exploratory analysis than the portal provides

## 21. Initial service ownership and cost model

The current starting assumption is:

| Service | Initial plan | Purpose |
| --- | --- | --- |
| GitHub | USQCD organization | Source, review, issues, and public content |
| Vercel | Pro, initially one deploying seat | Build and application hosting |
| Supabase | Free | Database, authentication, storage, and selected jobs |
| Slack | Paid collaboration workspace | Discussion and notifications |
| Document suite | Existing institutional service | Documents and calendar |
| ORCID/ROR | Public services | Researcher and institution identity |
| Zenodo | Public service | Optional software and data preservation |
| Password vault | Collaboration-controlled plan | Recovery and shared service credentials |

The approximate initial incremental hosting cost is expected to be dominated by
Vercel Pro and the Slack subscription. Usage alerts and a named billing owner are
required before production launch.

## 22. Open questions

These questions should be resolved in approximately this order.

### Governance and ownership

1. Who are the initial technical administrator, backup administrator, content
   approver, publication administrator, and reporting owner?
2. Which actions require one approver and which require two?
3. What are the onboarding, role-review, and offboarding procedures?

### Domain and public identity

4. What production domain or subdomain will the site use?
5. Who owns and administers DNS?
6. Is the working project title the exact approved public title and capitalization?
7. Which DOE Genesis Mission description and award claims have approved wording?

### Content and visual design

8. Which sections of the proposal may be adapted for the public site?
9. Who supplies and approves leadership biographies and scientist photographs?
10. What are the authoritative lists of people, institutions, roles, and
    workstreams at launch?
11. Is the supplied logo the final master, and is a vector source available?

### Authentication and administration

12. Is GitHub the only initial sign-in provider?
13. Will access be invitation-only, domain-based, or approved after first sign-in?
14. Which members may request preprint numbers?
15. What preprint-number format and policy should be used?

### Reporting and integrations

16. What are the final award identifiers and required acknowledgment text?
17. Which proposal milestones and metrics are public, and which are internal?
18. Which DOE reporting fields must be captured for every output?
19. Which Slack workspace and channels should receive automated messages?
20. Which institutional platform will hold documents and the project calendar?

### Legal and operational

21. Which license applies to the application code?
22. Which license or reuse statement applies to site text, graphics, and photos?
23. What privacy notice, records policy, and photo-consent process are required?
24. Where will encrypted backups be stored?
25. What analytics, if any, are acceptable for the public site?

## 23. Decision log

| Date | Decision | Status |
| --- | --- | --- |
| 2026-10-17 | Use `usqcd/usqcd-genesis` as the source repository | Confirmed |
| 2026-10-17 | Make the repository public | Confirmed |
| 2026-10-17 | Begin with Supabase Free | Confirmed |
| 2026-10-17 | Plan for Vercel Pro production hosting | Confirmed in principle |
| 2026-10-17 | Use a paid Slack workspace for collaboration communication | Confirmed in principle |
| 2026-10-17 | Keep public pages available independently of temporary backend downtime | Confirmed |
| 2026-10-17 | Defer repository licensing until code and content licensing are reviewed | Pending decision |

## 24. Immediate next steps

1. Review and amend this document with project leadership.
2. Answer the governance and domain questions above.
3. Review the funded proposal and produce separate public-content and internal
   milestone/metric inventories.
4. Add the final logo source and establish basic brand assets.
5. Approve the initial technical stack and application scaffold.
6. Create low-fidelity information-architecture and homepage wireframes.
7. Define the first public-site milestone and its acceptance criteria.
