# How to use Postman for API Workflow Documentation

Documentation about individual API calls rarely tells the whole story to your internal or external developers. To solve a real-world problem, developers often need to understand how a series of APIs work together in a sequence. This is the purpose of workflow documentation. In Postman, this workflow-centric understanding of an API is enabled by Flows. 

Building on the foundation of collections, Flows provides a visual canvas to chain API requests, handle data, and model complex workflow logic. It transforms documentation from a static page of text into a living, executable diagram that allows teams to quickly understand, share, and validate how their APIs work together to deliver value. Simply create a Flow and add requests from your existing collections to it and you’re ready to go.

**Run Logs** allow you to run and trace your** **visual workflows to understand what is happening at every step of the process.

**Scenarios in Flows** makes it possible to define and test a wide range of possible inputs to your API without maintaining separate workflows.

**Modules** make it easy to reuse the same workflow logic across multiple flows without having to duplicate efforts to reproduce or maintain logic.

**Live Embeds** makes it possible to share or embed a visual representation of the workflow logic into internal or external documentation.

**Slides** let you create a custom step-by-step walk through of the workflow directly within the Flow canvas.

Together, these features provide powerful capabilities for teams to define, run, and share complex API workflows visually without ever leaving Postman. By moving beyond static descriptions and creating executable, interactive, and easy-to-understand visual workflows, Flows helps you reduce ambiguity, accelerate onboarding, and empower every developer to see the full picture of how your APIs solves their problems.

## How to get started with Flows

Flows are designed to be intuitive, allowing you to visually construct API workflows in minutes. Because of this, you can build your first flow in minutes in Postman. Here are the basic steps to create your first Flow.

**Create a New Flow:** In your Postman workspace, select *Flows* from the sidebar. Click the + button or *Create Flow* to open a new, blank canvas with a *Start* block already in place.

**Add Your First Block:** The core of Flows is adding and connecting blocks. To add a block, you can right-click anywhere on the canvas. A common first step is to add a request from one of your collections.

**Connect the Blocks:** To create a sequence, connect the blocks. Hover over the output port on the right side of one block (like the *Start* block) and drag the connection line to an input port on the left side of another block.

**Run the Flow:** Click the *Run* button at the bottom of the canvas. The Flow will execute, and you will see the live data appear below each block as it runs.

For more detailed tutorials and advanced examples, you can explore the official Postman documentation on the Postman Learning Center.

## Flows for Collaboration

Traditional workflow collaboration relies on a handoff of disconnected artifacts. Producer teams share collections, API specifications, and links to a developer portal, leaving their users to piece together how a series of individual endpoints actually solve a business problem.

Flows transforms this handoff into a living, shared understanding. It replaces static text with a single, executable artifact that demonstrates a complete business process in conjunction with the collections already curated by the team.

Whether for internal collaboration within an internal workspace or external collaboration work via a public or partner workspace, creating and sharing Flow provides developers with a clear understanding of how APIs work together.

## Flows for API Testing

There are two ways to test APIs using Postman. Teams are able to use collection runner and collections to write and run tests. Alternatively, Flows can also be used to test API endpoints. While collection runner is a best in class tool for running linear test suites and validating individual endpoints with scripted assertions, ideal for regression and CI/CD testing, Flows is built for testing entire business processes. Use Flows when your testing requires conditional logic, branching, and a clear visualization of a multi-step transaction.

Flows empower you to visually map out and debug complex, end-to-end tests that mimic user journeys. Instead of scripting every possible path, you can use built-in blocks to make decisions based on API responses or test different inputs using Scenarios. This makes Flows the right choice for validating the logic of a complete workflow, especially when the sequence of calls can change based on the data. Additionally, you are able to easily integrate AI into your testing for situations for added flexibility.

## Flows for Developer Onboarding

Flows reduce the time it takes for developers to learn new systems by showing, not just telling, how APIs work together. This is a key factor in accelerating the onboarding of new team members. Instead of parsing dense documentation, a developer can open a Flow, execute it, and immediately see the sequence of calls and the data flowing between them.

This interactive approach encourages experimentation. Using features like scenarios, a developer can safely experiment with various edge cases or error conditions to build a deeper understanding of the APIs. This also allows teams to document their systems as they are built. Rather than waiting for a front-end or consumer application to be finished, teams can use Flows to demonstrate and validate how backend services interact, enabling parallel development and earlier integration.
