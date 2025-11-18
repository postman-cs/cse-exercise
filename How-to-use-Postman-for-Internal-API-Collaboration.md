# How to use Postman for Internal API Collaboration

Let’s look at what app-specific and reusable APIs mean for collaboration within Postman. Note that every sizeable company will have a mix of these.

**Pattern 1: Single-team collaboration - **App specific APIs rule within each team.

In this pattern, each team is building APIs mostly for themselves. These are app-specific APIs. Each API mirrors the application it is serving. In this pattern, if there are 100 teams, then each of them need to have a “hub workspace” where all of their APIs/services are documented and kept possibly with mocks, specs, tests, monitors etc. 

Individual teams collaborate on app-specific APIs.

*Guidance from Product: *Define a consistent workspace style guide and use cases for each of these teams. Depending on the tooling that a customer has adopted from Postman, users need to set up Collections, Specs, Mocks, Monitors, Perf Tests, Flows, Insights for their APIs. Customers need to Enforce RBAC and other rules using the Postman Enterprise plan for read/write access. Ensure that workspace descriptions and collections are well-documented. 

Use the prototype and iterate workflow frequently. Keep visibility open unless it is a private project. If you need to work closely with others on an API just enable real-time collaborative editing on requests called Live Sessions. This allows you multiple users to edit variables, run requests, and debug issues together, helping you get to 200s much faster.

Developers can also use the git integration to work within branches if working alongside code. Users can also set up the Slack and Jira integrations to connect to wider DevOps workflows. Developers might use their personal dev spaces along with team spaces to keep transient work separate. Customers can measure workspace adoption using reporting features of the platform.
note
*From the Field CTO: Examples where the pattern is applicable:*

**UPS**  UPS’ Solution Delivery Group has a big catalog of App Specific APIs. Teams have sponsorship to push “API product thinking” (reusable API thinking) deeper into the 5000-developer organisation with a legacy SOAP-UI, work within your teams, don’t work with others culture

**LogicMonitor**  
The monitoring platform’s entire UI is built on app-specific APIs—“almost every UI action is backed by an API, which btw is also made public to external customers, and has to be supported through the longtail

**Goodleap **  
Better intra-team collaboration now within some teams at Goodleap for App Specific APIs with Product & QE engineering working together to deliver the APIs

**RBC **Tonnes of teams building app-specific APIs, without any way to reuse.

**Uplight ** 
The energy-tech scale-up uses team or *private* workspaces for each vertical slice of the platform; engineers, embedded SDETs and PMs co-produce specs, collections and E2E tests inside the same space to “reduce bugs in production releases” and prototype new endpoints before any code is written.

*From the Field CTO: Examples where the pattern is applicable:*

**UPS** UPS | On-site | September 7, 2023 UPS’ Solution Delivery Group has a big catalog of App Specific APIs. Teams have sponsorship to push “API product thinking” (reusable API thinking) deeper into the 5000-developer organisation with a legacy SOAP-UI, work within your teams, don’t work with others culture

**LogicMonitor** LogicMonitor | Postcon | June 4, 2025 
The monitoring platform’s entire UI is built on app-specific APIs—“almost every UI action is backed by an API, which btw is also made public to external customers, and has to be supported through the longtail

**Goodleap **GoodLeap Build Test Deploy Workflow Implementation  
Better intra-team collaboration now within some teams at Goodleap for App Specific APIs with Product & QE engineering working together to deliver the APIs

**RBC **RBC | Postcon | June 3, 2025Tonnes of teams building app-specific APIs, without any way to reuse.

**Uplight **Uplight | Remote | Jan 31, 2024 
The energy-tech scale-up uses team or *private* workspaces for each vertical slice of the platform; engineers, embedded SDETs and PMs co-produce specs, collections and E2E tests inside the same space to “reduce bugs in production releases” and prototype new endpoints before any code is written.

**Pattern 2: Cross-team collaboration**

In this pattern, each team has their own hub, but there are also some workspaces for reusable APIs. Any team that is creating reusable APIs, creates a “Discovery workspace” and publishes the APIs they create for other teams to pick from. Consumer teams can “fork” a collection from the discovery workspace and work in their own hubs. So for 100 teams, and if 5 teams are publishing APIs for others, then there should be at least 105 internal workspaces. 

Teams contribute & consume shared APIs via discovery workspace. 

Partner and Public APIs are obvious examples of how internal teams can draw inspiration from and use them as reference points for internal APIs too.

