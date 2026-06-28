# Notes on Claude Connectors, Enterprise Search, and Research

## Claude Connectors

Connectors allow Claude to work with information from the apps and services you already use. Instead of manually copying information into the chat, you can connect Claude to tools like Google Drive, Gmail, Slack, Notion, Asana, Linear, and other services.

The main purpose of connectors is to give Claude useful context from your real work environment. This helps Claude answer questions, find documents, summarize information, and sometimes complete actions inside connected tools depending on the permissions you allow.

## Why Connectors Are Useful

Without connectors, Claude only knows what you type or upload into the chat.

With connectors, Claude can access approved tools and use that information during a conversation.

Connectors can help Claude:

* Search connected files
* Find specific documents
* Read relevant information
* Summarize messages or records
* Analyze data from connected services
* Create or update content when permissions allow
* Help complete tasks across work tools

This makes Claude more useful because it can work from your actual context instead of requiring you to provide everything manually.

## MCP and Connectors

Connectors are powered by MCP, which stands for Model Context Protocol.

MCP is a standard way for AI systems to connect with external tools and data sources. A simple way to understand MCP is that it acts like a shared connection system between Claude and other applications.

Instead of every app needing a completely different integration style, MCP creates a common method for connecting tools to Claude.

This means developers can build connectors for many different services, and Claude can interact with them in a consistent way.

## Types of Connectors

There are two major types of connectors:

```text
Web connectors
Desktop extensions
```

## Web Connectors

Web connectors connect Claude to cloud-based services.

Examples include:

* Gmail
* Google Drive
* Slack
* Notion
* Asana
* Linear
* Jira
* Stripe
* Salesforce
* Confluence

These connectors are useful when your information is stored online.

For example, Claude could help find a Google Doc, summarize a Slack discussion, or check the status of a task in a project management tool.

## Desktop Extensions

Desktop extensions work through the Claude Desktop app. These are used for tools and files on your local computer.

Desktop extensions can help Claude interact with:

* Local files
* Native desktop apps
* Browser tasks
* Design tools
* Local workflows

These require the Claude Desktop app because they run on your machine instead of only through the web version.

## Finding Connectors

Connectors can be found through Claude’s connector directory.

You can browse available connectors by opening the connector menu from Claude or by going to the connector directory.

The directory is usually organized into categories such as:

* Web tools
* Desktop extensions

This makes it easier to find the connector that matches the service you want to use.

## Setting Up a Web Connector

To connect a web-based service, the general process is:

1. Open the connector directory.
2. Choose the tool you want to connect.
3. Select the connect option.
4. Sign in to the external service.
5. Review the permissions being requested.
6. Approve access if you are comfortable with it.
7. Return to Claude and test the connection.

A simple test prompt could be:

```text
Can you access my Google Drive?
```

Or:

```text
Can you find my latest document in Notion?
```

The exact actions Claude can take depend on the connector and the permissions you approved.

## Setting Up a Desktop Extension

Desktop extensions require Claude Desktop.

A general setup process is:

1. Install Claude Desktop.
2. Open the app.
3. Go to settings.
4. Open the extensions area.
5. Browse available extensions.
6. Install the extension you want.
7. Follow any setup steps for that specific extension.

Desktop extensions are useful when Claude needs access to something local on your computer rather than a cloud service.

## Example Uses for Connectors

Connectors can be used across many types of work.

## Project Management

With tools like Asana, Linear, or Jira, Claude can help with questions such as:

```text
What tasks are due this week?
```

```text
Create a task for reviewing the budget proposal.
```

```text
Summarize the current status of the product launch project.
```

## Communication

With tools like Gmail or Slack, Claude can help with questions such as:

```text
Find the email thread about the vendor agreement.
```

```text
Draft a reply to the latest message from the marketing team.
```

```text
Summarize what the team decided about the launch timeline.
```

## Documentation

With tools like Google Drive, Notion, or Confluence, Claude can help with questions such as:

