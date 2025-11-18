# How to use Postman [Internal Preview]

As I have spoken to teams internally at Postman as well as looking at our go-to-market guidance for customers, it has been very clear to me that we don’t have a common definition of how best to use Postman. Postman is designed as a flexible product and it can be used by many different personas, many API technologies, and many different types of companies. That breadth of adoption and flexibility, also means that it can cause confusion about providing authoritative guidance. 

Lack of authoritative guidance has meant that we can only talk about the product only in terms of the lowest common denominator which is a feature. In the “feature-only” world, there are either good features, bad features, or non-existent features. The only path to progress is creating more features, improving existing features, or removing features.

At this point we have a ton of features, and a ton of customers. What customers are asking for is not just new capabilities but *how to best use these capabilities *and *how to prove value for these capabilities.*

To determine that, we need to understand what exactly APIs are and how their design affects collaboration, automation, and governance. Product, Engineering, Marketing, Sales, and Field Engineering teams need to be able to speak about APIs authoritatively and be able to guide customers from start to finish.

The API vocabulary is quite rich and there are many different types of APIs. At their core, they boil down to two broad types in terms of what these APIs enable.

These API types are independent of technology choices i.e. they can be implemented through any programming language (Java/Python etc) or any protocol (HTTP/Websockets). 

**App-specific APIs** - These are single user APIs or bespoke APIs that are built for a specific consumer functionality. The consumers can be an app, an integration, a business requirement etc. They are usually built within a team, for project, or a monolithic codebase. Also called services, micro-services, macro-services, RPC services etc. This (unfortunately) is a **common way **of building APIs. We have often called this the **code-first** model. App-specific API users have access to the code base and understanding of the codebase.

App-Specifc API: built for a specific consumer (eg. frontend team)

**Reusable APIs** - This API can be used independently by another team. These are self-service APIs which means that another developer, team, a partner, or a company can use this API on their own without synchronous collaboration with another team. Also known as APIs as products, external facing APIs, platform APIs, or partner APIs or public APIs. We have called this the **API-first model. **These APIs can be used to create apps, integrations, or any other capability. Reusable APIs in many cases are also built on top of app-specific APIs through patterns like BFFs, and GraphQL. Requirements for reusable APIs can have an impact on downstream services that are powering those APIs too. Reusable API users don’t have access to the code base.

Reusable API: built with scalability, security and architectural integrity

## **Pros and Cons of App-Specific APIs**

**Pros**

Easy to get started with if the UI is ready as developers are used to them in terms of code or library functions.

Requirements come quickly from projects as developers can break down UI requirements into API functions.

Only one consumer at the time of development.

**Cons**

Frontend can’t start if the backend is not ready. Backend can’t start if there is no clarity on UI. This can lead to lack of progress in the project.

API implementation is tightly coupled with the consumer. If an additional consumer uses the same API, it either doesn’t work or a new API has to be created by tweaking the existing API

APIs are hard to use as a consumer has to clearly understand the entire surface area of the API. For example, an API endpoint might do a very specific task that may or may not accomplish the user’s goal. Hence the user will continue hunting for the right API. 

Multiple APIs might exist with similar purposes. Sometimes developers duplicate entire app codebases which each have the same API

Tight coupling hurts consumers as they changes to the UI also mean changes to the backend through the API. Adding a new API becomes hard.

As these APIs proliferate, they are harder to audit for compliance or regulatory purposes especially if they are exposed to the outside world.

Impossible to integrate with external systems or partners or to the public.

APIs are tested indirectly through UI testing. This can lead to issues especially around security where alternative or malicious uses of the API might not have been thought of. 

## **Pros and Cons of Reusable APIs**

**Pros**

App consumers can get started easily and often self-serve themselves right away.

Scales almost infinitely provided change management is accounted for i.e. one API can support 100s or 1000s of teams internally and millions of developers externally

API boundary helps maintain architectural integrity. Duplicate APIs don’t exist.

Help integrate with external systems/partners/or 3rd-party developers

Loosely coupled meaning it is easier to do tech migrations as long as the API boundary is maintained

Easy to secure and audit as they are built with external consumers in mind - one of them being IT/Security.

**Cons**

Harder to create. Skill set for creating reusable APIs is limited and only experienced engineers can create them well.

Requires understanding the set of available consumers which delays projects. Building a reusable API is a deliberate choice - they don’t get built accidentally.

Requires change management among a large number of consumers when API versions evolve.

Supporting multiple versions of an API is a challenge as consumers might not want to move out of the existing API.

## **Which API type to use when**

Most APIs in the world start off being app-specific APIs. As building reusable APIs is a deliberate choice, they appear at a lower density especially internally. Engineering teams often continue in the app-specific API mode until tech debt reaches a threshold or a business priority forces them to externalize the API to other teams, or to partners, or to the public.

At a technical level, most organizations still use HTTP for APIs as it is the most versatile technology. Some might use GraphQL or gRPC but HTTP is the dominant form. RPC over HTTP is what the eventual implementation starts looking like for most APIs.

REST is the standard way to define reusable APIs and that is what you see in almost all well-adopted public APIs. REST also uses HTTP predominantly and hence it can be confusing to know what is REST and what is not. There are entire books written on this topic and there is no need to debate that.

So, the question becomes - When do companies build a reusable API? This is when they typically do it:

**When they have multiple consumers** of the API for their applications like a web, mobile, SaaS-platform app - at the same time or multiple products being built in the same company.

**When they have data model sprawl** - app-specific APIs often result in a data model spread across multiple services. If the business can’t get a sense of data and use it well, a reusable API needs to be created to unify the data model and give access to consumers in a proper way.

**When they start seeing functionality needed by multiple products or business units** - who all need the same thing - like identity, payment, storage, networking APIs etc - this typically results in building a platform

**When they have to adopt new technology** - a bank might still be running mainframes, but they need to adopt the cloud and now AI. They might build a new API on top of the existing app-specific APIs to serve new use cases while keeping the existing services intact.

**When they can’t ship new software** - sometimes app-specific APIs result in spaghetti architectures, after which no progress can be made. Architectural refactoring results in them wanting to build new APIs

**When software starts breaking in weird ways** - As app-specific APIs are tested primarily through the UI, if UI and backends change, over time, the tight coupling takes a toll and quality issues surface up.

**When they have to serve functional business needs** - they often come from finance, marketing, sales, or other functions where their software needs to send data outside, or needs to be integrated in GTM/Finance software.

**When they have to integrate their software with other vendors** (when they have to build a public API or a partner API ecosystem)

A company that has more than 10 engineers will typically starts to move towards reusable APIs in some shape or form. While their technical architecture might not be perfect from day 1 - all the needs mentioned above force them to have some form of a reusable API.

## Maturity Levels

Postman’s platform is designed for all types of APIs but different customers are at different stages in their API Maturity. There are 3 levels of maturity that we have seen among customers:

**Level 1: Primarily App-Specific APIs: **API development is tied to application development.

**Level 2: First Few Reusable APIs: **Teams have started building a few reusable APIs - sometimes internally or externally.

**Level 3: Reusable APIs as a common platform: **All teams are mandated to use specific APIs to build new products. This is where the company has a platform that others can build upon. (AWS level platform APIs)

## **How-to Guides**

 

 

 

API Workflow Documentation
