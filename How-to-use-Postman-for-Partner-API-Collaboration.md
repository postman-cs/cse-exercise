# How to use Postman for Partner API Collaboration

Partner APIs serve as a crucial middle ground between internal and public APIs. They are shared externally like Public APIs but are restricted to a select group of authorized partners, providing a much higher level of security, control, and governance. This controlled environment enables companies to share more sensitive data, offer advanced functionality, and provide opportunities for companies to monetize their APIs. 

Additionally, this positioning plays a strategic role in the API lifecycle. A company may initially release an API to a few trusted partners to gather feedback, refine its functionality, and validate its business value before considering a broader public launch (Examples: LinkedIn, Autodesk).

Let’s look at how different partner API patterns show up in Postman—and what guidance we recommend depending on the type of relationship. 
Pattern 1: API as a Products
One-way publishing – You’re the provider.
In this model, your teams own the APIs and share them with partners who are consumers. The collaboration is one-directional: you publish, they consume.

Use **Partner workspaces** to curate collections, reference implementations, specs, and documentation for external consumption. These sit alongside your **internal team spaces** that own the logic. All collections are pushed into the shared partner space.

These are read-only or lightly interactive workspaces. You own the source of truth; partners work off it in their own Postman instances.

Internal teams push collections into a shared Partner workspace, which is read by multiple external partner teams in their own Postman instances.

*Guidance from Product: *

Tiered onboarding collections that guide partners to integrate and hit value state faster

Pathways to Integrate: use the API and take it from sandbox → production

Flows & Visualizations to increase accessibility

“Run in Postman” buttons embedded in partner portals/docs.

RBAC + Tokens scoped per partner

Usage reporting dashboards shared with partner success teams
note
*From the Field CTO: Examples where the pattern is applicable*

Nationwide – insurance APIs offered as Products through a 5-tiered support model (e.g., Rivian checkout embeds policy purchase). Tiers from 0 (self-serve) to 4 (white glove, integration engineer supported)  

NFL – content & data APIs provided to licensed broadcast / media partners to power real-time stats, fantasy football, highlight reels, etc  

Verizon, T-Mobile, AT&T (Telecom APIs) - highly regulated, public APIs are a risk, exposed to partners like MLB  

Citi - Customers of CitiConnect APIs, enabling Payments/Treasury use cases . Takes months to onboard partners. 

Also, see AWS Talk on success metrics: https://www.youtube.com/watch?v=zGhhgfMK3Co 

*From the Field CTO: Examples where the pattern is applicable*

Nationwide – insurance APIs offered as Products through a 5-tiered support model (e.g., Rivian checkout embeds policy purchase). Tiers from 0 (self-serve) to 4 (white glove, integration engineer supported) Nationwide | On-site | July 11, 2023 

NFL – content & data APIs provided to licensed broadcast / media partners to power real-time stats, fantasy football, highlight reels, etc NFL | Remote | March 26, 2024 

Verizon, T-Mobile, AT&T (Telecom APIs) - highly regulated, public APIs are a risk, exposed to partners like MLB T-Mobile | In-Person | Feb 21, 2024 

Citi - Customers of CitiConnect APIs, enabling Payments/Treasury use cases Citibank | NYC | June 26, 2024. Takes months to onboard partners. 

Also, see AWS Talk on success metrics: https://www.youtube.com/watch?v=zGhhgfMK3Co 

Pattern 2: Partner-specific APIs
Bi-directional collaboration – You’re both building to integrate. 
Use a **Partner space** to co-build the integration and coordinate on contract changes. The workspace serves as the bridge between your Postman instance and the partner’s instance. Both sides can maintain their own Dev, QA, or Project spaces, while the Partner space reflects what’s being agreed upon.

Internal teams push collections into a shared Partner workspace, which is read members of the definition partner’s teams. 

*Guidance from Product: *

**Design-first APIs ** – Prototype and Iterate workflows to allow for Parallel development

Mocks/Sandboxes & Prod environments shared for early parallel development and staged rollout.

Contract Testing between Producer and Consumer of APIs

Mock servers for partner dev teams to start integration immediately.

Contract tests & monitors to guard against breaking changes.

Workspace notifications piped to Slack / Jira for real-time alignment.

