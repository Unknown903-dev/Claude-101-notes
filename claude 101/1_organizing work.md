# Notes on Claude Projects, Artifacts, and Skills

## Claude Projects

Claude Projects are separate workspaces that help organize related work. Each project can have its own chats, uploaded files, instructions, and saved context. Instead of starting over every time, a project lets Claude keep the same background information available across multiple conversations.

A project is useful when you are working on something ongoing. For example, if you are building a product, writing documentation, planning an event, doing research, or managing a client account, a project can keep all related materials in one place.

## Why Projects Are Useful

Projects help because they reduce repetition. Instead of uploading the same documents or explaining the same rules again and again, you can add that information once to the project.

Claude can then use that project knowledge whenever you start a new chat inside the project.

Projects are helpful for:

* Organizing related conversations
* Keeping reference documents in one place
* Reusing the same instructions across chats
* Giving Claude consistent background context
* Supporting team collaboration on shared work

## When to Use a Project

You should create a project when the work is more than a one-time question.

A project is useful when you have:

* Documents you will use repeatedly
* A specific topic or work area
* A consistent response style you want Claude to follow
* A workflow that needs the same format every time
* A team that needs access to the same shared information

Examples include:

* Product launch planning
* Research summaries
* Client account work
* Marketing campaigns
* Event planning
* Job description writing
* Technical documentation

## Creating a Project

To create a project, open the Projects section in Claude and select the option to create a new project.

A good project should have:

* A clear name
* A short description
* The right visibility setting
* Project instructions
* Uploaded reference materials

The project name should be specific enough that you and your team understand its purpose.

For example:

```text
Q3 Product Launch
Customer Research Notes
Capstone Project Documentation
Client Account Workspace
```

## Project Instructions

Project instructions tell Claude how it should behave inside that project.

These instructions apply across chats in the same project. They can control tone, format, level of detail, response style, and workflow.

Good project instructions can include:

* What the project is about
* Who the audience is
* What tone Claude should use
* What format responses should follow
* What steps Claude should take for common tasks
* Any rules or requirements Claude should always remember

Example project instructions:

```text
This project is for creating student-facing documentation for a software engineering capstone project.

Use clear and simple language. Avoid unnecessary jargon. When explaining technical ideas, include short examples. When creating documents, use headings, bullet points, and clean formatting. Always keep the content focused on the student experience.
```

Project instructions are useful because they make Claude’s responses more consistent.

## Project Knowledge

Project knowledge is the collection of files and documents uploaded into a project.

These files give Claude extra background information it can reference while answering questions.

Examples of useful project knowledge include:

* Meeting notes
* Reports
* Requirements documents
* Research papers
* Brand guides
* Style guides
* Templates
* Technical documentation
* Customer feedback
* Survey results
* Past examples of work

A project knowledge base is helpful because Claude does not need you to re-upload the same files every time.

## Naming Uploaded Files

File names matter.

Clear file names help Claude understand what each document is about.

Instead of using a vague name like:

```text
document1.pdf
```

Use a more descriptive name like:

```text
Q3-2026-Marketing-Plan.pdf
Student-Website-Requirements.md
Client-naming-Guidelines.pdf
```

Good file names make it easier for Claude to find and use the right information.

## Handling Large Project Knowledge

Projects can support large amounts of uploaded information.

When the uploaded knowledge gets too large to fit directly into the context window, Claude can use a retrieval-based approach. This means Claude searches for the most relevant parts of the uploaded files instead of loading everything at once.

This allows a project to handle more information while still giving focused answers.

In simple terms:

```text
Instead of reading every uploaded file at the same time, Claude finds the sections that are most relevant to your question.
```

This helps keep responses useful even when a project contains many documents.

## Working Inside a Project

Once a project is set up, every chat inside that project can use the project instructions and uploaded knowledge.

This means you can ask Claude questions like:

```text
Based on the project requirements, what are the main features we need?
```

Or:

```text
Use the meeting notes to create a summary for the team.
```

Claude can use the project context to give answers that are more specific to your work.

## Collaboration in Projects

For team and enterprise users, projects can be shared with other people.

This allows multiple team members to use the same instructions, files, and project context.

Shared projects are useful when a team needs to stay aligned.

For example, a shared project can help everyone use:

* The same templates
* The same reference documents
* The same writing style
* The same project requirements
* The same background knowledge

## Project Permission Levels

Shared projects can have different permission levels.

### View Access

People with view access can see the project and use its knowledge, but they cannot make changes to the project setup.

This is useful for people who need to reference the project but should not edit the instructions or files.

### Edit Access

People with edit access can make changes to the project. They can update instructions, add or remove knowledge, and help manage the project.

This is useful for active collaborators.

### Owner Access

The owner has full control over the project. The owner can manage sharing, visibility, instructions, files, and member access.

## Best Practices for Projects

Start with a focused project. Do not try to make one project handle everything.

Keep the knowledge base updated. Old documents can lead to outdated answers.

Write clear instructions. Vague instructions can create inconsistent responses.

