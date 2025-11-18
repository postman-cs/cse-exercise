# How to use Postman for API Governance

## Governance for App-Specific APIs

App-specific APIs are typically built for a single consumer, such as a specific UI or integration. These APIs are developed quickly to meet project demands and are often tightly coupled with the consuming application. As a result, the API specification is often minimal and utility-driven. In many cases, the specification is generated post-implementation to support gateway configuration, authentication, and rate-limiting tasks. Collections play a much larger role in the development workflow at this stage.

Using Postman, teams working with app-specific APIs benefit most from leveraging **Collections** to prototype APIs, run tests, mock endpoints, set up monitors, and share behavior across backend and frontend teams. Collections enriched with **Type information** add structured request and response formats that enhance clarity even before formal specifications are written. Since there is typically only one consumer, feedback loops are short and changes happen quickly.

**How to use Postman for API governance in this context:**

Start by building collections to define and test functionality. Enhance these collections with **Type information** to ensure accurate request/response structures. Use mock endpoints to unblock frontend or integration development early. Postman **Workspaces** enable backend and frontend teams to iterate quickly and collaborate in real time. Once validated, specifications can be generated post-implementation for gateway configuration or compliance needs—providing a smooth path from prototyping to structured delivery.

Governance is **lightweight and execution-focused**, typically centered on schema validation and authentication checks. Assign governance rulesets at the workspace or workspace group level to apply essential checks without slowing development. Store specs in **Spec Hub** as the centralized deployment reference, and integrate them into CI/CD pipelines using the Postman API.

Use **spec-level governance reports** to validate readiness with inline annotations. Combine this with **Postman CLI** to enforce governance in CI/CD pipelines and catch non-compliance early, helping teams move quickly without compromising on standards.

Governance workflow for App-specific APIs

## Governance for Reusable APIs

Reusable APIs are designed for broader consumption across teams, partners, or external developers. Unlike app-specific APIs, they prioritize scale and long-term maintainability. In Postman, reusable APIs lead to a **rich specification**, often authored directly in the Spec Designer using OpenAPI 3.0 or AsyncAPI 2.0 or generated from a consumer validated collection. These specs define consistent structure, naming, data models, and error handling.

Collections are equally critical—used for testing, mocking, onboarding, and monitoring. When paired with **Type information**, they validate design accuracy and ensure consistent behavior across consumers. Typed collections act as executable references that clarify how APIs are meant to be used.

**How to use Postman for API governance in this context:**

Begin by designing the API in **Postman’s Spec Designer** or by iterating with typed collections to explore endpoint behavior. Even when starting with a spec, generate collections to validate against real usage and gather early feedback. After validation, refine the spec or generate it from the collection—ensuring it reflects actual usage and meets internal standards.

Use the **Governance rule editor** to apply **Spectral-based rulesets** that enforce consistent standards—naming conventions, schemas, error formats, and more. These are critical for APIs used across teams and organizations. Early governance helps teams uncover design issues sooner and makes APIs more predictable and maintainable. Rulesets can be scoped at the account, workspace group, or individual workspace level to align with your org’s API strategy. Finalized specs should be stored in **Spec Hub** as the single source of truth.

Ensure continuous compliance with **Postman CLI** by embedding governance checks in CI/CD pipelines. These checks validate reusable APIs before broader publication and prevent promotion of non-compliant changes.

Use **Workspaces** to onboard internal teams, partners, or external developers via shared typed collections, mock servers, and docs. Workspaces also support **change management**—as APIs evolve, teams can update collections, notify consumers via workspace updates, and ensure alignment in real time.

Governance workflow for Reusable APIs

## Transitioning from App-Specific to Reusable APIs

For organizations evolving from app-specific to reusable APIs, Postman supports this transformation through a staged governance model:

Start by selecting a subset of APIs designated to become reusable—managed within **dedicated workspaces**.

Define governance standards using spectral rules for these APIs, including naming, schemas, error formats, and security.

Apply **lighter rulesets** to app-specific APIs and **stricter rules** to reusable ones, using workspace groups to manage enforcement scope.

Have development teams update API specs in the designated workspaces to meet reusable standards.

Run conformance checks on these workspaces using Postman’s governance tooling, while applying lighter checks to app-specific APIs.

Enforce governance policies via **CLI-based automation** and monitor program maturity through **governance overview reports**.

Use **workspace updates** to manage and communicate API changes as they mature from app-specific to reusable.

Postman enables organizations to turn APIs into reliable, scalable products. Governance becomes a deliberate and structured discipline, ensuring APIs are secure, consistent, and continuously compliant with evolving standards.

API Governance setup

## What’s Ahead on the Roadmap:

**Git integration and CI/CD hooks**: Enable branching, and governance enforcement through Git workflows. Automate checks at every stage of the build and deployment lifecycle to ensure early issue detection and consistent quality.

**Import from Gateways**: Automatically generate specs and collections from deployed API infrastructure for faster onboarding and governance alignment.

**Postman API for Governance**: Access governance results programmatically to support integration with compliance workflows and approval systems.

**Support for OpenAPI 3.1 and 2.0**: Broaden compatibility across Postman’s tooling, including Spec Designer, Governance Engine, and Collection Sync.