**Integration Testing** - that span multiple vendor mocks to validate end-to-end flows early.
note
*From the Field CTO: Examples where the pattern is applicable*

**Atlassian × Stripe billing migration** – Atlassian’s home-grown billing platform accumulated more than a decade of product-led-growth experiments—tiered SKUs, usage-based add-ons, legacy proration rules, internal credit systems, and bespoke discount logic across Jira, Confluence, Bitbucket, Trello, etc. is now being replaced by Stripe.

Retiring that platform and converging on Stripe Billing is a top-three company objective, tracked at the CEO and board level, to cut maintenance cost, speed new-commerce features, and simplify global payments.  

**T-Mobile IT transformation**: replacing home-grown systems with Amdocs (billing), Salesforce (CRM), Adobe Experience Manager etc. Each vendor must expose new or modified endpoints for T-Mobile-scale use cases, and those endpoints must interoperate through a T-Mobile led SI team, which owns the integration layer   

*From the Field CTO: Examples where the pattern is applicable*

**Atlassian × Stripe billing migration** – Atlassian’s home-grown billing platform accumulated more than a decade of product-led-growth experiments—tiered SKUs, usage-based add-ons, legacy proration rules, internal credit systems, and bespoke discount logic across Jira, Confluence, Bitbucket, Trello, etc. is now being replaced by Stripe.

Retiring that platform and converging on Stripe Billing is a top-three company objective, tracked at the CEO and board level, to cut maintenance cost, speed new-commerce features, and simplify global payments. Atlassian | Bangalore | October 6, 2023 

**T-Mobile IT transformation**: replacing home-grown systems with Amdocs (billing), Salesforce (CRM), Adobe Experience Manager etc. Each vendor must expose new or modified endpoints for T-Mobile-scale use cases, and those endpoints must interoperate through a T-Mobile led SI team, which owns the integration layer T-Mobile IT Leadership | Remote | May 7, 2024 T-Mobile | Postcon | June 4, 2025 

Pattern 3: Customised Public APIs
Program-level enablement – You're enabling many partners through a common API.
**Highly reusable, public-facing APIs but also customizable for partner needs**

A product team builds and maintains a public or partner-facing API platform. Dozens—or hundreds—of partners build on top of it. These APIs are reusable and governed: you can’t have five different versions of the same functionality.

Use a **Public Workspace** to represent your company’s developer-facing presence. Then create **Partner spaces** for each key partner or channel. These partner workspaces can be more tailored—e.g., you might customize environments or walkthroughs per partner.

Internal teams push collections to the Public API Network, from which dedicated partner workspaces can read for customised APIs.

*Guidance from Product: *

**Public Workspace** – open to anyone; rich docs, sample envs, mock servers, example collections and flows 

**Partner Workspace(s)** – Forked from canonical collections but scoped to one customer; includes guided “next-step” flows, custom credentials in environment, and demo assets (collections, flows)

**Post-Sales Partner Workspaces** – Contract tests, future change requests, feedback etc.
note
*From the Field CTO: Examples where the pattern is applicable*

**Meta – WhatsApp Business Platform**: Public Postman workspace exposes Cloud, Management & Flows APIs; devs can send test messages in minutes.

**PLG Funnel**: Meta instruments workspace telemetry (forks, successful calls) to spot businesses that reach a clearly defined value state

Sales teams invite those accounts into **partner workspaces** for tailored demos, and guided flows—shortening the sales cycle

After purchase, solution-architect teams / support engineers stay in the same workspace, co-designing deeper integrations or helping out with Support

**Salesforce, Paypal, Intuit **have similar stories.

*From the Field CTO: Examples where the pattern is applicable*

**Meta – WhatsApp Business Platform**: Public Postman workspace exposes Cloud, Management & Flows APIs; devs can send test messages in minutes.

**PLG Funnel**: Meta instruments workspace telemetry (forks, successful calls) to spot businesses that reach a clearly defined value state

Sales teams invite those accounts into **partner workspaces** for tailored demos, and guided flows—shortening the sales cycle

After purchase, solution-architect teams / support engineers stay in the same workspace, co-designing deeper integrations or helping out with Support

**Salesforce, Paypal, Intuit **have similar stories.
