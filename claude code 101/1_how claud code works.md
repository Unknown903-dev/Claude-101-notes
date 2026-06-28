# How Claude Code Works

## Agentic Loops

Claude Code works through an agentic loop.

An agentic loop means Claude does not just answer with text. It can understand a goal, gather context, use tools, take actions, verify results, and continue working until the task is complete.

A simple version of the loop looks like this:

```text
Prompt → Gather Context → Take Action → Verify Results → Repeat if Needed
```

## Step 1: You Enter a Prompt

The process starts when you give Claude Code a prompt.

Example:

```text
Add a dark mode toggle to the app header. It should switch the full app between light mode and dark mode.
```

Claude reads the prompt and determines what information it needs before acting.

## Step 2: Claude Gathers Context

Claude then gathers context.

It may read files, inspect the project structure, search through code, or use tools to understand how the project works.

This is important because Claude needs to know where changes should be made and what conventions the project already follows.

## Step 3: Claude Takes Action

After understanding the task, Claude can take action.

Depending on permissions, it may:

* Read files
* Edit files
* Create files
* Run commands
* Search documentation
* Execute tests
* Inspect command output

This is what makes Claude Code different from a normal chatbot. It can use tools to work directly inside a project.

## Step 4: Claude Verifies the Result

After taking action, Claude checks whether the result matches the original goal.

It may run tests, inspect files again, review output, or troubleshoot errors.

If the task is complete, Claude stops and waits for the next prompt.

If the result is not correct, Claude loops back, makes adjustments, and verifies again.

## Step 5: You Can Steer the Process

During this loop, you can interrupt, add context, or correct Claude.

For example, you can say:

```text
Do not use that library. Use the package we already have installed.
```

Or:

```text
That file is not the right place. Check the components folder instead.
```

This helps guide Claude toward the correct result.

## Context Window

Claude has a context window.

The context window is the amount of information Claude can hold in memory during a session.

The context window can include:

* Your prompts
* Claude’s responses
* File contents
* Command outputs
* Tool results
* Error messages
* Project context

Because the context window is limited, it is important to manage it carefully.

When the context gets too full, Claude Code may compact the conversation. Compaction summarizes older information and removes unnecessary details so the session can continue.

Compaction is helpful, but it can lose some details. Important project rules should be saved in `CLAUDE.md` instead of relying only on the conversation.

## Tools

Tools are the backbone of how Claude Code works.

Most AI assistants only receive text and return text. Claude Code can use tools to interact with the project and complete tasks.

Tools can allow Claude to:

* Read files
* Edit files
* Run terminal commands
* Search the web
* Inspect a codebase
* Use connected services
* Validate results

Claude uses semantic understanding to decide when a tool is needed and how to use the result.

## Permissions

Claude Code has several permission modes.

## Default Approval Mode

In the default mode, Claude asks for permission before editing files or running shell commands.

This gives you more control and lets you review changes before they happen.

Use this mode when you want to stay closely involved.

## Auto-Accept Mode

In auto-accept mode, Claude can automatically accept file edits.

However, commands still require approval.

This mode is faster, but you should use it carefully.

Use auto-accept when you trust the task and want Claude to move faster.

## Plan Mode

Plan Mode is a read-only mode.

Claude can inspect the project and create a plan, but it cannot edit files.

This is useful for complex changes because it lets Claude understand the codebase before writing code.

To enter Plan Mode, press:

```text
Shift + Tab
```

Cycle through the options until Plan Mode is enabled.

A good Plan Mode prompt looks like this:

```text
My app needs a dark mode toggle across the entire app. Create a plan for how to implement it. Find the best place to add the toggle, identify the files that need to change, and explain how the theme should be handled. Do not edit files yet.
```

After Claude gives you the plan, review it. If the plan is good, approve it and let Claude begin implementation.

## Installing Claude Code

Claude Code can be installed and used in several places:

* Terminal
* Visual Studio Code
* JetBrains IDEs
* Claude Desktop
* Claude Web

## Terminal

The terminal version is often the best option if you want access to the newest features first.

On macOS, Linux, or WSL, Claude Code can be installed through a terminal command.

After installation, you should be able to run:

```bash
claude
```

If the command does not work immediately, restart the terminal.

Navigate to your project directory and run:

```bash
claude
```

Claude will then start inside that project folder.

Claude Code will have access to the directory where you run it and all subfolders inside that directory.

## Visual Studio Code

To use Claude Code in VS Code:

1. Open the Extensions panel.
2. Search for “Claude Code.”
3. Install the extension from Anthropic.
4. Restart VS Code if needed.
5. Open the Command Palette with `Cmd + Shift + P` or `Ctrl + Shift + P`.
6. Search for “Claude Code Open in New Tab.”

The VS Code extension gives you an experience similar to the terminal, but integrated with your editor.

## JetBrains

To use Claude Code in a JetBrains IDE:

1. Open the JetBrains Marketplace.
2. Search for the Claude Code plugin.
3. Install it.
4. Restart the IDE.
5. Click the Claude logo to open Claude Code.

This gives you a Claude Code panel inside your IDE.

## Claude Desktop

Claude Desktop includes a Code mode.

After installing and signing in, you can use the Code toggle to work with a specific folder, change permissions, and use Claude Code from the desktop app.

This can be useful if you want Claude to work while you handle other tasks.

## Claude Web

Claude Code is also available through the web at:

```text
claude.ai/code
```

The web version is useful for working with GitHub repositories remotely.

However, the web version is more limited because it is restricted to GitHub repositories.

## Which Version Should You Use?

Use the terminal if you want the newest Claude Code features first.

Use VS Code or JetBrains if you want Claude Code inside your editor.

Use Claude Desktop if you want a more app-based workflow.

Use Claude Web if you want to work remotely through GitHub repositories.

## Writing Your First Prompt

When writing a prompt for Claude Code, be specific.

Instead of saying:

```text
Add dark mode.
```

Write:

```text
Add a dark mode toggle to the app header. The toggle should switch the entire app between light mode and dark mode. Use the existing theme colors and choose a dark mode color palette with good contrast. Start in Plan Mode and do not edit files until I approve the plan.
```

A detailed prompt helps Claude understand the goal, constraints, and success criteria.

## Auto-Accept vs Approval

You can switch between permission modes using:

```text
Shift + Tab
```

Approval mode is safer because Claude asks before making edits or running commands.

Auto-accept mode is faster because Claude can apply file edits automatically.

Plan Mode is safest for complex tasks because Claude can only inspect and plan.

## Example Prompt: Dark Mode Toggle

Here is a good first prompt:

```text
My app needs dark mode implemented across the entire app. Create a toggle switch in the header that lets the user switch between light mode and dark mode. Use my existing light theme as the base and choose dark mode colors with strong contrast. Start by analyzing the project structure in Plan Mode. Do not edit files until I approve the plan.
```

This prompt is strong because it explains:

* What feature is needed
* Where the feature should appear
* What design constraint matters
* That Claude should use Plan Mode first
* That Claude should not edit files without approval

## Recap

Claude Code works through an agentic loop.

It reads your prompt, gathers context, uses tools, takes action, verifies results, and repeats until the task is complete.

The context window is Claude’s working memory, so it should be managed carefully.

Tools allow Claude Code to read files, edit code, run commands, and verify work.

Permission modes let you control how much freedom Claude has.

Use Plan Mode for complex changes.

Use detailed prompts to get better results.
