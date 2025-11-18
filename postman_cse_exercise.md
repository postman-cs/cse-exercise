# **Customer Success Engineer** 
# Implementation Exercise

Welcome! This exercise simulates a real enterprise adoption scenario where an initial IT-driven purchase solved compliance needs, but engineering teams haven't realized the platform's full value for daily workflows like API discovery and testing. The CSE role involves technical leadership: guiding customers through hands-on implementation while transferring knowledge so they can own the platform long-term. The ultimate goal is to transform Postman from a "check-the-box" tool into an indispensable part of their engineering process, securing renewals and expansions. Through this, you’ll have a chance to demonstrate your ability to plan and deliver technical value and narrative quickly.

**Key Concepts You'll Need:**

- **Spec Hub:** Postman's centralized repository for API specifications (OpenAPI, AsyncAPI) that serves as the single source of truth
- **Domain Sprint Model:** A focused, phased approach to organize and activate APIs in one business domain, then scale to others
- **Collection:** A group of API requests in Postman that can include tests, documentation, and workflows
- **Workspace:** A collaborative space in Postman for organizing collections, specs, and environments

**Helpful Resources:**
- [What is Postman?](https://www.postman.com/product/what-is-postman/)
- [Postman Learning Center](https://learning.postman.com/)
- [Postman Public Workspace](https://www.postman.com/postman/postman-public-workspace/overview) (Examples and API access)

## **Time Management Guidance:**
**We strongly encourage using AI coding assistants to accelerate your work.** This exercise is designed to evaluate your ability to plan, communicate, and demonstrate value; not how many hours you spend coding. Focus on quality of thinking and presentation over manual implementation.

**Recommended AI Tools (Free Tiers):**
- **[Gemini Code Assist / Gemini CLI](https://developers.google.com/gemini-code-assist)** (Free tier): 1,000 requests/day, 60 requests/minute
- **[Claude Code](https://docs.anthropic.com/en/docs/agents-and-tools/claude-code)** (Free tier, limited preview): Available on Claude Free plan
- **[OpenAI Codex via ChatGPT Plus](https://openai.com/codex/)** ($20/month): 30-150 messages per 5 hours

**Time Allocation (4-5 hours total):**
- **Phase 1 (Code artifact):** 1-2 hours (use AI to generate ingestion script or GitHub Actions YAML)
- **Phase 2 (Conceptual + show automation):** 1 hour (use AI to help structure workflow and create demonstration)
- **Phase 3 (Conceptual framework):** 30 minutes (use AI to generate test pattern examples)
- **Presentation Prep:** 1-2 hours (focus on storytelling, value articulation, ROI calculations)

**Key Point:** Spend your time on strategic thinking, presentation design, and value articulation - not on writing boilerplate code. Use AI to handle implementation details so you can focus on demonstrating CSE-level communication and customer enablement.

## **The Situation**

**Customer Profile:** Large financial services company  
**Contract:** $480K ARR, 2,000 seats (seats refer to licensed user accounts)  
**Timeline:** 72 hours to develop your implementation approach  
**Presentation:** 45 minutes (30 minutes presentation, 15 minutes Q&A)  

This customer represents a classic enterprise adoption scenario: An IT-driven purchase was levied to solve compliance needs, but we need to deliver meaningful value to engineering teams. Single Sign-On (SSO) works, user governance is in place, but developers are still spending hours searching through AWS consoles, internal wikis, and scattered documentation to locate and use APIs. We need to demonstrate measurable engineering value within the first 90 days before Postman becomes shelfware.

As the incoming CSE, your role is to lead the "Domain Sprint model": a focused, phased approach to quickly organize and activate APIs in one business domain (here, Payment Processing), then scale to others. The Customer Success Manager (CSM) has already identified the pilot domain and gained stakeholder approval. Your task is to demonstrate how you'll reduce API discovery time from hours to seconds, while creating scalable patterns for the rest of their domains.

## **What You've Discovered So Far**

The CSM has completed initial discovery interviews and audits. Here's the key technical context for your execution plan:

**Current Reality:**  
- 1,440 active users out of 2,000 seats (72% adoption rate, meaning most seats are in use but not necessarily for engineering value)  
- 413 shared workspaces (collaborative spaces in Postman for organizing API collections); these lack consistent structure, making navigation difficult  
- 2,918 shared collections (groups of API requests); many are single-request or very ad-hoc (one-off or improvised), with very few representing reusable, high-quality assets like documented workflows  
- Some CI/CD pipelines (Continuous Integration/Continuous Deployment—automated build and testing processes) in parts of the business run Postman collections, but they rely on static files (exported copies stored in repos), leading to version inconsistencies and maintenance headaches  
- Engineers report spending 2-4 hours to find and successfully call an internal API  
- 89% of collections have no tests; the few that do only check basic HTTP status codes like 200 (success)  

**Where Their APIs Live (Current Sources):**  
- Their API Gateway (their primary API management service; 70% of APIs are served here)  
- Confluence pages (internal wiki with mixed levels of documentation)  
- GitHub repositories (production code)  
- Tribal knowledge (informal info like "ask the platform team on Slack")  

**Their Build Pipeline (Development Workflow):**  
- GitHub for source code control  
- GitHub Actions for repo-level automation (this is where you'll integrate Postman automation)
- GitLab for build promotion (their existing CI/CD tool for deployment pipelines; partial API testing via static collections in some teams—you should discuss conceptually how Postman automation would integrate here, but it's not required for the exercise)
- AWS for deployment (API Gateway routes to serverless functions or containers)  
- Separate environments: Dev (development), QA (quality assurance), UAT (user acceptance testing), and Prod (production)  

## **Payment Processing Domain - Your Pilot**

This domain is your starting point to prove the approach's effectiveness before expanding to the other three business areas.

**Domain Profile:**  
- 47 REST APIs total (HTTP-based RESTful services)  
- 14-person engineering team (8 backend developers, 3 QA testers, 2 DevOps engineers, 1 manager)  
- Critical business workflow: Payment authorization > capture > refund (a key sequence for financial transactions)  
- All services deployed on AWS (via API Gateway to Lambda/ECS)  
- Authentication: OAuth 2.0 for external partners, JWT (JSON Web Tokens) for internal calls  

**What the Reverse Demo Revealed:**

During the baseline exercise, a senior engineer attempted to integrate with their refund API:  
- Took 47 minutes of a meeting to find and figure out how to utilize an unfamiliar service to craft a simple CRUD workflow (Create, Read, Update, Delete operations)  
- Accessed 6 different systems (AWS console, Confluence, GitHub, Slack, email, personal notes)  
- Hit 3 dead ends (outdated docs, broken auth example, wrong endpoint version)  
- Eventually found a working example in someone's personal Postman workspace  

Their QA lead admitted: "We know we should validate schemas (data structures) and test error scenarios, but figuring out how to set that up in Postman feels like its own project. So we just check for 200s and move on."  

Previous attempts at organization failed—they created a 'Payment APIs' workspace that splintered into divergent forks across the 413 shared workspaces. With 2,918 collections (mostly ad-hoc), reusable patterns are buried under noise, and reliance on static files in CI/CD worsens synchronization issues across teams.

**Constraints You'll Work Within:**
- Limited availability for co-working sessions with customer engineers (must maximize value in each session)
- GitHub Actions is where you'll implement Postman automation (repo-level integration); GitLab handles build promotion but should be discussed conceptually for future integration—not required for this exercise
- The 413 shared workspaces need rationalization — propose a consolidation strategy: which workspaces migrate to the new automation-enforced structure, which can be archived/deleted, and what governance ensures it doesn't splinter again

## **Your Assignment: 3-Phase Co-Execution Plan**

Outline how you'll execute the three phases for the Payment Processing domain. As CSE, you'll handle the hands-on technical work (e.g., building collections, writing tests) while the CSM manages stakeholder relationships and adoption metrics.

### **Phase 1: Single API Proof of Concept**

**Your Technical Execution Plan:**  

Focus on implementing **one critical API** (the Payment Refund API) end-to-end to prove the pattern before scaling to the remaining 46 APIs:  
- How will you get the Refund API OpenAPI spec? (Conceptual; for the exercise, use the provided sample OpenAPI spec for the Refund API. Your talk track should think about how this will work in production)  
- What's your approach for importing the OpenAPI spec into Spec Hub? (Use the [Create a Spec](https://learning.postman.com/docs/designing-and-developing-your-api/managing-apis/#creating-an-api) endpoint: `POST https://api.getpostman.com/specs?workspaceId={{workspaceId}}` to create the spec in Postman's Spec Hub)  
- How will you generate a collection from this spec? (Use the [Generate Collection from Spec](https://learning.postman.com/docs/designing-and-developing-your-api/developing-an-api/generating-collections-from-api-specifications/) endpoint: `POST https://api.getpostman.com/specs/{{specId}}/generations/collection` with proper generation options)  
- Show the workspace structure you'll establish (naming conventions, environment setup for Dev/QA/UAT/Prod - see [Using Workspaces](https://learning.postman.com/docs/collaborating-in-postman/using-workspaces/internal-workspaces/use-workspaces/))  
- Demonstrate implementing JWT auth for this API (pre-request scripts for token generation - see [Guided Auth documentation](https://learning.postman.com/docs/sending-requests/authorization/authentication-for-public-apis/))  

**Deliverables:**
1. **Conceptual slides** (2-3 slides) explaining:
   - The overall Phase 1 approach and why it matters
   - The workspace consolidation strategy (migration plan, governance model)
   - How this single-API pattern will scale to remaining 46 APIs

2. **Hands-on demonstration** with working code that:
   - Takes an OpenAPI spec as input (either AWS CLI export OR the provided sample spec file)
   - Creates the spec in Postman Spec Hub via API (`POST https://api.getpostman.com/specs?workspaceId={{workspaceId}}`)
   - Generates a collection from that spec (`POST https://api.getpostman.com/specs/{{specId}}/generations/collection`)
   - Configures environments (Dev, QA, UAT, Prod) with appropriate base URLs and auth
   - Shows the exact workspace topology (structure) with Spec Hub as the central source of truth
   
3. **Live walkthrough** showing:
   - How to run your ingestion script
   - What API calls it makes (show request/response examples)
   - The resulting workspace structure in Postman
   - The 30-second discovery experience you've created

**Note:** A sample OpenAPI specification for the Refund API is provided to eliminate AWS setup requirements and let you focus on the core Postman workflow. You may also demonstrate AWS CLI export if you have access.

**Note:** The single-API approach proves that:
- Specs in Spec Hub can serve as the single source of truth
- Collections can be generated and regenerated as specs evolve
- The pattern is repeatable for the remaining 46 APIs
- Engineers can immediately test and validate the approach  

**Success Metric:** Complete the Refund API ingestion in under 30 minutes, demonstrating the pattern that will scale to all 47 APIs  

### **Phase 2: Continuous Sync and Automation**

**GitHub Actions Integration:** (GitHub Actions handles repo-level automation where you'll integrate Postman; GitLab handles build promotion and should be discussed conceptually. See [Postman CLI Documentation](https://learning.postman.com/docs/postman-cli/postman-cli-overview/) for running collections via command-line)  

Create a workflow that automatically:
1. Detects when OpenAPI specs change via code commits
2. Updates the specs in Postman Spec Hub via API (`PUT` or `POST` to `/specs` endpoint)
3. Regenerates collections from updated specs (POST to `/specs/{{specId}}/generations/collection`)
4. Runs the collections using Postman CLI to validate changes (addressing static file limitations - see [CI/CD Integration](https://learning.postman.com/docs/collections/running-collections/running-collections-overview/))
5. Reports results (non-blocking initially - advisory mode that logs failures without halting builds)

**Where Results Surface:**
- PR comments via GitHub Actions (showing test pass/fail status) - primary integration point
- GitLab pipeline integration (discuss conceptually how results could surface in build promotion pipelines)
- Slack notifications for failures
- Optional: Postman Monitors as fallback - see [Monitoring APIs](https://learning.postman.com/docs/monitoring-your-api/intro-monitors/)

**Deliverables:**
1. **Conceptual slides** (2-3 slides) explaining:
   - Why automation infrastructure must come before test scaling
   - The sync workflow architecture (spec changes > Spec Hub updates > collection regeneration > test execution)
   - Where results surface (PR comments, Slack, etc.) and the non-blocking approach

2. **Demo-ready GitHub Actions YAML** that:
   - Fetches updated OpenAPI specs from source (AWS API Gateway export or GitHub repo)
   - POSTs/PUTs to Postman API to update specs in Spec Hub
   - Triggers collection regeneration from updated specs
   - Runs collections via Postman CLI (`postman collection run` with collection ID)
   - Can be theoretical but must be logically sound and demonstrate understanding of the sync workflow

3. **Show the automation in action** (can use screenshots, recorded demo, or a live walkthrough):
   - **Trigger demonstration:** Show what happens when a spec file is pushed to the repo (GitHub Actions starts automatically)
   - **Workflow execution:** Walk through each step in the YAML and show what it does (can use GitHub Actions logs/UI screenshots)
   - **Results output:** Show example PR comments, Slack notifications, or workflow summaries that surface test results
   - **Compare before/after:** Contrast the old way (manually updating static files) vs. the new automated sync
   - **Key point:** Demonstrate that this runs automatically on code pushes, not manually triggered scripts

**Note:** Mention that establishing this automation infrastructure early ensures that test suites have a proper place to live; when tests are added in Phase 3, they can be automatically run as part of the workflow. 

### **Phase 3: Documentation and Testing Strategy (Conceptual Discussion)**

**Documentation Approach:**  
Discuss (conceptually) how you'll scale documentation and testing across all 47 APIs:  
- Template for collection-level documentation (README-style overviews with prerequisites and usage - see [Documenting Collections](https://learning.postman.com/docs/publishing-your-api/documenting-your-api/))  
- Strategy for implementing guided auth patterns across OAuth 2.0 (external partners) and JWT (internal) APIs - see [Authorizing Requests](https://learning.postman.com/docs/sending-requests/authorization/authorization/)  
- Approach for handling different response scenarios using [Environment Variables](https://learning.postman.com/docs/sending-requests/variables/environment-variables/) across Dev/QA/UAT/Prod  

**Test Activation Strategy:**  
Outline your conceptual approach for test implementation across the 47 APIs:  
- **Functional smoke tests:** Beyond status codes, verify critical response fields (e.g., refund ID, transaction status - see [Test Script Examples](https://learning.postman.com/docs/tests-and-scripts/write-scripts/test-examples/))  
- **Schema validation tests:** Ensure responses match expected JSON structure - see [Validating Response Structure](https://learning.postman.com/docs/tests-and-scripts/write-scripts/test-examples/#validate-response-structure)  
- **Error scenario coverage:** Strategy for handling 401 unauthorized, 400 bad request, 500 server error across all APIs  
- **Integration chaining patterns:** How you'll pass data between sequential requests (e.g., auth token reuse - see [Using Variables in Scripts](https://learning.postman.com/docs/tests-and-scripts/write-scripts/variables-in-scripts/))  
- **E2E workflow testing:** Approach for the payment flow (authorization > capture > refund sequence)

**Deliverables:**
1. **Conceptual slides** (3-4 slides) explaining:
   - The documentation and testing strategy across all 47 APIs
   - How patterns extend from single endpoints to full workflows
   - Team training approach and timeline for activation
   - How this builds on Phase 1 workspace structure and Phase 2 automation

2. **Conceptual examples** (no hands-on code required, but show the patterns):
   - Reusable test script templates (JavaScript using `pm.test()` - see [Writing Tests](https://learning.postman.com/docs/tests-and-scripts/write-scripts/intro-to-scripts/))
   - Documentation standards for collections
   - Schema validation approach
   - Error scenario coverage strategy
   - How you'll train the team to apply these patterns to remaining APIs

**Note:** With workspace structure (Phase 1) and automation (Phase 2) in place, test suites can be housed in the proper, discoverable locations and be invoked automatically via CI/CD pipelines.  

### **The (Hypothetical) Build Log You'll Create**

A "build log" is an internal Postman record of adoption progress, used to track metrics and share success stories. Show the entry you'll create for this domain:  

```
Domain: Payment Processing
Timeline: Week 1 (Phase 1), Week 2 (Phase 2), Week 3 (Phase 3), Week 4 (Scale)
Team Size: 14 engineers
APIs: 1 in Phase 1 (Refund API), 47 total by Week 4

Phase 1 (Week 1):
- Single API (Refund) ingested into Spec Hub: [Time taken]
- Collection generated and environment configured: [Time taken]
- Workspace consolidation strategy established: [Success/Challenges]
- Pattern validated and documented: [Success/Challenges]

Phase 2 (Week 2):
- GitHub Actions workflow deployed: [Status]
- Automated sync implemented: [Frequency of updates]
- Collections automatically regenerated from spec changes: [Success rate]

Phase 3 (Week 3):
- Documentation and testing strategy defined: [Framework created]
- Team training completed: [Number of engineers trained]
- Test templates deployed into organized workspaces: [Number of reusable templates]
- Tests automatically run via Phase 2 CI/CD: [Initial pass/fail rates]

Before:
- 47-min discovery time for unfamiliar APIs
- Ad-hoc collections dominating 2,918 total collections
- 89% of collections have no tests
- Static file dependency in CI/CD causing sync issues

After (Projected by Week 4):
- Under 30-sec discovery via organized Spec Hub + Collections
- Single source of truth (Spec Hub) with auto-generated collections
- 70%+ test coverage with schema validation
- Automated sync workflow eliminating static file issues

Business Impact:
- Time savings: 14 engineers × 2-4 hours saved per API discovery
- Quality improvement: From 11% to 70%+ test coverage
- Reduced tribal knowledge dependency: APIs discoverable without Slack searches

Quote You'll Capture:
- Engineer testimonial on transformation from 47-minute discovery to seconds
- QA lead feedback on test activation without "its own project" overhead
```

## **Presentation Format**

Your 30-minute presentation should follow this structure (tailored for a panel evaluating your technical and customer-facing skills):

### **Opening: The Baseline (5 minutes)**
- Walk through the 47-minute reverse demo struggle  
- Frame the problem: Despite strong seat activation, ad-hoc collections and a lack of integration signal untapped potential 
- **Sell the vision:** Transform Postman from ad-hoc execution tool to a shared asset repositoriy and engineering accelerator, proving measurable ROI
- **Calculate and articulate the cost:** 14 engineers × 2 hours per API discovery × ~2 discoveries/week = ~$437K/year in lost productivity (at $150/hr engineer rate). Highlight how 72% seat adoption masks low engineering ROI—high usage but low business value.


### **Core: Your 3-Phase Co-Execution Approach (20 minutes)**

**Phase 1: Single API Proof of Concept (Week 1)**
- Show commands/scripts: POST to Spec Hub API > POST to Generate linked collection
- **Demonstrate workspace consolidation strategy:** Discuss how to migrate from ad-hoc workspaces to organized domain-based structure (e.g., "Payment Processing - Production" workspace), what criteria determines preservation vs. archival, and what governance (naming conventions, access controls) prevents future sprawl
- Show the 30-second API discovery experience you'll create (search for workspace, view generated collection, run request)
- **Articulate the value:** Reducing discovery time delivers immediate ROI—project $280K annual savings (14 engineers × 3 hours saved/week × $150/hr × 52 weeks) and positions Postman as essential within 90 days
- Prove the pattern works before scaling to remaining APIs

**Phase 2: Continuous Sync and Automation (Week 2)**
- Present GitHub Actions workflow concepts
- **Walk through the workflow:** Demonstrate (via screenshots, recorded demo, or talk-through) what happens when code is pushed to the repo
- **Compare before/after:** Show the old way (manual static file updates causing sync issues) vs. the new automated approach
- **Sell the infrastructure value:** Automation infrastructure and workspace structure should be in place before scaling tests; why?

**Phase 3: Documentation and Testing Strategy (Weeks 3-4)**
- Present conceptual framework for scaling across other APIs
- Discuss reusable test script templates (e.g., schema validation pattern using `pm.test`)
- Outline documentation standards and team training approach
- Show how patterns extend beyond single endpoints to full workflows: demonstrate how the same testing/documentation approach applies to the complete payment lifecycle (authorization API > capture API > refund API in sequence), validating that data passes correctly between services
- **Connect to business impact:** With workspace structure (Phase 1) and automation (Phase 2) in place, test templates deploy to organized, discoverable locations and can run automatically. Elevating coverage and discoverability reduces QA hours and accelerates releases, directly demonstrating measurable engineering productivity gains. 

### **Close: The Path Forward (5 minutes)**
- **Week 4 and Beyond:** Show how the proven pattern scales from 1 API to all APIs and other domains.
- **90-Day Success Metrics:** Present the key indicators you'll track to prove transformation from seat adoption (compliance-driven) to engineering engagement (value-driven):
  - API discovery time: ~ an hour > 30 seconds
  - Test coverage increases on shared collections, increases in collection runs on shared collecitons rather than new ones created ad-hoc
  - Workspace sprawl: 413 ad-hoc > organized domain structure
  - CI/CD integration: static files > automated sync
- **Handoff Strategy:** Explain how you'll ensure the customer's team owns this independently by Day 90; what documentation, training, and checkpoints ensure they don't need ongoing CSE support

## **What We're Looking For**

**Technical Execution:**  
Can you actually perform the work? Choose when and where to demonstrate, but the full presentation should have both conceptual framing and a level of demonstration:
- **Phase 1:** Conceptual slides explaining the approach + hands-on demonstration with working ingestion script
- **Phase 2:** Conceptual slides explaining the automation architecture + a discussion of how to achieve it with GitHub Actions YAML
- **Phase 3:** Conceptual slides with example test patterns

You must deliver ONE fully working code artifact (Phase 1 script). The other phase can be demonstrated conceptually with pseudocode or theoretical structure. Reference: [Postman API](https://learning.postman.com/docs/developer/postman-api/make-postman-api-call/) for programmatic access to specs, collections, and workspaces.

**Pattern Thinking:**  
Does your single-API approach (Phase 1) create a repeatable template that scales? Starting with one API and workspace structure proves the pattern quickly. The automation infrastructure (Phase 2) eliminates manual repetition. The test framework (Phase 3) leverages the organized structure. Explain how this accelerates Domains 2-4: Domain 1 takes 3 weeks, Domain 2 takes 1 week, Domain 3 is self-sufficient.

**Co-Execution Mindset:**  
You're not just advising; you're partnering hands-on with the customer's engineers. Phase 1 is pair-programming (you build together). Phase 2 is knowledge transfer (they learn the framework). Phase 3 is automation (they maintain independently). How will you ensure they own the pattern by Week 4?

**Metrics That Matter:**  
Focus on: (1) Phase 1: time to ingest single API (target: under 5 min) and workspace consolidation progress, (2) Phase 2 - automated sync frequency and collection regeneration success rate, (3) Phase 3 - test template adoption rate and coverage improvements. Track discoverability time (47 min > X min), test coverage (11% > X%), and CI/CD evolution (static files > dynamic sync). Show how you'll track what prevents shelfware and drives 90-day value adoption.

**Value-Selling and Vision Articulation:**  
Demonstrate your ability to connect technical execution to business outcomes—the core of CSE success. Your presentation must clearly articulate: (1) ROI projections tied to the $480K ARR renewal decision (quantify time/cost savings), (2) How technical wins (e.g., 30-sec discovery, 70% test coverage) translate to executive-level value (productivity gains, risk reduction), (3) The transformation narrative: Postman evolving from compliance tool to engineering accelerator, (4) Evidence of customer buy-in through testimonials/quotes showing engineering adoption. This competency will be scored separately (20% of evaluation) to ensure you can sell vision and demonstrate value, not just implement solutions.

## **Submission**

**Required:**  

1. **Presentation deck** (30 minutes + 15 minute Q&A) that includes:
   - **Phase 1:** 2-3 conceptual slides + hands-on demonstration/walkthrough
   - **Phase 2:** 2-3 conceptual slides + theoretical code snippets or hands-on demonstration
   - **Phase 3:** 3-4 conceptual slides (no hands-on required, but show example patterns)
   - Opening and closing sections per the format above

2. **Choose ONE code artifact** for hands-on demonstration:
   - **Option A (Phase 1):** Ingestion script (Python/Bash/Node.js) that takes OpenAPI spec as input and makes Postman API calls to create spec and generate collection, OR
   - **Option B (Phase 2):** GitHub Actions workflow YAML file implementing the full sync workflow (spec update > collection regeneration)
  
   **Important:** You only need to deliver one working code artifact. The other phase can be demonstrated with conceptual slides showing the approach, pseudocode, or theory.

**What "Hands-On Demonstration" Means:**
- For your chosen code artifact (Phase 1 or Phase 2), you should:
  - Show the actual code/YAML during presentation
  - Walk through what each section does
  - Explain the API calls being made (request/response examples)
  - Demonstrate the output/results (can be screenshots, recorded demo, or live if feasible)

## **Supplementary Materials Provided**

To eliminate setup barriers, a sample spec is provided:

**Sample OpenAPI Specification:**
- **File:** `payment-refund-api-openapi.yaml` - A complete OpenAPI 3.0 specification for the Payment Refund API
- **Endpoints included:**
  - `POST /refunds` - Create refund (full or partial)
  - `GET /refunds` - List refunds with filtering and pagination
  - `GET /refunds/{refundId}` - Get refund details with status history
  - `GET /refunds/{refundId}/status` - Get lightweight refund status
  - `POST /refunds/{refundId}/cancel` - Cancel pending refund
  - `GET /health` - Service health check

This allows you to focus on demonstrating your understanding of the Postman workflow (Spec Hub > Collection Generation > Testing > CI/CD) rather than spending time on AWS CLI setup or API Gateway access.

**If you have AWS experience:** You're welcome to demonstrate the full AWS CLI export process as a bonus, but it's not required for success.  

## **The Bar for Success**

**Good:** Your code works; it successfully demonstrates the core workflow. You can explain what you built and walk through how it functions. Your presentation covers all three phases with basic explanations. You answer questions directly about your implementation. Your conceptual demonstration of the other phase shows you understand the workflow, even if it lacks depth. 

The presentation is functional but may be more surface-level than actionable. With CSE guidance, your plan would succeed.

**Great:** Your code works and your presentation is clear and well-structured. You explain *why* you made technical choices and can discuss trade-offs thoughtfully. Your presentation demonstrates customer empathy, you frame solutions from the user's perspective, and you connect technical work to the problems it solves. Your conceptual demonstration of the other phase is logically sound and shows you understand integration points and workflow dependencies. You articulate how all three phases connect together, and your consolidation strategy includes clear reasoning that shows strategic thinking. 

Your Phase 3 framework demonstrates how patterns would scale and enable the team. You communicate effectively during Q&A, showing you can translate technical concepts clearly. Domain 2 would accelerate significantly using your approach. You're a force multiplier who can communicate value.

**Exceptional:** Your code works and your presentation is exceptional. You tell a compelling story that connects technical execution to business outcomes. You articulate ROI and value clearly ("This automation saves X hours per week," "Reducing discovery time from 47 minutes to 30 seconds delivers $280K annual value"). You anticipate questions and address edge cases proactively in your presentation. Your conceptual demonstration of the other phase shows sophisticated understanding; you've thought through scalability and integration complexity. 

Your workspace consolidation strategy includes migration plans. Your Phase 3 framework includes training considerations and ideas for enablement materials that show you understand customer success. You articulate how all three phases connect as an integrated system. You connect technical solutions to business impact throughout the presentation. Your approach demonstrates true CSE-level thinking: clear communication, strategic value articulation, customer enablement, and the ability to translate technical work into business outcomes.  

## **Why This Exercise Matters**

These enterprise customers begin here: IT achieved compliance (e.g., high seat adoption), but engineering faces fragmented tools (ad-hoc collections, static CI/CD), risking Postman becoming shelfware. Without demonstrating fast, tangible engineering value within 90 days, customers may abandon the platform or reduce spend.

Your execution in the first domain decides whether they see Postman as essential. Succeed, and you establish momentum for broader adoption and long-term value. Fail, and we're explaining why 72% adoption with minimal reusable assets justifies continued investment.  

Show us you can make Postman essential to their success.

## **Key Documentation References**

**Core Platform:**
- [Postman Learning Center](https://learning.postman.com/) - Complete documentation hub
- [What is Postman?](https://www.postman.com/product/what-is-postman/) - Platform overview
- [Postman Collections Overview](https://learning.postman.com/docs/collections/collections-overview/) - Organizing API requests
- [Using Workspaces](https://learning.postman.com/docs/collaborating-in-postman/using-workspaces/internal-workspaces/use-workspaces/) - Team collaboration

**API Ingestion & Import:**
- [Managing APIs and Spec Hub](https://learning.postman.com/docs/designing-and-developing-your-api/managing-apis/) - Creating and managing specs
- [Create a Spec Endpoint](https://www.postman.com/postman/postman-public-workspace/request/12959542-5fbbc5ec-d156-41e0-aa5c-d76b1f5bca03) - POST `/specs?workspaceId={{workspaceId}}` for importing OpenAPI/AsyncAPI
- [Generate Collection from Spec](https://learning.postman.com/docs/designing-and-developing-your-api/developing-an-api/generating-collections-from-api-specifications/) - POST `/specs/{{specId}}/generations/{{elementType}}`
- [Postman API Documentation](https://learning.postman.com/docs/developer/postman-api/make-postman-api-call/) - Programmatic access
- [Postman Public Workspace](https://www.postman.com/postman/postman-public-workspace/overview) - API examples and reference collections

**Authentication:**
- [Authorizing Requests](https://learning.postman.com/docs/sending-requests/authorization/authorization/) - OAuth 2.0, JWT, and more
- [Guided Auth for Public APIs](https://learning.postman.com/docs/sending-requests/authorization/authentication-for-public-apis/) - Simplified auth setup
- [Variables in Scripts](https://learning.postman.com/docs/tests-and-scripts/write-scripts/variables-in-scripts/) - Dynamic token management

**Testing & Scripts:**
- [Writing Test Scripts](https://learning.postman.com/docs/tests-and-scripts/write-scripts/intro-to-scripts/) - `pm.test()` and assertions
- [Test Script Examples](https://learning.postman.com/docs/tests-and-scripts/write-scripts/test-examples/) - Practical test patterns
- [Validating Response Structure](https://learning.postman.com/docs/tests-and-scripts/write-scripts/test-examples/#validate-response-structure) - Schema validation
- [Environment Variables](https://learning.postman.com/docs/sending-requests/variables/environment-variables/) - Managing test data

**CI/CD Integration:**
- [Postman CLI Overview](https://learning.postman.com/docs/postman-cli/postman-cli-overview/) - Command-line interface
- [Running Collections in CI/CD](https://learning.postman.com/docs/collections/running-collections/running-collections-overview/) - Automation patterns
- [Monitoring APIs](https://learning.postman.com/docs/monitoring-your-api/intro-monitors/) - Scheduled test runs

**Documentation:**
- [Documenting Collections](https://learning.postman.com/docs/publishing-your-api/documenting-your-api/) - Auto-generated API docs