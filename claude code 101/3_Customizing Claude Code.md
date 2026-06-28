# Customizing Claude Code

## CLAUDE.md

One of the most useful ways to customize Claude Code is by using a `CLAUDE.md` file. This file gives Claude Code persistent project memory, so it does not have to rediscover the same information every time you start a new session.

Without a `CLAUDE.md` file, Claude Code starts fresh. It may need to re-explore the codebase, understand the project structure, identify dependencies, and figure out what has already been implemented. This can lead to repeated explanations, incorrect assumptions, and more time spent steering Claude in the right direction.

A `CLAUDE.md` file solves this by acting like an onboarding guide for your project. You place it in the root of your project, and Claude Code reads it automatically when a session starts.

Example:

```md
# Project

This is a Next.js 15 app using the App Router, Tailwind CSS, and Drizzle ORM.

# Commands

- Start development server: `pnpm dev`
- Run tests: `pnpm test`
- Run linting: `pnpm lint`

# Code Style

- Use 2-space indentation.
- Prefer named exports.
- Place API routes inside `app/api/`.
- Use server actions instead of API routes when possible.
```

With this file, Claude already knows your stack, commands, and coding preferences before it starts making changes.

## Team and Personal Memory

There are different levels of Claude memory.

A project-level `CLAUDE.md` file lives in the root of the project. This file should be committed to version control so the entire team can share the same project context.

A user-level `CLAUDE.md` file lives in your personal Claude configuration folder. This file is only for your own preferences and can apply across multiple projects.

Project-level memory should include information that benefits the whole team, such as project architecture, commands, conventions, and important rules.

User-level memory should include personal preferences, such as how you like explanations, commit messages, documentation, or code style.

## Tips for CLAUDE.md

If you repeatedly correct Claude about the same thing, add that rule to `CLAUDE.md`.

For example, if Claude keeps creating API routes when your project prefers server actions, add a rule like:

```md
# Important Rules

- Prefer server actions instead of API routes when possible.
```

You can also reference important project files using the `@` symbol:

```md
# Project Documentation

Read the README for more context: @README.md
```

A good approach is to start without a `CLAUDE.md` file, notice where Claude needs repeated correction, and then add only the most useful rules. This keeps the file focused and prevents it from becoming too large.

## Subagents

Subagents allow Claude Code to delegate specific tasks to smaller specialized agents. Each subagent works in its own isolated context window.

This is useful because the main Claude session has limited context. If Claude spends a lot of time exploring files, searching documentation, or analyzing a large codebase, that information can fill up the main context window quickly.

A subagent can handle a task such as exploring the codebase, reviewing files, or researching a specific issue. When it finishes, it returns a summary to the main Claude session instead of bringing back every detail.

This keeps the main conversation cleaner and more focused.

## Creating a Subagent

To create a subagent, run:

```bash
/agents
```

Then choose “Create new agent.”

Claude will guide you through the setup process. You can define the agent’s purpose, choose its scope, select which tools it can use, and customize its behavior.

Subagents are defined using Markdown files with YAML frontmatter. Claude can generate the initial configuration for you.

A subagent can be used for tasks such as:

* Exploring a codebase
* Reviewing code
* Searching for bugs
* Summarizing project structure
* Researching documentation
* Checking security concerns

For code review, it is best to limit the subagent to read-only tools. A reviewer should identify problems, not edit files directly.

## Skills

Skills help Claude Code perform repeated tasks more accurately and efficiently.

A skill is usually a folder that contains instructions, scripts, and resources for a specific type of work. Instead of repeating the same guidelines every time, you can create a skill that Claude can load when needed.

In Claude Code, a skill includes a `SKILL.md` file. The description in that file helps Claude decide when the skill should be used.

Personal skills go in:

```text
~/.claude/skills
```

These follow you across projects and can store your personal preferences, such as commit message style, documentation format, or how you like code explained.

Project skills go in:

```text
.claude/skills
```

These are shared with anyone who clones the project.

The main difference between `CLAUDE.md` and skills is how they load into context.

`CLAUDE.md` loads into every conversation. Use it for information Claude should always know.