*Guidance from Product: *Apply lessons from Pattern 1 but work on making “discovery workspaces” self-service. Have extensive documentation, onboarding guides, workspace updates, change management rules in place to make it easy for new developers to get started. Encourage *contract tests *to ensure that breaking changes do not happen for consumers. Assign maintainers for each workspace and use workspace updates to enforce change management. Users can also set up the Slack and Jira integrations to connect to wider DevOps workflows. Keep visibility open unless it is a private project.

Q3 Update
note
*From the Field CTO: Customer examples where the pattern is applicable*

**Fox ** 
Documentation and collaboration are critical to ensuring the efficiency of API usage across Fox’s thousands of engineers. To standardize workflows and avoid the chaos of disconnected processes, Fox has integrated Postman as a key cog in their development lifecycle. **All teams are required to create and share mock APIs in Postman, define contracts, and maintain fully functional workspaces**, instead of maintaining lengthy Confluence Pages. This has significantly **improved developer productivity and collaboration, transforming APIs into an accessible and powerful resource for the organization**. 

**Axis Bank ** 
Teams use collections “as a primary way of discovering and sharing APIs across teams” in shared workspaces

**Verizon ** Most people within the company don’t know that they have a “reusable” Identity API, so they just go ahead and build their own things.

*From the Field CTO: Customer examples where the pattern is applicable*

**Fox **Fox - December 2, 2024 
Documentation and collaboration are critical to ensuring the efficiency of API usage across Fox’s thousands of engineers. To standardize workflows and avoid the chaos of disconnected processes, Fox has integrated Postman as a key cog in their development lifecycle. **All teams are required to create and share mock APIs in Postman, define contracts, and maintain fully functional workspaces**, instead of maintaining lengthy Confluence Pages. This has significantly **improved developer productivity and collaboration, transforming APIs into an accessible and powerful resource for the organization**. 

**Axis Bank **Axis Bank | On-Site | September 25, 2023 
Teams use collections “as a primary way of discovering and sharing APIs across teams” in shared workspaces

**Verizon **Verizon | On-Site | April 8, 2024 Most people within the company don’t know that they have a “reusable” Identity API, so they just go ahead and build their own things.

**Pattern 3: Platform-wide collaboration** - Reusable APIs with a clear mandate to use them across the company. Other APIs with the same functionality *are not allowed to be created.*

In this pattern, there is a central platform team (or multiple teams) mandated to release APIs for the whole organization. This team does not create end-user applications but instead serves product teams that consume these APIs. 

The platform teams can create multiple workspaces. 

Everyone contributes & consumes shared APIs via multiple discovery workspaces. 

While platform teams work across these multiple workspaces, the best place for them to keep make these discoverable and consumable by other teams is through the Private API Network. The Private API network is not just a place for discovery but also to prevent duplicate work from happening. For example, a company might want to have only one Identity API.

Producers publish, consumers reuse — via Private API Network.

*Guidance from Product: *Apply lessons from 1 and 2 and correspondingly invest in the Private API Network to make it a place for self-service. Use the Promote and Manage change workflow. Keep visibility open by default. Users can also set up the Slack and Jira integrations to connect to wider DevOps workflows.
note
*From the Field CTO: Examples where the pattern is applicable:*

**Nationwide **  A central team is responsible for Building & buying the platforms and tools on top of which APIs are built, managed, discovered and distributed, along Enabling and governing teams that build APIs, with a purpose of externalization of key capabilities that they can then bring to Partners

**T-Mobile**    IT’s role as “systems integrator,” across all capabilities within the org; contract-driven development via Postman to impose company-wide standards so producers and consumers stay in sync.

**Crown Castle **  Primary objectives with the API program:

Catalog and document existing & future APIs to facilitate discovery, reduce duplicate work, and streamline collaboration

Enable the CCI’s teams to centralize and automate existing APIs processes from multiple protocols and a multi-cloud environments into a single platform

Support the teams and the business in its mission to mature their API program for system integration and customer experience

**Moneris**  The API-First initiative is a part of the CIO’s Cloud Transformation charter. An API Design Governance committee now *requires* teams to publish to the Private Network and adhere to a company-wide style-guide before other groups can safely consume their services.

