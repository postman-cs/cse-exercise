# The "Path A" Customer Onboarding Playbook

## The Problem

Customers are asking for new capabilities to close product gaps, and we're working on those. But they're also asking for something equally critical: how to use what they already have effectively, and how to prove it's worth the investment.

We've developed comprehensive internal guidance on how Postman should be used to solve real platform engineering problems: API discovery and cataloging, collaboration patterns, test automation, governance workflows, observability integration, change management, and auditable trails. These patterns are documented in our "How to Use Postman" guides ([Internal API Collaboration](https://postmanlabs.atlassian.net/wiki/spaces/PRODUCT/pages/6400246392), [Test Automation](https://postmanlabs.atlassian.net/wiki/spaces/PRODUCT/pages/6406013264), [Governance](https://postmanlabs.atlassian.net/wiki/spaces/PRODUCT/pages/6527721754), [Partner](https://postmanlabs.atlassian.net/wiki/spaces/PRODUCT/pages/6405554659) and [Public API Collaboration](https://postmanlabs.atlassian.net/wiki/spaces/PRODUCT/pages/6420791343), [Workflow Documentation](https://postmanlabs.atlassian.net/wiki/spaces/PRODUCT/pages/6557041563), [Toolchain Integration](https://postmanlabs.atlassian.net/wiki/spaces/PRODUCT/pages/6520308058)).

The reality is that customers struggle to implement workspace topologies, testing frameworks, and governance automation without someone working alongside them through execution. Guidance is not enough.

This gap shows up most clearly in IT-driven purchases. IT gets what it needs: SSO deployed, governance controls in place, security requirements met. From their perspective, the purchase is justified. But engineering teams? They're getting the same value they had on the free tier, sometimes less. API definitions stay scattered across cloud consoles, wikis, and institutional memory. Testing remains rudimentary. The engineering problems that the guides are designed to solve remain unsolved.

Even if we see high collaboration metrics in Looker, the reality on the ground may be workspace sprawl, missing documentation, and duplicate collections everywhere. Engineers continue jumping between systems because Postman doesn't contain what they need, which reinforces the habit of looking elsewhere first and prevents us from becoming the first place users go for API development. The [2025 State of the API Report](https://voyager.postman.com/doc/postman-state-of-the-api-report-2025.pdf) confirms this pattern: 93% of developers face collaboration blockers, 55% struggle with inconsistent documentation, and 34% can't discover APIs that already exist within their own organizations. *The people surveyed for the State of the API Report are our own customers.*

This creates the renewal risk. Without engineering value that's measurable and embedded in workflows, there's nothing preventing teams from dropping back to free tiers or trying alternatives. And without proof that the approach works, we can't expand into additional domains or buying centers.

## What is This Playbook?

This is the field execution version of the "How to Use Postman" guides. Each phase maps directly to a guide and informs the way we build an integrated journey.

- Phases 0-2: Internal API Collaboration guide (hub topology, documentation, ownership)  
- Phase 3: API Test Automation guide (assertion patterns across test types)  
- Phase 4: Toolchain Integration guide (CLI/CI, Git, Slack/Jira)  
- Phase 5: Governance and Network guide (reporting, Private API Network, readiness criteria)

Links to each guide are in the Authoritative Execution Guidance section.

**The approach:**

**Day 1:** We start two parallel tracks. The CSM works with IT on org foundation work (SSO, provisioning, user governance policies \- targeting completion by Month 3). Simultaneously, a CSE embeds directly with a pilot domain's engineering team to implement the first Domain API Workspace in 2-4 weeks.  
**Weeks 5-8**: We use Domain 1 as proof to secure Domain 2\. The patterns are established, the build log shows measurable outcomes, and customer tech leads from Domain 1 can advise Domain 2\.  
**Weeks 9-16**: Repeat the template for domains 3 and 4\. By this point, customers are executing with minimal CSE involvement.  
**End state after 3-6 months:** Engineering value is documented, measurable, and embedded in daily workflows. Postman becomes infrastructure that engineering teams depend on and executive sponsors champion.

## Three Outcomes Per Domain

Every domain we activate hits the same three milestones. These are the minimum bar.

**1\. Self-Service API Discovery**

