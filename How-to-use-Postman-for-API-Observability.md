# How to use Postman for API Observability

## Deployment Guide for Insights

## Who is Insights for and what problem does it solve

Insights helps developer productivity by reducing mean time to resolution for issues caused by API errors (4xx/5xx errors and high latency):

**Insights helps teams catch user-impacting issues faster,** by making it super easy to set up error and latency alerts across every single API endpoint.

**Insights helps developers root cause issues faster** by providing an automatic, comprehensive view of errors and high latency across all API endpoints.

**Insights help developers resolve issues faster** by making it seamless to replay failing API calls on real user data, using the Repro Mode feature.

Additionally, Insights gives technical leaders visibility into errors and latency on APIs across the services they overview.

## How to set up Insights

Insights projects live in your Postman workspace. We recommend each time set up Insights projects within a single workspace, creating one Insights project per service.

**[Workspace admin role required] **Enable Insights in your team-specific workspace.

**[Infra permissions required] **Set up the Insights Agent to run alongside your container environment, generally as a sidecar.

https://learning.postman.com/docs/insights/get-started/kubernetes/overview/ 

https://learning.postman.com/docs/insights/get-started/ecs/ 

https://learning.postman.com/docs/insights/get-started/ec2/ 

https://learning.postman.com/docs/insights/get-started/beanstalk/ 

**[Workspace admin role required]** Enable Repro Mode from the Insights project settings.

**[Slack permissions required]** Enable alerts and configure it to send to a Slack channel monitored by your squad. Docs: https://learning.postman.com/docs/insights/reference/app/alerts-tab/ 

More information here: https://learning.postman.com/docs/insights/get-started/overview/ 

## How to use Insights to be more productive

## Set up

Set up Insights across all services

Set up available alerts (currently 5xx)

## Day-to-day

Check your Slack channel for Insights alerts and investigate alerts that may be problematic, using Repro Mode to help root cause and test resolutions

Mute alerts that are not useful, so you are only getting useful alerts

## Weekly

Check your Insights Overview and Errors Overview pages during ops review to see if there are endpoints your team needs to be paying attention to, before they become incidents

Check your weekly email digests for the same

## Connecting Insights to Collaboration, Test Automation, and Governance

## Insights for Collaboration

Insights currently supports sharing links to Error details pages for any given endpoint. In the future, Insights will support commenting, assigning owners to issues, and more. Insights will leverage the existing Postman collaboration actions, as well as integrate with other tool for collaboration like PagerDuty and Jira.

Today, Insights also plugs into existing collaboration workflows as follows:

Insights' Repro Mode feature integrates with Request Builder, automatically populating Request Builder with real user requests. From Request Builder, users may save requests and use them in any collaboration workflows.

Insights' “Save to Collections” feature, accessible via the “Endpoints” tab, make it possible to take any subset of API calls that Insights has automatically discovered and export to either an existing Collection, or a new Collection.

## Insights for Test Automation

Insights' integrations with Request Builder and Collections make it possible to use Insights endpoints with Postman’s test automation capability:

Insights' Repro Mode feature integrates with Request Builder, automatically populating Request Builder with real user requests. From Request Builder, users may save requests to collections in order to use with Postman Monitors. Insights records a separate request for different API calls, making it easy to explore variants of the same API call for API testing.

Insights' “Save to Collections” feature, accessible via the “Endpoints” tab, make it possible to take any subset of API calls that Insights has automatically discovered and export them to collections to use with Postman Monitors.

**Coming up: **Insights will integrate with CI/CD pipelines to correlate stage/production errors to deployments, to help teams have more confidence in what they ship.

## Insights for Governance

Insights uses AI to automatically discover API endpoints, meaning Insights has the ability to detect API endpoints that otherwise go undocumented in an organization. How to use this feature:

Deploy Insights across services, as described above. Insights will watch passively watch all API traffic and use AI to automatically infer API endpoints, for instance rolling up calls to /users/user0 and /users/user1 into a /users/{user} endpoint.

Go to the “Endpoints” tab to explore the discovered endpoints. Since Insights discovers *endpoints* rather than logging and displaying raw API calls, the discovery is more powerful than simple request logging. On the “Endpoints” tab, users may explore endpoints via search and filtering by properties such as status code, host, and method.

Use the “Save to Collection” feature to create a Collection from the discovered endpoints.