**RBC**  **Finding the “right” API inside the bank** – they “struggle” to locate usable internal endpoints; discovery today happens by emailing colleagues or trawling repos, which leads to duplicate or stale APIs and slows delivery. **Ambitious developer-productivity mandate** – The DevOps & Insights team owns a target of CA $200M in savings by FY28; without streamlined API discovery, governance and automation, they risk missing that target. **No authoritative inventory for regulators** – The organization needs *breadth* (every API that exists) *and* *depth*(how each is built and secured) to satisfy looming Regulatory Audits, right now nothing exists

*From the Field CTO: Examples where the pattern is applicable:*

**Nationwide **Nationwide | On-site | July 11, 2023  A central team is responsible for Building & buying the platforms and tools on top of which APIs are built, managed, discovered and distributed, along Enabling and governing teams that build APIs, with a purpose of externalization of key capabilities that they can then bring to Partners

**T-Mobile** T-Mobile T-Mobile | Postcon | June 4, 2025  IT’s role as “systems integrator,” across all capabilities within the org; contract-driven development via Postman to impose company-wide standards so producers and consumers stay in sync.

**Crown Castle **Crown Castle | Remote | March 6, 2024  Primary objectives with the API program:

Catalog and document existing & future APIs to facilitate discovery, reduce duplicate work, and streamline collaboration

Enable the CCI’s teams to centralize and automate existing APIs processes from multiple protocols and a multi-cloud environments into a single platform

Support the teams and the business in its mission to mature their API program for system integration and customer experience

**Moneris** Moneris | On-site | July 13, 2023 The API-First initiative is a part of the CIO’s Cloud Transformation charter. An API Design Governance committee now *requires* teams to publish to the Private Network and adhere to a company-wide style-guide before other groups can safely consume their services.

**RBC** RBC | Postcon | June 3, 2025 **Finding the “right” API inside the bank** – they “struggle” to locate usable internal endpoints; discovery today happens by emailing colleagues or trawling repos, which leads to duplicate or stale APIs and slows delivery. **Ambitious developer-productivity mandate** – The DevOps & Insights team owns a target of CA $200M in savings by FY28; without streamlined API discovery, governance and automation, they risk missing that target. **No authoritative inventory for regulators** – The organization needs *breadth* (every API that exists) *and* *depth*(how each is built and secured) to satisfy looming Regulatory Audits, right now nothing exists

**Pattern 4: Project-level collaboration **- These should capture all other work and other types of collaboration like brainstorming, drafting, demos, etc.

Most companies might also just start with working on a project-basis with Postman or they might be moving from app-specific to reusable APIs. Or they might be going from an internal API to a public API. These temporary workspaces serve as places to get that work done *before the work is ready to be committed as an authoritative place.*

APIs are also often needed by non-technical audiences too and these workspaces help to serve for experimentation, demonstration, or learning. Project based workspaces can also help with that.

*Guidance from Product: *Keep them separate from 1-3. Ensure that their visibility stays private to not pollute the global namespace for workspaces.
note
*From the Field CTO: Examples where the pattern is applicable*

Most of the examples I have here are projects with specific external partners, leaving here for patterns that should apply internally as well but haven’t surfaced in our discovery since we don’t historically position the platform this way

**T-Mobile supply-chain modernization ** 
Contract-driven workspaces potentially enable parallel build between T-Mobile, Adobe, Salesforce and SI partners, avoiding two-week surprise regressions.

**Verizon × Mastercard**  enabling a unique offering for silent authentication for Mastercard on Verizon powered phones

**Atlassian x Stripe billing migration ** 
Consolidating *all* product lines onto a new Stripe-backed billing platform is a CEO-tracked OKR; success hinges on keeping a single, authoritative contract that dozens of internal and external teams rely on. Very much a project based entry with clear start & end dates

*From the Field CTO: Examples where the pattern is applicable*

Most of the examples I have here are projects with specific external partners, leaving here for patterns that should apply internally as well but haven’t surfaced in our discovery since we don’t historically position the platform this way

**T-Mobile supply-chain modernization **T-Mobile IT Leadership | Remote | May 7, 2024 
Contract-driven workspaces potentially enable parallel build between T-Mobile, Adobe, Salesforce and SI partners, avoiding two-week surprise regressions.

**Verizon × Mastercard** Verizon | On-Site | April 8, 2024 enabling a unique offering for silent authentication for Mastercard on Verizon powered phones

**Atlassian x Stripe billing migration **Atlassian | Bangalore | October 6, 2023 
Consolidating *all* product lines onto a new Stripe-backed billing platform is a CEO-tracked OKR; success hinges on keeping a single, authoritative contract that dozens of internal and external teams rely on. Very much a project based entry with clear start & end dates