Per [RFC-139](https://postmanlabs.atlassian.net/wiki/spaces/PRODUCT/pages/2725087832/RFC-139+What+is+an+API+Platform?atlOrigin=eyJpIjoiYjM3ODUzZDUwMzRkNDhlY2FkM2Q1NjFiOTVkODk3NjMiLCJwIjoiYyJ9), the core value proposition of an API platform is eliminating the "discovery tax" \- the hidden cost of engineers spending hours hunting through systems to find APIs.

We remove that tax by consolidating a domain's API definitions in Postman. API definitions get imported from Cloud Portals, API Gateways, wikis, and repos. Each collection includes documentation, working auth examples, and lifecycle tags.

The test: can an engineer find an API in under 30 seconds? Before we show up, that same task takes hours of console navigation and asking around. After, it's a workspace search.

The workspace becomes the starting point for API work, not just where engineers send requests and run tests after finding APIs elsewhere.

**2\. Test Automation Activated**

We activate multiple test types across the domain: functional smoke tests, auth and error scenarios, integration chaining, and at least one end-to-end workflow. This typically covers 5-10 critical endpoints.

Tests need to run reliably in local environments before CI integration. The goal is demonstrating that Postman supports meaningful test automation \- functional validation, error handling, workflow testing \- not just endpoint health checks that return 200 responses. This is a prerequisite to CI integration; only once this outcome is validated do we unlock the ability to meaningfully integrate with CI.

**3\. Proof We Can Show Leadership**

We document the transformation: build logs with before and after screenshots, measurable improvements in onboarding time and discoverability, customer quotes from engineers who experienced the change. Active users trending up, test cases expanding, test pass rates improving, time-to-first-call improvements. The beginning state and end state of all of these is snapshotted so that we can show progress.

This documentation serves two audiences: CSMs use it to justify expanding to additional domains, and customer executive sponsors use it to defend renewal decisions.

## How We Execute

The key is co-execution, not consulting. We can’t continue to provide recommendations and hope customers implement them.

The CSM’s role is to broker buying center relationships, identify domains, and coordinate sessions. CSEs work directly with customer engineers in co-working sessions \- same room (virtual), building workspaces together, activating aspirational test cases together, wiring CI together. This is pair programming. The CSE guides in real time.

**Why the CSE model compresses timelines**

Advisory model: 3-6 months per domain, because customers are figuring it out on their own between check-ins.  
Pair programming model: 1-4 weeks per domain, because a CSE is there to guide them through the process.

This acceleration lets customer success activate ***many*** more accounts simultaneously.

**What CSE involvement delivers:**

- 80%+ test activation rate per domain (vs. closer to 20% with advisory-only)  
- 100% attainment of case-study-ready metrics

First domain: 10-15 hours. Second domain: 4-6 hours. Third domain: 2-4 hours, if that.

The customer becomes increasingly independent. CSE time shifts from hands-on guidance to validation and spot-checks, and CSMs are free to focus on buying center expansion and renewal strategy.

| Activity | CSM (Responsible) | CSE (Accountable) | Customer Tech Lead (Consulted) | Executive Sponsor (Informed) |
| :---- | :---- | :---- | :---- | :---- |
| Buying Center Prospecting | Broker relationships, qualify domains | N/A | Identify domain priorities | Approve expansion targets |
| Session Coordination | Schedule, facilitate, follow-up | Prepare technical agenda | Commit to co-working time | N/A |
| Technical Guidance | Wide-scale and surface level | Hands-on support in ingestion, docs, tests, CI | Execute hands-on with guidance | Provides organizational target goals |
| Build Log and Proof | Compile business case, metrics, quotes | Validate technical artifacts | Provide testimonials | Review for renewal alignment |
| Renewal Case | Own executive narrative, forecast | Provide technical evidence | Confirm engineering value | Sign-off on expansion |

## Two Tracks from Day 1: Org Foundation and Domain Pilot

We run two workstreams simultaneously. The CSE role makes this possible.

**Track 1: Org Foundation** CSM coordinates with IT. SSO, provisioning, baseline governance, users in the platform. The target is to have users functional by Month 3\. Throughout this, the CSM continues business discovery and owns keeping everything aligned with business objectives.

**Track 2: Domain Pilot** CSM coordinates, CSE executes with engineering. Stand up the first Domain API Workspace immediately. Deliver usable value in Weeks 1-4 through co-working sessions.

Why run both at once? Because waiting for IT to finish before touching domains adds 3 months to every engagement. Running parallel gives us a domain win while IT work completes, which creates executive confidence and political cover to expand into more domains.

**Stakeholders Confirmed:**

- Executive sponsor (sustaining IT mandate)  
- Domain leads identified (engineering managers for each buying center)  
- CSM plus CSE assigned  
- Customer domain Tech Lead (the technical owner who will co-execute)

**Org-level Governance (CS and IT):**

- SSO and user provisioning are working; CSM monitors drift and the onboarding experience.  
- Enterprise governance controls are active (SCIM, audit logs, role baselines); CSE operates policy as code where possible.  
- Security/compliance requirements are documented with owners and a review cadence; outstanding gaps are tracked with dates.  
- A Postman API key is available for automation; CSE maintains automation collections for health checks.

**Domain-level Governance (CS-led, domain-owned):**

- Workspace standards: naming, lifecycle tags, folder structure, environment strategy.  
- Access model: domain engineer write access; broader org read access; PR/MR workflow defined.  
- Documentation standards: request-level docs, guided auth, examples, links to canonical docs.  
- Test standards: smoke, auth/error, chaining, and performance smoke tests as a minimum; CDC/security optional.

**Domain Prioritization Criteria:**

- Regulatory risk or compliance visibility needs  
- Engineering team size and API volume  
- Renewal impact (domain tied to a key sponsor or revenue)  
- Technical accessibility (CSE can get access to source systems)

**Acceptance to Proceed:**

- 1 domain selected with a named engineering lead and CSE access.  
- IT "solved" narrative is documented.  
- A 4 to 6 week timeline is blocked for the first domain sprint.

## Target Metric \#1: Discoverability Time

Most CS teams track activity: users logged in, collections created, requests sent. These are lagging indicators that don't explain why a customer will renew, and they often hide real value activation problems.

Path A tracks outcomes: time saved, productivity gained, renewal justification earned.

**The metric:** Discoverability time. How long does it take an engineer to find an API and successfully execute it?

This is easy to measure, easy to show executives, and the value compounds across every engineer, every integration, every new hire.

**Before Path A:** Hours of navigating cloud consoles, searching wikis, asking on Slack.

**After Phase 2:** Under 30 seconds via workspace search.

**How to measure this:**

Week 0 \- Work with a technical stakeholder. Live on a call, have them pick a service and walk through what they would have to do to figure out how to properly craft a CRUD workflow for that API. Time them from start to completion. Document every step they take (console navigation, wiki search, whatever).

After Phase 2 \- Same test: have them craft a CRUD workflow for a service in the workspace. Time from workspace search to completed workflow. Target: under 30 seconds to find the service, under 5 minutes to set up auth, under 5 minutes to build the workflow.

Build log entry: "Discoverability improved from \[X hours\] to \[Y seconds\] \- a Z% reduction."

This metric justifies workspace creation before we touch testing or CI. It maps to [the API Platform definition](https://postmanlabs.atlassian.net/wiki/spaces/PRODUCT/pages/2725087832/RFC-139+What+is+an+API+Platform?atlOrigin=eyJpIjoiYjM3ODUzZDUwMzRkNDhlY2FkM2Q1NjFiOTVkODk3NjMiLCJwIjoiYyJ9) in RFC-139 (search and discovery as core abstractions). Executives understand it immediately when you show them the before/after, and the gains here are exponential.

## Phase 1: Get APIs Definitions Into Postman (Week 0-1)

Traditional onboarding fails because it skips ingestion. Teams jump straight to "cool features" and wonder why adoption stalls. The reason is simple: if engineers don’t know that Postman has the information they need, they won't live in it.

Path A inverts this. We ingest 80%+ of a domain's APIs definitions first. We layer on more verbose documentation, more advanced collaborative patterns, and automation later. Without complete ingestion, everything else will fail because the developers are going to be going elsewhere for information regardless.

**What we're doing:** First, we inventory where API definitions actually live \- gateways, cloud portals, repos, wikis. These definitions need to exist in Postman so developers have minimal reason to leave the platform to understand API functionality. We set up environments (Dev/QA/UAT) with proper `baseUrl` and auth placeholders. We build collections with all endpoint and method definitions. We add enough documentation so engineers understand what each API does. We assign at least 2 maintainers per workspace. We publish one stable collection that serves as a one-stop shop for utilizing the API.

We can start the build log with baseline screenshots showing the before state, if it exists.

**Scenario variations:** All three scenarios target the APIs needed for one critical end-to-end workflow as the first domain.

- Blank Slate (S1): Build from scratch by ingesting from external sources  
- Large Existing Team (S2): Fix what's already in Postman, supplement with external sources where gaps exist  
- Foundation Repair (S3): Fix what's already in Postman and supplement with external sources where gaps exist, but limit scope

**Why this matters:** When API definitions are scattered across multiple systems, engineers face delays finding APIs, rely on institutional knowledge to locate resources, duplicate effort across teams, constantly switch between platforms, and multiply documentation and testing work. The longer APIs remain fragmented, the more these costs accumulate across the organization.

Reference: [Internal API Collaboration guide](https://postmanlabs.atlassian.net/wiki/spaces/PRODUCT/pages/6400246392) and [Toolchain Integration guide](https://postmanlabs.atlassian.net/wiki/spaces/PRODUCT/pages/6520308058).

**Done when:**

- [ ] 80%+ of domain APIs are in Postman  
- [ ] 2+ maintainers assigned, domain lead confirmed as sponsor  
- [ ] At least 1 Published collection with clear purpose  
- [ ] Dev/QA/UAT environments configured with `baseUrl` and auth placeholders  
- [ ] New engineer can find target API in under 30 seconds  
- [ ] Build log started with before/after screenshots

## Phase 2: Make It Consumable (Week 1-2)

Consolidating API definitions into Postman without leveraging our strengths in making it actionable and executable only gets us partway there. Phase 2 is where we lean into our strengths and leverage Postman-specific functionality to remove barriers to consuming the APIs.

The difference between Postman and traditional API docs is executability. Engineers don't just read about an API \- they leverage guided auth to accelerate onboarding, they run it inline, and they modify and build with it in the same environment.

We're not trying to wholly replace comprehensive API reference documentation; it can continue to live in a developer portal if the customer desires. We're answering the four questions engineers ask when they need to use an API:

1. What does this do?  
2. How do I auth?  
3. What does a working request and response look like?  
4. Where do I go for more detail?

This is where documentation becomes actionable. External portals may remain, but Postman becomes a one-stop shop for engineers to do what they need to do.

**What we're building:**

- Collection-level docs: purpose, owner, auth guidance, links to canonical docs  
- Request-level docs: parameters, examples, error scenarios  
- Guided authorization: OAuth configs, pre-request scripts  
- 3-5 saved examples per key endpoint (happy path, auth failure, validation error)  
- External doc links  
- Publish stable APIs to Private API Network (optional but valuable)  
- Fork and PR workflow for changes  
- Workspace updates for change management

Reference: [Internal API Collaboration guide](https://postmanlabs.atlassian.net/wiki/spaces/PRODUCT/pages/6400246392) and [Collaborative Debugging guide](https://postmanlabs.atlassian.net/wiki/spaces/PRODUCT/pages/6448055476).

**Done when:**

- [ ] All Published collections have descriptions, owner info, repo links  
- [ ] External links present (Postman to existing docs and source repos)  
- [ ] Auth setup works in under 5 minutes  
- [ ] Top 10 requests have 3+ saved examples  
- [ ] New QE can find API, auth, send first successful request in under 30 minutes  
- [ ] Fork workflow documented, hub separation enforced  
- [ ] Build log updated with documented collection screenshot and domain Tech Lead quote

## Phase 3: Activate Testing (Week 2-3)

Phase 3 is where the narrative shifts from "useful for finding APIs" to "accelerates releases."

The goal isn't 100% coverage. The goal is demonstrating the breadth of testing possible with Postman and the value of doing it before we ever wire anything into CI.

We activate a breadth of test types per the official Test Automation guide: Exploratory, Functional, Smoke, Integration chaining. The point is showing comprehensive value beyond "hit endpoint, check for 200."

**Test Case Activation Matrix:**

- Exploratory tests: ad-hoc with documented steps  
- Functional/smoke: 2-3 assertions checking status and response shape  
- Auth/error scenarios: 401 and 400 at minimum  
- Integration chaining: pass data between requests  
- Performance smoke: simple response time threshold  
- E2E workflow: one business flow across services  
- Optional: Security checks, Consumer-Driven Contract tests

Reference: [Test Automation guide](https://postmanlabs.atlassian.net/wiki/spaces/PRODUCT/pages/6406013264).

**Done when:**

- [ ] Each Testing Activation Matrix row covered at least once  
- [ ] 5-10 endpoints plus 1 workflow instrumented with assertions  
- [ ] Tests runnable locally with documented steps, failures produce clear messages  
- [ ] Parameterization started (environment variables)  
- [ ] Build log updated with local run screenshot and note on test types activated

## Phase 4: Make Results Visible (Week 3-4)

Phase 4 takes everything we activated in Phase 3 and makes it visible where engineers already work: PRs and MRs, Slack, dashboards, email.

**What we're doing:** Pick at least one visibility channel. CI non-blocking is ideal; tests run on every MR but don't block merges while we stabilize. Monitors can be an alternative, if necessary.

Select one high-value, working E2E workflow activated in Phase 3, and integrate it where engineers live: MR/PR comments, Slack notifications, Jira updates, monitor emails.

Reference: [Toolchain Integration guide](https://postmanlabs.atlassian.net/wiki/spaces/PRODUCT/pages/6520308058).

**Done when:**

- [ ] At least one visibility channel active (CI, Monitor, or manual cadence)  
- [ ] 1 business-critical E2E workflow executing successfully in Dev and/or QA  
- [ ] Results visible to engineers (MR view, Slack/Jira, monitor email, dashboard)  
- [ ] E2E flow demoed and validated as valuable by domain lead/team  
- [ ] Build log updated with results screenshot and E2E run evidence

## Phase 5: Prove It and Scale (Week 4+)

Phase 5 is the go/no-go decision. Is this domain ready to serve as proof for the next buying center, or do we need another week to stabilize?

The Domain Readiness Scorecard gives us objective criteria: adoption metrics, automation metrics, efficiency gains, renewal leading indicators.

If we pass: compile the build log with before/after screenshots and customer quotes, present to the domain lead and exec sponsor, use that proof to open the next buying center. This is how CSMs prospect like AEs \- with evidence, not promises.

**What we're doing:** Score the domain against the Readiness Scorecard. Address gaps if they exist. Compile the complete build log: before/after, metrics, customer quote. Present to domain lead and executive sponsor to validate value delivered.

If Go: execute Next Domain Plan. Select next domain, schedule kickoff, replicate the template we just proved works.

**Domain Readiness Scorecard (Go/No-Go to Next Domain):**

**Adoption Metrics:**

- [ ] Active users in workspace: ≥5 per week (target: 50%+ of the team)  
- [ ] Maintainers assigned: ≥2 per workspace  
- [ ] Published collections: ≥1 (target: all stable APIs)  
- [ ] Private API Network entries: ≥1 (if applicable)

**Automation Metrics:**

- [ ] CI pipeline running: Yes (on MRs/PRs)  
- [ ] Test pass rate: ≥80% over the last 10 runs  
- [ ] Test coverage: ≥1 auth test \+ ≥1 schema test per top endpoint  
- [ ] E2E workflow: ≥1 passing in Dev/QA

**Efficiency Metrics:**

- [ ] Time-to-first-success for a new QE: ≤30 minutes  
- [ ] API discoverability: \<30 seconds to find a target API  
- [ ] Doc referral uptake: Evidence of traffic from Postman to canonical docs

**Renewal Leading Indicators:**

- [ ] Weekly CI run count: Trending up  
- [ ] Forks/PRs per month: ≥2 (active use and contribution)  
- [ ] Private API Network views: Trending up (if published)  
- [ ] Cross-domain consumption: ≥1 additional team

**Next Domain Plan:**

- [ ] Select the next domain using prioritization criteria.  
- [ ] Book a kickoff session with the new domain lead.  
- [ ] Replicate the Domain Sprint Template (2-4 weeks).  
- [ ] Share the build log from Domain 1 as internal proof.  
- [ ] Update the CSM/CSE capacity plan (can run 2-3 domains in parallel after 1-2 iterations).

# Domain Sprint Template and Build Log

The first domain with any customer is where we figure out what works for their specific environment \- where their API definitions live, how to get them into Postman, what their auth patterns look like. The second domain within that same customer is where we prove the approach is repeatable with less hands-on CSE work. By the third domain, that customer is running most of it themselves with CSE spot-checks.

**How this scales across the portfolio:** The CSE does most of the technical execution work (co-working sessions, hands-on guidance), while the CSM handles coordination, buying center relationships, and business case assembly. Once a CSE has validated this approach with one customer's first domain, they understand the pattern well enough to run first domains with other customers in parallel.

**CSE capacity and engagement duration:**

- **First domains:** A single CSE can handle 2-3 first domain implementations across different customers simultaneously (10-15h per domain). This works because the engagement is structured into 4 co-working sessions with customer homework in between, not continuous hands-on work.  
- *Second and Third Domains:*\* As customers progress to domains 2 and 3 (requiring 4-6h and 2-4h respectively), a CSE can manage even more accounts. A CSE might be running first domains with 2 customers while supporting second/third domains with 3-4 others.  
- **CSE graduation:** By the time a customer completes their third domain, the CSE is essentially done with Path A onboarding for that account. They may return later for other work (advanced automation, governance, other use case activation), but the foundational Path A work is complete.  
- **CSM longevity:** The CSM remains engaged throughout the customer lifecycle \- continuing buying center expansion, coordinating additional domains, managing renewals, and orchestrating strategic initiatives. While the CSE's Path A work has a clear endpoint, the CSM relationship is ongoing.

Every customer's first domain requires discovery work \- their API landscape, auth patterns, and infrastructure are all unique. But the framework (Phase 1-5, co-working sessions, acceptance criteria) stays consistent. The key is that CSEs are teaching the pattern through co-execution, not doing all the work for the customer.

After validating the approach with the first domain, each subsequent domain follows a structured 2-4 week cycle with four co-working sessions, clear homework, and defined acceptance criteria.

**Build Log Template:**

```
Domain: [Name]
Timeline: [Start] - [End]
Team Size: [# Engineers]
API Count: [# APIs ingested]

Before (Screenshots + Description):
- APIs scattered across [systems]
- No single source of truth
- No automated testing
- Onboarding took [X days]
- No production visibility for API errors

After (Screenshots + Description):
- Domain API Workspace with [X] Published collections
- [Y] active users/week; discoverability <30 seconds
- CI pipeline running [Z] tests per MR with [W]% pass rate
- E2E workflow automated

Business Impact:
- Onboarding time (time to first call): [X days] > [Y minutes] (Z% improvement)
- Test cases automated: [X number]
- Amount of time saved via test case automation: [X] per version

Customer Quote:
"[Domain Lead Name], [Title]: '[Before statement]. Now [after statement]. [Business impact with number].'"

Example (aim for something similar): "When we started using Collection Runner for all the right things, we dramatically accelerated our testing. What took us days now takes us minutes."

Metrics Summary:
- Ingestion: X% of APIs in Postman
- Adoption: Y active users/week (Z% of team)
- Automation: N tests, W% pass rate, CI on all MRs
- E2E: M workflows passing in Dev/QA
```

# Appendix A: What We've Seen Work, and What We've Seen Fail

These observations come from actual Path A engagements across different customer scenarios.

**What tends to fail:** Skipping comprehensive ingestion to move quickly into testing or CI integration. When API definitions remain fragmented across cloud consoles, wikis, and tribal knowledge, engineers continue jumping between systems to find what they need. This system-hopping establishes Postman as one tool among many rather than the primary entry point for API work. Each successful workflow that starts elsewhere reinforces the habit of looking for APIs outside Postman first. Without comprehensive ingestion, Postman never becomes the default starting point, which prevents adoption from taking hold.

**What tends to succeed:** Completing ingestion first, establishing Postman as the primary entry point for API work, then adding automation incrementally while tracking metrics that support renewal conversations.

**Complete ingestion before moving forward.** Without at least 80% of domain APIs in the workspace, subsequent phases build on an incomplete foundation. Engineers continue using their existing discovery patterns (console, wiki, Slack) because those systems still contain the necesasry fundamental information that Postman lacks. Comprehensive ingestion breaks this cycle by making Postman the most reliable source of API information. Early investment in systemic governance and automation can wait until engineers develop the habit of starting their API work in Postman.

**Documentation makes Postman the easier choice.** The flexibility of the collection format creates variability in quality. A canonical collection that clearly describes domain service behavior makes Postman more useful than the alternatives. When engineers can find working auth examples, clear request documentation, and links to deeper resources within Postman, they stop context-switching to other systems. Each piece of documentation reduces friction and reinforces Postman as the primary workflow.

**Activate test types before integrating CI.** The initial goal is demonstrating breadth of testing methods, not achieving immediate CI integration. Most teams use Postman primarily for individual endpoint checks. Expanding to functional tests, integration tests, smoke tests, and end-to-end workflows \- even running locally without CI \- shifts the perception of Postman from "HTTP client" to "testing platform." Once multiple test types are active and validated locally, CI integration becomes a natural extension of an established workflow rather than a disruptive change. Moving directly from basic endpoint testing to full CI integration with reporting introduces too many changes simultaneously and risks failure.

**Track renewal-relevant metrics.** Renewal decisions require answering "What problem did this solve and how much better are we now?" Metrics like active users, CI run frequency, test pass rates, and cross-domain consumption only become renewal-relevant when they show measurable improvement from a documented baseline. This is why Path A starts the build log at Week 0 with baseline screenshots and measurements. Without the before-state, current metrics are just numbers. With documented improvement, they become evidence that Postman solved real problems. Customer quotes amplify this by showing engineers valued the change. The tracking strategy isn't just measurement \- it's building a defensible renewal case from day one.

**Maintain consistency across domains.** Each domain follows the same 2-4 week sprint structure. This consistency serves multiple strategic purposes beyond operational efficiency. It makes success replicable \- domain leads can look at previous build logs and see the exact path they'll follow. It makes knowledge transferable \- tech leads from domain 2 can get specific, actionable advice from domain 1's team because they're executing the same process. It makes outcomes comparable \- when every domain follows the same phases, variations in results reveal what's working and what needs adjustment rather than reflecting process differences. Most importantly, consistency allows customers to internalize the pattern and eventually execute independently. Without it, each domain becomes a custom project requiring full CS involvement. With it, each domain reinforces the template and accelerates adoption of the next one.

**Structure for capability transfer.** CSMs track progression through dependency phases. CSEs provide intensive initial guidance, then validate as Customer Tech Leads execute with increasing autonomy. This graduated reduction in CSE involvement ensures capability transfers to the customer team, creating lasting ownership rather than dependency on external resources.

# Appendix B: Scenario Selection Guide

Not every Path A customer starts from the same place. The core principles stay the same \- establish Domain API Workspaces, activate test automation \- but tactical execution varies depending on whether you're working with a blank slate, a large existing team, or a foundation-repair situation.

Path A customers share a commonality: IT- or Security-mandated Postman consolidation. There are differences, though. and how they arrived at that point matters.

A new Enterprise customer bringing scattered free users under governance faces different challenges than a customer with 1,000 existing users in an existing Postman instance. Both are different from a customer whose initial Enterprise implementation failed and now faces renewal risk.

Applying the same approach to all three would result in unnecessary work for some customers, insufficient scoping for others, wrong stakeholder engagement, and misaligned success metrics.

## Which Scenario Am I In?

**Does the customer already have Postman Enterprise?**

- NO: Go to next question  
- YES: Skip to third question

**Do they have significant existing Postman usage (100+ users)?**

- NO: Scenario 1 (Blank Slate)  
- YES: Scenario 2 (Large Existing Team)

**Are they getting value (engagement, adoption, automation)?**

- YES: Not a Path A customer \- use standard expansion playbook  
- NO (renewal at risk): Scenario 3 (Foundation Repair)

## Scenario 1: Blank Slate

New Enterprise purchase. Scattered free users, minimal structure.

These customers just bought Enterprise to consolidate individual accounts and small team workspaces. No authoritative workspace topology exists. No consistent naming. No governed access model. No systematic docs or testing.

This is the ideal Path A starting point. We can build correctly from day one without remediating chaos or fighting existing workflows.

**When to use this approach:** New Enterprise purchase with scattered free users. There's nothing to "undo" here.

**Why this is easier:** There are no remediation costs or organizational politics around changing existing structures. This accelerates time-to-value and allows us to establish the canonical Domain API Workspace pattern without legacy constraints.

**Signals you're in this scenario:** There is no authoritative workspace topology. API collections are sparse or incomplete. Lifecycle tags, environments, and PR/fork workflows are not established. Documentation exists outside of Postman. CI integration and automated testing are absent.

## Scenario 2: Large Existing Team

Upgrading from Free or Professional with hundreds (or thousands) of active users.

These customers have existing workspace structures, collection libraries, and established usage patterns. The critical unknown is quality. They may have organically developed sound practices that need governance layered on top. They may have high collaboration numbers, but the quality and value of that collaboration may be limited.

The only way that we'll know is to look. High user counts and collaboration metrics can mask serious structural problems: workspace sprawl with hundreds of unorganized collections, widespread duplication, hardcoded values instead of proper environment management, missing lifecycle tags, and tribal knowledge dependencies.

This scenario requires careful political navigation. Teams have established workflows, and resistance to structural changes can exceed the technical complexity of migration itself.

**When to use this approach:** This applies when a customer is upgrading from Free or Professional tier with hundreds to thousands of existing users. The quality and structure of their current usage is unclear, and multiple workspaces and collections exist with inconsistent standards across them.

**Why assessment first matters:** A structured assessment and remediation plan reduces the risk of disruption during migration. Quality improvements such as deduplication, proper tagging, and environment configuration enable more credible collaboration metrics.

**Signals you're in this scenario:** The customer has high user counts, but the quality of their usage is unclear. Collaboration metrics appear strong on paper, but structural issues are suspected. Teams have established workflows that may create resistance to change.

## Scenario 3: Foundation Repair

Target customers for this scenario have been on Enterprise for 6 or more months with low adoption and are now facing renewal risk, whether they admit to it or not.

These accounts face renewal risk because the initial implementation failed. Whether self-executed or poorly guided, they never established the hub, automation, and other foundations that justify the Enterprise investment.

Engagement remains low despite licenses being available. The account shows minimal active users, few or no Published collections, limited test method utilization, and limited or no integration with automation. Teams are still relying on tribal knowledge or external documentation.

This scenario requires both urgency and scope discipline. Comprehensive remediation is not feasible in the available timeframe. The Rescue Sprint approach focuses on proving value with one domain and one end-to-end workflow within 2-3 weeks, securing renewal commitment, then backfilling the broader foundation.

**When to use this approach:** The customer has been on Enterprise for 6 or more months with low adoption and renewal risk. The initial implementation did not establish the foundations needed to justify the investment.

**Why the rescue-first approach works:** A fast, evidence-backed win changes value perception and creates breathing room. Focusing scope prevents getting mired in comprehensive remediation when time is limited. The broader foundation work can happen after the renewal is secured, but we can't just sit around and pray either.

**Signals you're in this scenario:** Renewal conversations have already started or are imminent. Someone on the customer side is asking "what are we getting for this investment?" The executive sponsor needs concrete proof of value to defend the renewal, and they need it in weeks, not months. There's organizational memory of a previous attempt that didn't deliver, creating skepticism that needs to be overcome quickly.

# Appendix C: PS/FDE Escalation Triggers

CSEs handle standard domain sprints: guiding ingestion from common sources, demonstrating test patterns, and providing CI templates. When complexity exceeds this scope, we escalate to Professional Services or Forward Deployed Engineering. The trigger isn't "this is hard"; it's "CSE hands-on-keyboard time will exceed 20 hours" or "the customer can't execute even with active guidance."

**CSE Scope:**

- Facilitating co-working sessions with real-time guidance  
- Providing ingestion recipes for standard sources (API Gateway, OpenAPI)  
- Demonstrating test script patterns; the customer implements with CSE validation  
- Providing CI config templates and guiding customization  
- Guiding E2E workflow design with live troubleshooting

**Professional Services (PS) Escalation:** Escalate to Professional Services (PS) when a customer requires a fully managed 'Onboarding' engagement to get set up securely for scale, or a custom 'Workflow' engagement to solve a specific business problem not covered by standard CSE guidance.

**PS Engagement Types:**

- **Onboarding:** IT-ready environment consolidation, initial workspace setup matching collaboration patterns.  
- **Workflows:** Custom implementations for Design/Prototype/Iterate, Build/Test/Deploy, or Promote/Manage Change patterns.  
- Large-scale migrations (\>10 domains in parallel).  
- Complete governance framework implementation.  
- Customers unable to execute technical work (require full-service delivery).

**Forward-Deployed Engineering (FDE) Escalation:** Escalate to Forward-Deployed Engineering (FDE) when a customer requires a novel, bespoke solution that extends Postman's core capabilities, such as the project to enable 'Postman Monitors in T-Mobile's private environment.' This is for challenges that cannot be solved with existing product features and require deep, embedded engineering work.

**FDE Engagement Types:**

- Novel technical solutions extending product capabilities  
- Private environment integrations (e.g., T-Mobile's private monitors)  
- Custom tooling requiring embedded engineering  
- Integration with proprietary or non-standard systems requiring new development  
- Complex architectural problems requiring product changes

**Trigger Criteria:**

- CSE session time exceeds 20 hours for a single domain (vs. the standard 10-15).  
- Customer requests advanced automation beyond standard patterns.  
- Domain has \>500 APIs requiring automated ingestion pipelines.  
- Integration with non-standard systems (mainframes, SOAP-only, proprietary gateways).  
- Customer lacks the technical resources to execute even with active guidance.  
- Solution requires product capabilities that don't exist yet.

### How it ties Together

- **When to engage:** Use the Trigger Criteria above as decision points for escalation; if the scope threatens sprint timelines or requires non-standard integrations, we need to engage the proper team immediately.  
- **Professional Services (PS):** Time-bound engagements that accelerate onboarding outcomes (ingestion at scale, dedupe automation, governance rollout, non-standard CI wiring). PS delivers with clear SOWs and returns maintainable assets to the customer team.  
- **Forward-Deployed Engineering (FDE):** Embedded engineering for complex, in-environment workflows (custom tooling, platform integrations). FDE converts solutions into reusable templates and guidance for CS/CSE and product.  
- **Handoff flow:** When a trigger is identified, the CSE and AE assess the scope with either PS or FDE. For PS engagements, they pull in professional services to create a statement of work that defines measurable Path A outcomes. For FDE engagements, FDE embeds directly with the customer to solve the problem. During execution, the CSE shadows the work to learn and transfer capability back to the broader CS team. Once complete, the customer returns to the standard Path A cadence, and we update our templates and Build Log with what was learned.

# Appendix D: Time-to-First-Call \+ Reverse Demo

This is how we establish the baseline for the Discoverability Time metric. Instead of demoing Postman to the customer, we have them demonstrate their current API discovery and integration workflow to us. This serves three purposes: it quantifies the "before" state for our build log, it reveals exactly which systems we need to ingest from in Phase 1, and it creates an organic narrative that executive sponsors understand immediately.

This session happens at Week 0, before any Path A work begins. It's a 30-60 minute working call with a technical stakeholder who regularly works with the domain's APIs.

## Pre-Call Setup

**Who needs to be on the call:**

- CS Resource  
- Technical stakeholder from the customer (engineer, QE, or technical lead who actually uses the APIs daily)  
- Optional: Domain lead or manager (observer only)

**Do not invite:** Executive sponsors, IT stakeholders, or anyone who will explain the process theoretically rather than showing it practically.

**Technology setup:**

- Record if we can (with customer permission)  
- Timer ready

**Pre-call message to the technical stakeholder:**

"We're going to do something a bit different on tomorrow's call. Instead of us showing you Postman features, we'd like you to walk us through how you currently find and use APIs in \[domain name\]. 

The goal is to make Postman the place developers can go to get up and running with the APIs they need to use extremely quickly. To do that effectively, we need to understand your current workflow \- where you look for documentation, how you figure out auth, all of it. 

We'll pick a service API, and you'll show us what you'd do today to build a working CRUD workflow for that API. Plan for 30-60 minutes, and come ready to screen-share."

## Opening the Call

Start with this framing to set expectations and remove any perception of criticism:

"Thanks for taking the time. Let me explain what we're trying to accomplish here. The best way we see enterprises use Postman is to have it serve as the place that developers can go to get up and running with the APIs they need to use to build stuff extremely quickly.

So instead of you having to go to GitHub, Confluence pages, maybe even Slack somebody to figure out how to utilize a service and integrate it correctly \- all that information is just accessible in Postman. It doesn't have to be the full, comprehensive documentation for the API, but we want people to be able to find these APIs, services, and endpoints, the schemas for the responses and requests, and get up and running in 30 seconds.

To make that work for your environment, we need to understand your current workflow. When you need to integrate with a service, how do you figure out what it does, how to authenticate to it, what a working request and response look like, and where to go for more detail? We want to see that discovery process step by step.

Let's think about your current work. Is there anything you're working on right now, or anything on your to-do list, where you need to figure out how to use a service or API that you haven't used before? Something where you'd need to go hunt down documentation, figure out auth, and build a working integration?

If nothing current comes to mind, we can pick one of your domain's services that you're somewhat familiar with but haven't touched recently. Either way, we'll walk through how you'd build a basic CRUD workflow for it \- Create, Read, Update, Delete operations. Show us everything: where you'd look for documentation, how you'd figure out auth, where you'd test requests, all of it.

We'll time this to establish a baseline. After we onboard this service into Postman, we'll compare the results. Ideally, we compress what might take 30-45 minutes today down to a few minutes.

Any questions before we start?"

*Wait for confirmation, then proceed:*

"Great. Share your screen and walk me through it.

## During the Exercise: What to Observe and Document

Use this template in your shared doc to capture information in real-time:

```
Reverse Demo Documentation
Domain: [Name]
Date: [Date]
Technical Stakeholder: [Name, Role]
Service Selected: [Service Name]

START TIME: [HH:MM:SS]

Timeline and Observations:
[HH:MM:SS] - Started exercise
[HH:MM:SS] - Navigated to [System/Tool]
[HH:MM:SS] - Searched for [documentation/API definition]
[HH:MM:SS] - Switched to [another system]
[HH:MM:SS] - Asked question: "[exact question]"
[HH:MM:SS] - Hit dead end: [description]
[HH:MM:SS] - Found auth documentation
[HH:MM:SS] - Attempted first request
[HH:MM:SS] - [continue documenting every action with timestamp]

END TIME: [HH:MM:SS]
TOTAL ELAPSED TIME: [X minutes Y seconds]

Systems Accessed:
- [System 1] - [purpose]
- [System 2] - [purpose]
- [System 3] - [purpose]

Context Switches: [Number of times they switched between different tools/tabs/systems]

Authentication Challenges:
- [List any auth-related friction]

Documentation Sources Consulted:
- [Cloud console / Wiki / Confluence / Slack / Email / Asking colleague / etc.]

Tribal Knowledge Dependencies:
- [Any instance of "I usually ask Dave" or "I remember from last time"]

Dead Ends Encountered:
- [Times they went down a path that didn't work]

Questions They Couldn't Answer Without Help:
- [Questions they had but couldn't resolve on their own]

Final Outcome:
- [ ] Successfully built complete CRUD workflow
- [ ] Partially successful (which operations: [ ])
- [ ] Unable to complete

Engineer's Reaction/Comments:
"[Capture any frustration, surprise, or commentary they provide during the exercise]"
```

**What to listen for and document:**

- **Fragmentation signals:** "Let me check the AWS console... now I need to look at our internal wiki... let me Slack our platform team."  
- **Tribal knowledge:** "I think \[colleague\] knows where this is documented." "If I remember correctly..."  
- **Authentication friction:** "I need to generate a token... wait, where do I do that again?"  
- **Documentation gaps:** "The docs are out of date." "This isn't documented anywhere."  
- **Duplicate effort:** "I built something similar last month, but I can't find it now."

**Look out for shortcutting.**

***If they say:*** "I would normally just ask \[colleague\]..." You respond: "That's valuable information \- I'll note it down. But for this exercise, pretend \[colleague\] isn't available. What would you do?" ***If they say*****:** "If I remember correctly..." You respond: "Try to show us the steps as if you were doing it fresh. Walk us through each one." ***If they try to explain instead of showing:*** You say: "Actually, rather than explaining, can you share your screen and just do it? It helps if we can see the real workflow, clicks and all."

**If they start showing you their existing Postman setup:** Acknowledge it briefly, note any relevant details, then redirect: "This is helpful context \- I can see what you've got here. For this exercise though, let's focus on a fresh scenario where you need to integrate with something new. Walk me through that discovery process."

**Keep the conversation focused on the discovery exercise.** If workspace design, permission models, or setup questions arise, note them for later: "That's a great question \- let's capture that for when we discuss workspace topology. For now, let's stay focused on how you'd find and use this API today."

**When friction appears, let it play out.** If they encounter a dead end, authentication failure, missing documentation, or express frustration, do not rush to help. Acknowledge it: "I can see it's not straightforward \- we can fix that. I'll note this down as a particular point of friction."

**This friction is data**. Broken documentation, dead links, abandoned wikis, "I don't remember where this lives" \- these aren't failures of the exercise. They're proof points of the problem you're solving. The more visible the friction is in this baseline measurement, the more dramatic the improvement will be later.

**The exercise ends when:** (1) They successfully demonstrate all CRUD operations, (2) They hit a hard blocker they can't resolve, or (3) They reach 30 minutes of effort. Any of these outcomes provides the baseline you need.

## Closing the Exercise

Once they've either completed the CRUD workflow or hit a stopping point, stop the timer and acknowledge the work:

"Thank you \- that was perfect. It looks like it took us about \[X minutes\]. I know that felt \[awkward/frustrating/tedious\], and that's the point. What you just showed us is the baseline we're going to improve.

In a few weeks, after we complete the first two phases of onboarding this API, we’ll cut this down to a few minutes. The target is under 30 seconds to find the API, a few minutes to set up auth, and under 5 minutes to complete the workflow.

When we present results to \[executive sponsor\], we'll show them this before state and the after state side by side. That's how we prove the value of what we're building.

Any questions about what happens next?"

## Post-Call Documentation

Within 24 hours of the call, complete these steps:

**1\. Calculate and document the metrics:**

- Total elapsed time (minutes and seconds)  
- Number of systems accessed  
- Number of context switches  
- Number of tribal knowledge dependencies  
- Number of dead ends  
- Success outcome (complete/partial/failed)

**2\. Take screenshots:**

If the session was recorded, capture screenshots showing:

- The multiple browser tabs or systems they had open  
- Any dead ends or error states they encountered  
- The final state (successful workflow or wherever they stopped)

**3\. Add to the build log:**

Create the Week 0 entry in the build log:

```
Week 0 Baseline - Reverse Demo Results

Domain: [Name]
Service Tested: [Service Name]
Technical Stakeholder: [Name, Role]

Current State:
- Time to build CRUD workflow: [X minutes]
- Systems accessed: [List]
- Context switches: [Number]
- Tribal knowledge dependencies: [Number]
- Authentication setup: [X minutes]
- Documentation sources: [List]

Observable Friction:
- [Quote or description of specific pain points]

Stakeholder Quote:
"[Capture any direct quotes about the difficulty or frustration]"

Target After Phase 2:
- Time to build CRUD workflow: <5 minutes total
- API discovery: <30 seconds
- Auth setup: <2 minutes
- Workflow construction: <5 minutes
- Systems accessed: 1 (Postman)
```

**4\. Use this data to inform Phase 1 planning:**

The systems they accessed during the Reverse Demo tell you exactly where API definitions need to be ingested from. If they checked AWS API Gateway, an internal wiki, and a Confluence page, those are your Phase 1 ingestion sources. 

The authentication friction they experienced tells you which auth patterns need guided setup in Phase 2, and the documentation gaps they hit tell you which request-level docs need to be prioritized.

## Why This Works

The Reverse Demo accomplishes four things simultaneously:

1. **Quantifies the baseline:** You now have objective data (time, systems, friction points) instead of subjective complaints.  
2. **Reveals ingestion sources:** You know exactly which systems contain the API definitions you need to consolidate in Phase 1\.  
3. **Creates empathy:** The customer sees that you're interested in understanding their real workflow, not just pitching features.  
4. **Builds the narrative:** When you show executives a 45-minute struggle compressed into 5 minutes, they understand the value immediately. No abstract ROI calculations needed.

The "before" state you document here becomes the anchor for every subsequent metric improvement you show in the build log. With this baseline, your Phase 2 results become real, tangible, and direct value delivery metrics.

# Appendix E: Using Postman Insights to Accelerate Path A

Postman Insights is a lightweight way to get automatic, per-endpoint error and latency visibility across services with minimal setup. Insights accelerates Path A by surfacing where to focus (endpoints with the highest error rates and latency), making failures reproducible (Repro Mode populates Request Builder from real user traffic), and providing alerting that meets teams where they already work (Slack). Reference: [Insights overview](https://learning.postman.com/docs/insights/overview/).

## What Insights Adds to Path A

- Insights shortens mean time to detection and diagnosis by providing automatic endpoint inference, error aggregation, and latency views with no custom dashboards.
- Repro Mode turns real failing calls into executable requests in Request Builder, so teams can diagnose and validate fixes faster within Postman.
- Alerts integrate with Slack to keep error-rate regressions visible without additional tooling.
- Insights complements (not replaces) Phase 1–4 work: it points to hotspots while Path A establishes the hub, consumable documentation, tests, and visibility.

## How to Set Up Insights (15 minutes)

**[Workspace admin role required]** Enable Insights in your team workspace and create one Insights project per service. Reference: [Insights overview](https://learning.postman.com/docs/insights/overview/).

**[Infra permissions required]** Deploy the Insights Agent alongside each service:

- Kubernetes (DaemonSet/sidecar): https://learning.postman.com/docs/insights/get-started/kubernetes/overview/
- AWS ECS: https://learning.postman.com/docs/insights/get-started/ecs/
- AWS EC2: https://learning.postman.com/docs/insights/get-started/ec2/
- AWS Elastic Beanstalk: https://learning.postman.com/docs/insights/get-started/beanstalk/

After deployment, verify endpoints appear in the Insights app. Use the Overview, Errors, Latency, and Endpoints tabs to confirm traffic is flowing and endpoint inference is active. Reference: [Insights app overview](https://learning.postman.com/docs/insights/reference/app/overview/).

**[Workspace admin role required]** Enable Repro Mode in the Insights project settings to replay failing calls with real request/response context. Reference: [Insights overview](https://learning.postman.com/docs/insights/overview/).

**[Slack permissions required]** Configure Alerts and connect to a monitored squad Slack channel so regressions surface immediately. Reference: Alerts tab docs: https://learning.postman.com/docs/insights/reference/app/alerts-tab/

## Mapping Insights to Path A Phases and Outcomes

**Phase 1: Get API Definitions Into Postman (Week 0–1)**

- Use the Endpoints tab to inventory discovered endpoints per service; filter by host/method/status to prioritize ingestion.
- Use “Save to Collections” from Insights (Endpoints) to seed canonical collections for top endpoints.
- Assign 2+ maintainers, configure environments (Dev/QA/UAT), and publish one stable collection.

Done when:

- [ ] Endpoints for the pilot service are discovered and visible in Insights
- [ ] Top endpoints saved to collections, published where appropriate
- [ ] Maintainers assigned; environments configured (baseline `baseUrl` and auth placeholders)

Build log artifacts:

- Screenshot: Insights Endpoints tab before/after
- Note: % of pilot service endpoints present in Postman

**Phase 2: Make It Consumable (Week 1–2)**

- For endpoints saved from Insights, add collection-level purpose/owner/auth, request-level parameter docs, and 3–5 examples (happy path, auth failure, validation error).
- Link to canonical docs and repos; publish stable APIs to the Private API Network if applicable.

Done when:

- [ ] Saved endpoints have owner/auth docs and examples
- [ ] Auth setup works in under 5 minutes
- [ ] New engineer can find and execute a target API in under 30 seconds

Build log artifacts:

- Screenshot: documented collection
- Quote: domain Tech Lead on onboarding speed improvement

**Phase 3: Activate Testing (Week 2–3)**

- Use Repro Mode to load real failing calls into Request Builder; save to collections and add assertions (functional, auth/error, chaining, performance smoke).
- Target 5–10 critical endpoints plus one E2E workflow.

Done when:

- [ ] Each Test Activation Matrix row covered at least once
- [ ] 5–10 endpoints instrumented with assertions; 1 workflow chained
- [ ] Failures produce clear messages locally

Build log artifacts:

- Screenshot: local run with assertions
- Note: tests added derived from Repro Mode specimens

**Phase 4: Make Results Visible (Week 3–4)**

- Turn on Insights Alerts to Slack for error-rate/latency regressions.
- Pair with CI/Monitors (outside Insights) to post test results to PR/MR or Slack.

Done when:

- [ ] Slack channel receiving Insights alerts
- [ ] At least one visibility channel active for tests/E2E workflow

Build log artifacts:

- Screenshot: Slack alert and/or PR/MR comment
- Screenshot: Insights Errors/Latency trend over time

**Phase 5: Prove It and Scale (Week 4+)**

- Use Insights trend charts (Errors, Latency) plus Path A adoption/automation metrics to complete the Readiness Scorecard.
- Present before/after evidence: discoverability time, error-rate reduction, latency improvement, and E2E reliability.

Done when:

- [ ] Readiness Scorecard criteria met
- [ ] Executive sponsor validates value; next domain selected

Build log artifacts:

- Screenshots: Insights Overview/Errors/Latency trend lines
- Summary table: before/after metrics with dates

## KPI Mapping: Where to See It in Insights

- Error rates (4xx/5xx) by endpoint/service: Errors tab (filter by timeframe, host, method)
- Latency (P50/P95/P99): Latency tab (watch for regressions after deploys/config changes)
- Endpoint coverage/hotspots: Endpoints tab (traffic, error concentration)
- Alerted incidents: Alerts tab and Slack channel history (detection speed, MTTR)
- Reproducible failures: Repro Mode sessions linked to specific errors (faster root cause and fix validation)

## Two- to Four-Week Domain Sprint with Insights (Overlay)

- Week 0 (Reverse Demo baseline): Time current discovery + CRUD flow; capture friction and screenshots for the build log (see Appendix D).
- Week 1 (Phase 1): Deploy Agent, confirm endpoint inference; save top endpoints to collections; assign maintainers; configure environments; publish first stable collection.
- Week 2 (Phase 2–3): Add owner/auth docs and examples; enable Repro Mode; convert failing calls into assertions across test types; wire one E2E workflow.
- Week 3 (Phase 4): Enable Alerts → Slack; make results visible in PR/MR or Slack via CI/Monitors.
- Week 4 (Phase 5): Compile Insights screenshots and Path A metrics; run the Readiness Scorecard; secure Domain 2.

## Troubleshooting and Tips

- No endpoints visible: Verify Agent is running and attached to the correct service/namespace; confirm traffic reaches the service.
- TLS/auth issues: Ensure certificates and proxy settings match environment; verify service egress allows the Agent’s required calls.
- Excessive path cardinality (e.g., IDs in paths): Rely on Insights’ endpoint inference to normalize paths (e.g., `/users/{userId}`) before saving to collections.
- Alert noise: Start with error-rate alerts only; tune thresholds and mute noisy endpoints; expand to latency once error rates stabilize.
- Data handling: Confirm org data policies allow Repro Mode in the selected environment before enabling.

## References

- Insights overview: https://learning.postman.com/docs/insights/overview/
- Insights app overview: https://learning.postman.com/docs/insights/reference/app/overview/
- Get started: Kubernetes: https://learning.postman.com/docs/insights/get-started/kubernetes/overview/
- Get started: AWS ECS: https://learning.postman.com/docs/insights/get-started/ecs/
- Get started: AWS EC2: https://learning.postman.com/docs/insights/get-started/ec2/
- Get started: Elastic Beanstalk: https://learning.postman.com/docs/insights/get-started/beanstalk/
- Alerts tab: https://learning.postman.com/docs/insights/reference/app/alerts-tab/