```text
Find the brand voice guidelines.
```

```text
Summarize last week’s product review notes.
```

```text
What does the style guide say about contractions?
```

## Business Tools

With tools like Stripe, PayPal, or Salesforce, Claude can help with questions such as:

```text
Show revenue trends from the last quarter.
```

```text
What is the status of this sales opportunity?
```

```text
List recent high-value transactions.
```

## Connector Security

Connectors require permissions, so they should be used carefully.

When you connect a tool, you are allowing Claude to access information from that service. Some connectors may only allow Claude to read information. Others may allow Claude to create, update, or modify data.

Important security points:

```text
Claude can only access what your account can access.
You can remove connector access later.
You should review permissions before approving a connector.
You should only install connectors from sources you trust.
```

For example, connecting your work email does not mean Claude can access every employee’s inbox. It should only access the data your own account is allowed to access.

## Questions to Ask Before Using Connectors

Before connecting a tool, ask:

```text
Do I trust this connector?
What permissions is it requesting?
Does Claude need read-only access or action permissions?
Could this connector expose private or sensitive data?
Will this save me time compared to copying information manually?
```

Connectors are most useful when you repeatedly need Claude to work with information from the same tools.

---

# Enterprise Search

Enterprise Search is designed for organizations that want Claude to search across company knowledge sources.

It gives users a dedicated place to ask questions about internal company information. Instead of searching through multiple tools manually, users can ask Claude to find and summarize relevant information from connected company systems.

Enterprise Search is mainly for Team and Enterprise plans and usually must be enabled by a workspace administrator.

## What Enterprise Search Does

Enterprise Search helps answer questions using internal company data.

It can search across connected workplace tools such as:

* Shared documents
* Chat messages
* Email threads
* Company files
* Internal documentation
* Meeting notes
* Knowledge bases

Claude then combines the relevant information into one response and provides citations so users can check the original sources.

## How Enterprise Search Is Different From Regular Connectors

Regular chats with connectors can access connected tools when needed.

Enterprise Search is more focused. It is designed specifically for searching and synthesizing internal organizational knowledge.

A simple way to understand it is:

```text
Connectors help Claude use your connected tools in normal chats.
Enterprise Search creates a dedicated search experience for company knowledge.
```

Enterprise Search is useful when the answer may be spread across many internal sources.

## What You Can Ask Enterprise Search

Enterprise Search is useful for questions that require internal context.

Examples include:

```text
What happened while I was out yesterday?
```

```text
What are the main blockers on the platform project?
```

```text
What is the company policy for remote work?
```

```text
How do I submit an expense report?
```

```text
What were the key decisions from last week’s leadership meetings?
```

```text
How does our authentication system work?
```

```text
Who should I contact about the billing system?
```

## Common Use Cases

Enterprise Search can help with:

* Getting caught up after time away
* Finding company policies
* Understanding internal processes
* Researching customer feedback
* Reviewing project decisions
* Helping new employees onboard
* Summarizing team discussions
* Tracking project updates
* Finding information across documents and messages

This is useful because employees often spend time asking coworkers questions that may already be answered somewhere in company tools.

## Enterprise Search Setup for Admins

For an organization to use Enterprise Search, an admin or owner usually needs to complete the first setup.

The general admin process is:

1. Open the organization search option.
2. Start the setup process.
3. Connect required company tools.
4. Choose document sources, such as Google Drive or SharePoint.
5. Choose chat sources, such as Slack or Microsoft Teams.
6. Optionally connect email sources.
7. Add any additional tools the organization needs.
8. Customize the name users will see.
9. Add a description.
10. Finish setup.

After setup is complete, users in the organization can begin connecting their own accounts.

## Enterprise Search Setup for Users

After an admin enables Enterprise Search, users can open the shared organization search area.

The general user process is:

1. Open the organization search project.
2. Follow the setup prompts.
3. Connect the recommended tools.
4. Sign in to each service.
5. Start asking questions about company knowledge.

