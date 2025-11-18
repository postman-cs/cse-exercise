# How to use Postman with your toolchain

## **Pattern: How to setup git with Postman to…**

*Scope: App-specific APIs, internal reusable APIs*

**Set up a Workspace or Collection with git**

Start by importing the latest specs and APIs from git

If developers want to work in a separate Workspace, simply fork the Collection

**When iterating on an Collection, develop Collections alongside code using git-based workflows (Currently only GitHub)**

Connect a git repository and branch to the Collection

Start collaborating by forking the Collection which also creates and is tied to a new branch. Then make changes in Postman (i.e., feature branch development) while syncing back to that branch in git.

Run tests / CI for a Collection for the branch while developing features to catch issues before changes rollout (both locally and via pipeline)

When ready for review, create a pull request and merge it in git (i.e., pull request review, view diffs, etc)

A two-way sync is now established to keep Collections and code in synch

## **Pattern: How to setup Slack / Teams with Postman to…**

*Scope: App-specific APIs, internal reusable APIs*

**Stay on top of changes**

Publishers can keep their teams up to date by connecting their Workspace to a Slack / Teams channel

Once connected, notifications and updates (select activity) will be sent to that channel for activity for that Workspace

When posting a Workspace Update, Publishers can also send the update to a channel directly

On the flip side, consumers can stay on top of changes in their relevant Slack / Teams channels

When consumers interact with any of the messages and come back to Postman to engage, team members can then respond and collaborate as needed

**Stay on top of activity**

After configuring your monitor, you can select a Slack / Teams channel to send notifications when monitors are triggered, fail, etc

Enable personal notifications from settings to take actions via Slack (i.e., request. grant access)

**Collaborate, test, and troubleshoot APIs**

Developers can copy + share links for Collections, requests / responses, Workspaces, comments, etc directly to individuals or channels to share context and get help or feedback from the broader team.

When developers receive messages, they can interact with the message and / or come back to Postman to collaborate and engage the team.  Team members can then respond and collaborate as needed.

*Scope: Public reusable APIs*

**Stay on top of changes in a Public Workspace**

Any developer can subscribe to notifications and updates by connecting a Slack / Team channel to Public Workspaces of interest

 

## **Pattern: How to setup Jira Cloud with Postman to…**

*Scope: App-specific APIs, internal and Partner reusable APIs*

**Collaborate, test, and troubleshoot APIs**

If an error or unexpected result occurs for an API, connect and create a Jira issue from the request / response panel to share context (description, response) with relevant teams (custom fields and multiple Jira Cloud sites are supported)

See issue details in Postman and Jira Cloud to streamline collaboration with relevant teams to resolve the issue