Skills only load their name and description at first. Claude loads the full skill only when it decides the skill is relevant. This makes skills more context-efficient.

Use `CLAUDE.md` for always-needed project rules.

Use skills for repeatable workflows that are only needed sometimes.

## MCP

MCP stands for Model Context Protocol. It is an open standard that allows Claude Code to connect to external tools and data sources.

A lot of useful project context lives outside the codebase. It may be in databases, project management tools, documentation websites, GitHub repositories, or other services. MCP allows Claude Code to access those tools when needed.

For example, an MCP server can connect Claude Code to:

* Linear issues
* GitHub repositories
* Databases
* Internal documentation
* Cloud services
* Public documentation sources

MCP gives Claude access to tools that can help it complete tasks more effectively.

## Adding MCP Servers

You can add MCP servers using:

```bash
claude mcp add
```

There are two main types of MCP servers.

HTTP servers are remote services hosted over the network.

Stdio servers are local processes that run on your machine.

Inside Claude Code, you can manage MCP servers with:

```bash
/mcp
```

This lets you see which servers are connected, check their status, and disable servers you do not need.

## MCP Scopes

MCP servers can have different scopes.

Local MCP servers are only available in the current project and only for you.

User MCP servers are available across all your projects.

Project MCP servers are defined in a `.mcp.json` file and can be checked into version control so the whole team uses the same setup.

## MCP and Context Cost

MCP servers add tool definitions to Claude’s context window. Even if you are not actively using a server, its tools may still consume context.

If you have too many MCP servers enabled, they can reduce the amount of space available for your actual task.

Use `/mcp` to disable servers you are not currently using.

If a tool has a command-line version, such as `gh` for GitHub or `aws` for AWS, using the CLI may be more context-efficient than using an MCP server.

Skills can also be more context-efficient than MCP because Claude only loads the full skill when needed.

## Hooks

Hooks allow you to run commands at specific points in Claude Code’s workflow.

The main difference between hooks and prompts is that hooks are deterministic. A prompt is a suggestion, but a hook always runs.

For example, you can tell Claude in `CLAUDE.md` to run Prettier after editing files. Most of the time it may do it, but it is not guaranteed.

A hook guarantees that formatting runs after every edit.

Common uses for hooks include:

* Auto-formatting files after edits
* Logging commands for compliance
* Blocking dangerous commands
* Preventing changes to production files
* Sending notifications when Claude finishes a task

## Hook Events

Hooks are configured in `settings.json`.

Common hook events include:

```text
PreToolUse
PostToolUse
UserPromptSubmit
Stop
Notification
```

`PreToolUse` runs before a tool call.

`PostToolUse` runs after a tool call completes.

`UserPromptSubmit` runs when you submit a prompt, before Claude processes it.

`Stop` runs when Claude finishes responding.

`Notification` runs when Claude sends a notification.

You can configure hooks by using:

```bash
/hooks
```

Or by editing `settings.json` directly.

## Blocking Dangerous Actions

`PreToolUse` hooks can block dangerous actions before they happen.

For example, a hook can block:

* `rm -rf`
* Writes to production config files
* Commits directly to `main`
* Changes to protected directories

A `PreToolUse` hook receives the tool name and input as JSON through stdin.

The exit code controls what happens:

```text
Exit code 0: allow the action
Exit code 2: block the action
Any other exit code: show a non-blocking error
```

This is useful for enforcing hard rules that must always be followed.

## Sharing Hooks With a Team

Project-level hooks can be stored in:

```text
.claude/settings.json
```

This file can be committed to the repository so the entire team gets the same hooks.

Use the `CLAUDE_PROJECT_DIR` environment variable in hook commands so scripts work regardless of Claude’s current working directory.

## Recap

Claude Code can be customized with `CLAUDE.md`, subagents, skills, MCP servers, and hooks.

Use `CLAUDE.md` for project memory and team rules.

Use subagents to keep the main context clean.

Use skills for repeatable workflows.

Use MCP to connect Claude Code to external tools and data sources.

Use hooks when something must happen every time without fail.

---
These are my personal study notes based on Anthropic materials. The notes are written in my own words and are not an official Anthropic resource. Original material copyright 2025 Anthropic. All rights reserved.