The more relevant services a user connects, the more complete the search results can be.

## Enterprise Search Safety

Enterprise Search is designed to respect existing permissions.

That means Claude should only show information that the user already has permission to access in the original tool.

For example, if a user does not have access to a private folder in Google Drive, Enterprise Search should not reveal information from that folder.

Important safety points:

```text
Enterprise Search follows existing access permissions.
Connected data is not available to everyone automatically.
Users only see information they are already allowed to see.
Conversations remain private.
Connected data is not separately indexed as a new public database.
```

## When Enterprise Search Is Most Useful

Enterprise Search is best when the question is about internal company knowledge.

Use Enterprise Search when:

* The answer is inside company documents or messages
* The question depends on internal context
* You need information from multiple workplace tools
* You are looking for policies, decisions, updates, or processes
* You want citations back to the original company sources

## Questions to Ask Before Using Enterprise Search

Ask yourself:

```text
Is this question about my organization?
Could the answer be in internal documents, Slack, email, or shared files?
Would this usually require asking a coworker?
Would it save time to search across multiple company tools at once?
```

If yes, Enterprise Search is probably the right tool.

---

# Claude Research

Research is a feature that allows Claude to investigate a topic in a more thorough and structured way.

Instead of doing one quick search, Claude can run multiple searches, compare information, follow leads, and build a more complete answer.

Research is useful when you need a deeper report rather than a short fact.

## What Research Does

Research helps Claude gather and analyze information from several sources.

It can explore different parts of a question, identify missing information, and combine findings into a structured response.

Research is useful for questions that require:

* Multiple sources
* Comparison
* Current information
* Detailed analysis
* Citations
* A complete report
* Synthesis across different viewpoints

## How Research Is Different From Web Search

Web search is better for quick answers.

Research is better for deeper investigations.

A simple difference:

```text
Use web search when you need a fast fact.
Use Research when you need a full investigation.
```

For example, web search is better for:

```text
What is Apple’s current stock price?
```

Research is better for:

```text
Analyze the electric vehicle battery market, including major companies, technology trends, supply chain issues, and investment risks.
```

## How Research Works

Research uses a multi-step process.

Claude first thinks through the question and decides what information is needed. Then it searches for relevant sources. As it finds information, it decides what to investigate next. After gathering enough information, it organizes the findings into a report.

A simple version of the process is:

```text
Plan the investigation
Search multiple sources
Follow useful leads
Fill in missing details
Compare findings
Summarize the results
Provide citations
```

This makes Research more thorough than a single search.

## When to Use Research

Use Research when you need:

* Market research
* Competitive analysis
* Vendor comparisons
* Product launch planning
* Complex project planning
* Technical documentation from several sources
* Briefings based on current information
* Reports with citations
* Analysis across web and connected tools

Research is especially useful when the task would normally take a lot of manual searching.

## When Not to Use Research

Research is not always necessary.

Use normal web search when:

* You only need one quick fact
* The answer is simple
* One or two sources are enough
* Speed matters more than depth

Use extended thinking when:

* The problem mainly requires reasoning
* No outside information is needed
* You are solving math, logic, or code issues
* The answer comes from analysis rather than research

Use Enterprise Search when:

* The question is about your company
* The answer is inside internal documents or messages
* You need organizational policies, decisions, or updates

## Examples of Good Research Tasks

Research is useful for prompts like:

```text
Compare the top project management tools for a small software team. Include pricing, major features, integrations, limitations, and best use cases.
```

```text
Research the current market for AI-powered note-taking tools. Identify competitors, pricing models, features, and gaps in the market.
```

```text
Create a briefing on cybersecurity risks for small businesses, including common threats, recommended protections, and recent trends.
```

```text
Analyze possible vendors for cloud storage and compare cost, security, scalability, and ease of use.
```

## Using Research With Connected Tools

Research can become more useful when connected tools are enabled.