Use descriptive file names. This helps Claude understand and retrieve the right documents.

Mention specific documents when needed. For example:

```text
Based on the Q3 customer feedback report, what were the biggest issues customers mentioned?
```

This helps Claude focus on the correct material.

## Questions to Ask Before Creating a Project

Before creating a project, ask yourself:

```text
Will I use this information more than once?
Am I re-uploading the same documents often?
Do I need Claude to follow the same style or process every time?
Would a team benefit from having the same shared context?
Is this work connected to a larger ongoing goal?
```

If the answer is yes, a project is probably useful.

---

# Claude Artifacts

Artifacts are separate outputs that Claude creates outside of the normal chat message. They appear in their own workspace so they are easier to view, edit, reuse, copy, or download.

Artifacts are useful when the output is more than a short answer.

Instead of placing a large document, code file, diagram, or interactive tool directly in the chat, Claude can create it as an artifact.

## When Claude Uses Artifacts

Claude may create an artifact when the content is:

* Long enough to stand on its own
* Something you may want to edit later
* Something you may want to reuse
* More complex than a regular chat response
* Better viewed in a separate panel

Examples include:

* Documents
* Code files
* Web pages
* Diagrams
* Charts
* React components
* SVG graphics
* Interactive tools

## Common Artifact Types

### Documents

Artifacts can be used for written content such as:

* Reports
* Meeting notes
* Blog posts
* Project plans
* Templates
* Briefs
* Documentation

These are useful when you want to copy, export, or keep editing the text later.

### Code

Claude can create code artifacts in many programming languages.

Examples include:

* Python scripts
* JavaScript files
* HTML pages
* CSS files
* React components
* C++ programs

A code artifact makes it easier to view and copy the code separately from the conversation.

### HTML Pages

Claude can create complete HTML pages with styling and JavaScript.

This is useful for:

* Landing pages
* Forms
* Simple prototypes
* Interactive demos
* Mock websites

### SVG Images

SVG artifacts are useful for simple graphics, icons, logos, and diagrams.

Because SVG is scalable, it can be resized without losing quality.

### Mermaid Diagrams

Mermaid artifacts can show structured diagrams such as:

* Flowcharts
* Sequence diagrams
* Timelines
* Gantt charts
* Organization charts

These are helpful when a process or system is easier to understand visually.

### React Components

React artifacts can be interactive. They can include real logic, buttons, forms, dashboards, calculators, and visualizations.

This is useful for creating quick prototypes or testing UI ideas.

## Creating an Artifact

You can ask Claude to create an artifact directly.

Example prompts:

```text
Create a reusable project brief template as an artifact.
```

```text
Build an interactive monthly budget tracker as an artifact.
```

```text
Create a flowchart showing the onboarding process.
```

```text
Design a simple landing page for a productivity app.
```

If Claude gives the answer in the chat instead of an artifact, you can say:

```text
Please turn this into an artifact.
```

## Using an Artifact

When Claude creates an artifact, you can usually:

* Preview the result
* View the underlying code or text
* Copy the content
* Download it
* Continue editing it
* Create new versions

This makes artifacts useful for work that needs to be reused or refined.

## Sharing Artifacts

Artifacts can be shared in different ways depending on your account type.

You can copy or download an artifact for personal use.

Some work accounts allow artifacts to be shared inside an organization.

Some users can publish artifacts publicly with a link.

When an artifact is published publicly, only the artifact is shared. The private chat conversation is not shared.

However, anyone with the artifact link may be able to view it, so you should not publish private, sensitive, or confidential information.

## Artifact Best Practices

Be specific about what you want Claude to create.

Instead of saying:

```text
Make a budget tool.
```

Say:

```text
Create a monthly budget tracker where I can enter expenses by category, see totals, and get a warning when spending goes over the budget.
```

Describe who the artifact is for.

For example:

```text
This diagram is for new employees, so make it simple and easy to follow.
```

Make changes step by step. It is better to ask for one improvement at a time instead of many changes at once.

If the response is large or reusable, ask Claude to make it an artifact.

## Questions to Ask Before Requesting an Artifact

Ask yourself:

```text
Will I reuse this later?
Would this be easier to edit outside the chat?
Is this a document, diagram, tool, prototype, or piece of code?
Would a visual or interactive version make this easier to understand?
```

If yes, an artifact may be the best format.

---

# Claude Skills

Skills are reusable instruction packages that help Claude complete specific tasks in a consistent way.

A skill can include instructions, resources, scripts, or examples that guide Claude through a specialized workflow.

You can think of a skill as a repeatable process that Claude can load when the task is relevant.

## Why Skills Are Useful

Skills are useful when you want Claude to follow the same method every time.

Instead of explaining a workflow repeatedly, you can create a skill once and let Claude apply it when needed.

Skills can help with:

* Document creation
* Spreadsheet generation
* Slide deck creation
* PDF creation
* Data analysis
* Brand review
* Legal review workflows
* Business report formatting
* Meeting note formatting
* Repetitive writing tasks

