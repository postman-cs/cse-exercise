# How to use Postman for Public API Collaboration

Public API collaboration on Postman is for companies seeking to distribute reusable APIs to new and existing customers. For the company, the API drives revenue or contributes to business growth. For the consumer, the API enables innovation in building other products, and when successful, results in the creation of a community around the API that the publisher continues to serve.

## **Pattern: Public API Collaboration**

Collaboration around public APIs in Postman occurs in three distinct areas, illustrated below using a fictional shipping company called AcmeShipping. Note that collaboration within these areas can occur simultaneously. Instead of viewing this as a flow diagram, view it as different teams working on and using the public API in different ways.

AcmeShipping teams design and build APIs internally, following a consistent style guide designed to make it easy for end-customers to use the API. 

AcmeShipping publishes and maintains its APIs on the network, publishing new content as their API product evolves.

Developers evaluate, experiment with, and integrate the AcmeShipping API in private spaces to see if it does the job for them.

Three distinct areas of collaboration: AcmeShipping designs and builds its APIs internally, AcmeShipping distributes APIs publicly, and customers privately test AcmeShipping API products.

The rest of this document is organized around these three areas, including examples and best practices we’ve learned from real customers. 

## Collaboration Area: Internal API design and build

AcmeShipping is building its reusable APIs internally with the intention of distributing them publicly.

A basic shipping product requires the ability to validate addresses, ship packages, and track their delivery, all of which are reflected here as individual teams. Distributing a reusable API to the public is a high-intent action. So teams adhere to style guides that cover aspects such as parameter naming, casing, security concerns, HTTP status code usage, and the structure of error responses. Like any product, the details and polish determine the end-customer experience, and that starts with intentional internal API design.

Typically, this looks like the platform-wide collaboration pattern found in . For example, Moneris adheres to this pattern, resulting in a simple API for e-commerce. For more details, read: .

To be successful, AcmeShipping defines a consistent API style guide for all teams contributing to the public API. Developers should iterate on APIs in developer or project spaces, using fork-and-merge workflows to push updates to team spaces. Once APIs are known to adhere to AcmeShipping’s public API standards, AcmeShipping promotes the APIs to a public space, ensuring all APIs adhere to company standards before being made public.

## Collaboration Area: Publishing to the API network

The API network provides a channel for publishers to reach new and existing customers. The only requirement to be included on the network is to have a public workspace, but to be successful in reaching customers, companies like AcmeShipping should also do the following:

## 1. Let customers know who they are, and that their API is on Postman

The first step AcmeShipping should take is to get verified on the network. Verification establishes credibility and improves discoverability. When developers see AcmeShipping on Postman, the verification badge signals trust and authenticity. Because of those signals, verified companies appear more prominently in search results and autocomplete.

AcmeShipping should also let customers know they’re on Postman by deploying a Run in Postman button to their developer portal. As a tool commonly used by developers to design and test APIs, seeing a Run in Postman button makes it simple for developers to try the API. 

## 2. Make it easy to onboard to their API

Most APIs have primary use cases that drive the majority of their value. AcmeShipping should recognize these and make it easy for customers to get started with these use cases by organizing requests into Collections. For them, it’s likely tracking or address validation. Remaining use cases can be covered by one or more collections that cover the entire AcmeShipping API surface. For example, Zoom has dedicated Getting Started collections for meetings and webinars.

AcmeShipping API’s require authorization, which is often the first barrier to onboarding. Too many issues, and the developer will abandon the API and find another way. To simplify this, AcmeShipping should configure Guided Authorization, allowing them to define authorization steps for their API, including single-click options such as OAuth.

To share narratives for use cases that developers can run interactively, AcmeShipping should write notebooks. For example, Moneris published a notebook showing developers how to use their APIs with an AI Agent.

To share complete applications using the API, such as an AI Agent, AcmeShipping should create a Flow. For example, HubSpot published a Flow showing their customers how to create a call analysis task creation agent.

## 3. Keep customers updated

Once a customer watches AcmeShipping on Postman, AcmeShipping can reach the customer in-app and via email using Workspace Updates. AcmeShipping should notify customers about new features, changes to the API, new content, or any other relevant announcements.

As AcmeShipping publishes updates about its API, the updates will appear in our global news feed. Customers can react and comment, letting AcmeShipping know how they feel about the update, providing a valuable opportunity to get feedback from the community.

## 4. Improve their API

Within Postman, AcmeShipping can see the number of developers who have viewed their API, called their API, the response codes they’re receiving, and the number of developers experiencing authorization issues. Using this information can provide a valuable signal to improve the developer experience. For example, if AcmeShipping notices a high rate of 401s from developers, they can set up Guided Authorization and inform customers about it through a workspace update.

## Collaboration Area: Consumer usage

Collaboration continues for the consumer after the publisher has put their API on the network. There are three common patterns.

The most common pattern is for a developer to fork the AcmeShipping Collection to evaluate whether the API solves the problem they have. If it does, the developer can become a customer, watch the API on Postman, and become part of the community.

Developers will also commonly bring the collection into a team space. If a developer determines they need AcmeShipping for the product they’re building, then they’ll want to configure AcmeShipping so their entire team can test the API, explore other use cases, and stay connected to the community.

Finally, developers will fork collections with the intent to improve them, and give those improvements back to the AcmeShipping’s community. This can range from correcting a typo in a collection to demonstrating how AcmeShipping can be integrated with another API (e.g., an e-commerce platform). Developers can also contribute to the community by authoring notebooks that utilize the API, which other developers can use to learn how to leverage the API.