For example, Claude may be able to combine public research with information from:

* Google Drive
* Gmail
* Google Calendar
* Slack
* Company documents
* Internal notes

This allows Claude to answer questions using both outside information and your own work context.

Example prompts:

```text
Summarize what has been discussed about Project X in my emails and Slack, then compare our approach to industry best practices.
```

```text
Look at my meetings next week and research each company I am meeting with.
```

```text
Find internal documents about pricing strategy and compare them with competitor positioning.
```

## Internal-Only Research

Research can also be used with web search turned off if you only want Claude to search connected internal tools.

This is useful when the answer should come only from private or company sources.

Example:

```text
Search my connected documents and Slack messages for everything related to the Q3 launch plan. Do not use the public web.
```

## Tips for Better Research Prompts

Good Research prompts should be clear and specific.

Instead of asking:

```text
Tell me about the EV market.
```

Ask:

```text
Analyze the electric vehicle battery market. Include major companies, technology trends, supply chain risks, pricing pressure, and factors that could affect investment decisions.
```

A strong Research prompt should include:

* The goal
* The topic
* The type of output you want
* Any sections you want included
* Constraints like budget, location, timeline, or audience
* Whether to use web sources, connected tools, or both

## Prompt Structure for Research

A useful Research prompt can follow this format:

```text
Research [topic].

Focus on:
1. [Area 1]
2. [Area 2]
3. [Area 3]

Include:
- Key findings
- Comparison of options
- Risks or limitations
- Recommendations
- Citations

Audience: [who will read it]
Constraints: [budget, timeline, location, tools, or other limits]
```

## Example Research Prompt

```text
Research collaborative note-taking tools for a university capstone course.

Focus on:
1. Real-time collaboration features
2. GitHub integration options
3. Pricing for about 200 students
4. Data privacy and admin controls
5. Ease of integration with an Angular and FastAPI app

Include a comparison table, pros and cons, and a final recommendation.

Audience: computer science students and faculty.
```

## Questions to Ask Before Using Research

Before using Research, ask:

```text
Do I need information from several sources?
Would this normally take a long time to research manually?
Do I need citations?
Do I need a comparison or recommendation?
Does the answer require current information?
Would a structured report be better than a quick answer?
```

If yes, Research is a good choice.

---

# Connectors vs. Enterprise Search vs. Research

These three features are related, but they are not the same.

## Connectors

Connectors let Claude access specific external tools.

Use connectors when you want Claude to work with your apps and data.

Example:

```text
Find the Google Doc about our brand guidelines.
```

## Enterprise Search

Enterprise Search is for searching across company knowledge.

Use Enterprise Search when the question depends on internal organizational information.

Example:

```text
What did our team decide about the product launch timeline?
```

## Research

Research is for deeper investigation across multiple sources.

Use Research when you need a full report, comparison, or analysis.

Example:

```text
Compare the top competitors in the AI note-taking market and summarize their pricing, strengths, and weaknesses.
```

## Quick Comparison

| Feature           | Best For                              | Example                                               |
| ----------------- | ------------------------------------- | ----------------------------------------------------- |
| Connectors        | Accessing specific tools and services | Searching Gmail, Drive, Slack, Notion, Asana          |
| Enterprise Search | Finding internal company knowledge    | Policies, project updates, decisions, onboarding info |
| Research          | Deep multi-source investigation       | Market reports, vendor comparisons, briefings         |

## Final Summary

Connectors let Claude use the tools and services you connect.

Enterprise Search helps organizations search across internal knowledge sources.

Research helps Claude investigate complex questions by gathering and synthesizing information from multiple sources.

Use connectors when Claude needs access to your tools.

Use Enterprise Search when the answer is inside company knowledge.

Use Research when you need a detailed, cited report.


---
These are my personal study notes based on Anthropic materials. The notes are written in my own words and are not an official Anthropic resource. Original material copyright 2025 Anthropic. All rights reserved.