## Types of Skills

There are two main types of skills.

### Built-In Skills

Built-in skills are created and maintained by Anthropic.

These can support common file and document tasks, such as creating spreadsheets, presentations, documents, and PDFs.

Claude can use these automatically when your request matches the skill.

### Custom Skills

Custom skills are created by you or your organization.

They are useful for workflows that are specific to your needs.

For example, you could create a custom skill for:

* Writing quarterly business reviews
* Applying company brand guidelines
* Formatting meeting notes
* Reviewing contracts
* Creating project status reports
* Running a specific data analysis process

## Enabling Skills

Skills may need to be enabled in Claude settings.

In general, skills require file creation and code execution features because Claude may need a secure working environment to create or modify files.

To use skills, check the settings or capabilities area and make sure the needed features are enabled.

Some organization accounts may require an admin or owner to enable skills before members can use them.

## Using Skills

Most of the time, you do not need to manually select a skill.

Claude can decide when a skill is relevant based on your request.

Example prompts that may use skills:

```text
Create an Excel spreadsheet that tracks monthly expenses and calculates totals.
```

```text
Turn these meeting notes into a PowerPoint presentation.
```

```text
Generate a PDF report based on this data.
```

```text
Create a financial model with different scenarios.
```

When Claude uses a skill, it may create a downloadable file that you can save or open in a connected storage service.

## Working With Files

Skills allow Claude to work with uploaded files in a controlled environment.

For example, you can upload:

* Spreadsheets
* Presentations
* Word documents
* PDFs
* Contracts
* Reports

Claude can then create a new edited or transformed version of the file.

Important note: Claude usually creates a new version of the file instead of directly changing the original file.

This is useful because the original file stays safe while you review the new version.

## Skill Security

Because skills can include executable instructions or scripts, they should be handled carefully.

Only use custom skills from sources you trust.

If you download or receive a custom skill from someone else, review the contents before installing it.

Built-in skills from Anthropic are maintained by Anthropic, but custom skills should be checked before use.

A good security rule is:

```text
Do not install a skill unless you understand what it does and trust where it came from.
```

## Creating a Custom Skill

You can create a custom skill by explaining the workflow you want Claude to follow.

You do not always need to manually write the technical files yourself. Claude can help generate the skill structure.

A basic process for creating a custom skill is:

1. Start a new chat.
2. Tell Claude what kind of skill you want.
3. Answer Claude’s questions about the workflow.
4. Upload examples, templates, or guidelines if needed.
5. Let Claude generate the skill files.
6. Save the skill.
7. Test it and improve it over time.

Example request:

```text
I want to create a skill for writing weekly project status reports. It should use a consistent format with accomplishments, blockers, next steps, risks, and deadlines.
```

## Improving a Skill

Skills can be updated over time.

If the skill is not producing the right output, you can ask Claude to revise it.

Examples:

```text
Update this skill so it always includes a risk section.
```

```text
Revise the skill so the tone is more professional and less casual.
```

```text
Add a step that checks whether the final document follows our template.
```

This makes skills useful for workflows that improve through iteration.

---

# Projects vs. Skills

Projects and skills both give Claude more context, but they serve different purposes.

A simple way to understand the difference is:

```text
Projects store information.
Skills define procedures.
```

## Projects

Projects are best for keeping knowledge organized.

Use a project when Claude needs access to reference materials, background documents, research, meeting notes, or shared team context.

Projects answer the question:

```text
What information should Claude know?
```

Examples:

* Customer research hub
* Product documentation workspace
* Client account workspace
* Event planning project
* Class notes project

## Skills

Skills are best for repeatable workflows.

Use a skill when Claude needs to follow a process in the same way each time.

Skills answer the question:

```text
How should Claude complete this task?
```

Examples:

* Blog drafting process
* Contract review checklist
* Brand guideline review
* Weekly report generator
* Slide deck creation workflow

## How They Work Together

Projects and skills can work together.

A project can provide the information, while a skill provides the process.

Example:

```text
A customer project contains customer notes, contracts, and past emails.
A customer call prep skill tells Claude how to prepare a call agenda using that information.
```

In this case, the project gives Claude the background, and the skill tells Claude what steps to follow.

## Quick Comparison

| Feature  | Main Purpose                       | Best For                                                  |
| -------- | ---------------------------------- | --------------------------------------------------------- |
| Projects | Store shared knowledge and context | Long-term work, uploaded files, team collaboration        |
| Skills   | Run repeatable processes           | Workflows, templates, document creation, analysis methods |

## Final Summary

Claude Projects, Artifacts, and Skills each solve a different problem.

Projects help organize ongoing work and keep background knowledge available.

Artifacts are useful for creating standalone outputs that can be edited, reused, copied, downloaded, or shared.

Skills help Claude perform repeatable tasks using a consistent process.

Use projects when Claude needs to remember information.

Use artifacts when you need a reusable output.

Use skills when you want Claude to follow a repeatable workflow.
