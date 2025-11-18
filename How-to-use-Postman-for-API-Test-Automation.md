# How to use Postman for API Test Automation

Testing is a vast area and is deemed to become more critical as the job for developers shifts from writing code to doing higher level tasks of system design, building bigger systems, and eventually testing them. Testing an API is a continuous activity and it happens next to *any change to the behavior of the API*. This means, that testing needs to happen when the codebase changes, components change, infrastructure changes, dependencies change etc.

Postman has a robust set of tools for testing:

An API client to construct requests and observe responses

An extensible Javascript based testing environment to write validations and test scripts

An automation environment accessible through the UI in the app and CLI - the Collection Runner

A performance testing tool to simulate the API under bigger loads and real-world usage patterns than just sending an API endpoint

Mock servers for helping isolate dependencies

Interceptor or Proxy tools to capture APIs from end-user applications

Synthetic monitoring tool to help run tests post-deployed on automated alerts

Tools for testing in Postman

## **How does API Test Automation connect with Collaboration**

Testing is done by many people who are involved in shipping software - developers, quality engineering, security engineering, SRE/DevOps. API testing is also needed by consumers of APIs who might be front-end developers or by external consumers of the API. For the purpose of this document, we’ll refer all of them as “developers”.

People involved in testing APIs need to know what the API is, what it’s intended/unintended use cases are, and they need to tie this info to the end goal. Postman Collections provide the core language for developers to communicate this. Postman’s Test Automation tools extend the ability of Collections to testing and when these are made available in Workspaces, developers know exactly what to do.

If teams are adopting Postman for test automation, these tests can live inside their team-specific spaces as described in  

Testing patterns are mostly similar for App-Specific APIs as well as reusable APIs. Contract testing is the most recent development that helps producers/consumers align and enforce tests that catch breaking changes. 

Let’s look at the types of APIs and what types of testing is typically done with them:

Types of testing across spaces

## **For App-Specific APIs**

**Exploratory Tests** - These are informal tests conducted to explore the functionalities of an application without predefined test cases. The goal is to identify defects and gain a better understanding of the application through hands-on experience. Exploratory testing encourages testers to use their creativity and intuition to discover issues that may not be covered by scripted tests.

*Guidance from product: *Set up Postman Collections with documentation to allow developers to have an easy jumping off point inside an internal workspace. Developers might fork collections into their own workspace for their own exploratory workflows. Setting up authentication is the most common blocker for getting started with new APIs. Hence, use the Authorization tools in Postman to guide users to set up auth properly or use pre-request scripts at the Collection level to help developers obtain access to the API (especially internal APIs). Use Mock Servers to help developers “get a feel” of the API without actually incurring infrastructure costs or destructive changes to the real APIs.

**Functional/Smoke Tests** - These tests are designed to verify that the basic functionalities of an application are working as intended. They check the critical paths of the application to ensure that the most important features are functioning correctly.

*Guidance from product: *Use Postman’s scripting environment to add basic tests like checking the request code or the response bodies. Most teams might be graduating out from UI tests to be using functional tests. API testing is faster, less brittle, and when it is independent of the UI, it is more cost effective. Postman has libraries built-in to help with creating security tests and can also be extended with external scripts to help create reusable test suites. Collections can be run using the Collection Runner or the Postman CLI.

**Integration Tests** - These tests focus on the interactions between different modules or services within an application. They ensure that the integrated components work together as expected and help identify issues that may arise when combining different parts of the system.

*Guidance from product: *Collections can contain requests from the same API/service or a collection of APIs depending on what the app that the API is serving actually does. Use features described in exploratory and functional testing paragraphs to add tests to requests. Use environment variables and the setNextRequest function to orchestrate workflows like passing data from one request to another or repeating requests. Postman also supports data files like CSVs to help developers run tests on a range of input scenarios.

**Security Tests** - These tests are aimed at identifying vulnerabilities and weaknesses in an application. They assess the security measures in place to protect data and ensure that the application is resistant to attacks and unauthorized access.

*Guidance from product: *Use Interceptor or Proxy to capture API requests and save them inside Collections to get a sense of which APIs are being called and which APIs could be exposing vulnerabilities.

**Performance Tests** - These tests evaluate the responsiveness, speed, scalability, and stability of an application under a particular workload. They help determine how the application behaves under stress and identify any performance bottlenecks.

*Guidance from product: *Use Postman’s performance testing tool to help simulate lightweight loads. Performance Testing in Postman is early right now in maturity so we recommend using it as an early signal versus a full production load. Postman Collections can be imported into tools like Gatling to run bigger/deeper tests.

**End-to-end workflow Tests** - These tests validate the complete flow of an application from start to finish. They simulate real user scenarios to ensure that all components of the application work together seamlessly and that the user experience is as expected.

*Guidance from product: *Record tests using the Interceptor or Proxy, or re-create test scenarios using Collections. Apply everything mentioned in building exploratory tests, functional tests, and integration tests sections.

**Synthetic Production Testing** - These are automated tests that simulate user interactions with an application in a production environment. They help monitor the application's performance and availability, providing insights into how the application behaves under real-world conditions.

*Guidance from product: *Build Collections that test for the behavior you expect when APIs are deployed to staging/production environments. Use Postman Monitors to run them on a schedule.

## **For Reusable APIs**

**All of the above *****plus***

**Consumer-Driven Contract Tests** - These tests are designed to ensure that the interactions between service consumers and providers meet the expectations set by the consumers. They focus on the contracts that define how services should behave, allowing for better collaboration between teams and ensuring that changes in one service do not break the functionality expected by another service.

## **General guidance for all types of testing App-Specific APIs and Reusable APIs**

Maintain tests in a shared internal workspace within a team

Use environments to parameterize tests so they can be run in different environments

Use the Postman CLI to run tests in CI/CD environments

Connect tests to your GitHub repo using the git integration

Connect Postman Monitors to existing engineering dashboard systems that you have

Automation Testing Setup

## Recommended workspace topology

Workspace

Who owns it

What lives there

Access model

Why it matters for CDC

**Consumer team workspace**

Mobile/Web/Backend consumer team

Contract collection(s) + example data

Internal team editors

Lets the consumer evolve the contract with their code base.

**Producer workspace**

API team

Implementation collections, environment configs, mock servers, docs

Internal editors; consumers usually *view-only*

Keeps implementation churn separate from contracts, but still visible.

**Shared *****Contract***** workspace** (Team or Partner)

Jointly owned, or by Platform team

“Source-of-truth” fork of every consumer contract + badges for last CI run

Consumer: view & pull requests.
Producer: edit & merge.

Central place where CI pulls contracts and where both sides inspect failures.

**Partner workspace** (if external consumers)

Platform team

Curated public-surface collections, auth instructions, monitors

External partners invited as guests

Postman Partner Workspaces give external companies secure, read-only or controlled-edit access without exposing internal assets. 

**Discovery / Private API Network**

Org-level enablement team

Index of all stable, reusable APIs, auto-published from producer workspaces

Everyone in the org

Makes it trivial for new consumers to *find* the contract collection before writing code.

Contract tests can be run in CI pipelines like other tests that the consumer is running as part of their codebase.
