# Daily Claude Code Workflow

## Explore → Plan → Code → Commit

A strong Claude Code workflow follows four steps:

```text
Explore → Plan → Code → Commit
```

This workflow helps prevent mistakes because it keeps Claude from jumping straight into writing code before understanding the project.

## Explore

The first step is exploration.

Claude should inspect the relevant files, understand the codebase, identify the current structure, and learn how the feature should fit into the project.

This step is important because Claude needs context before making changes. Without exploration, it may make incorrect assumptions or edit the wrong files.

A good exploration prompt looks like this:

```text
Explore the project and identify where this feature should be implemented. Do not edit any files yet. First, explain the relevant files, dependencies, and current structure.
```

## Plan

The next step is planning.

Plan Mode is useful because Claude can read files and gather context without editing anything. This makes it safer for complex changes.

To enter Plan Mode, press:

```text
Shift + Tab
```

Cycle until you see Plan Mode enabled.

Then give Claude a prompt like:

```text
I need to add WebP conversion to our image upload pipeline. Figure out where in the pipeline it should happen, whether we need new dependencies, and how we should approach the implementation. Do not edit files yet. Give me a plan first.
```

Claude will review the project and return a plan.

This is the best time to correct Claude because no code has been written yet. If the plan is wrong, ask Claude to revise it before approving implementation.

## Code

After the plan looks good, approve it and let Claude begin coding.

During the coding phase, Claude will make changes, run commands, test results, and troubleshoot issues.

You can decide whether Claude should ask permission for every edit or automatically accept file edits.

For smoother coding, define success criteria clearly.

Example:

```text
The feature is complete when:
1. Users can upload an image.
2. The image is converted to WebP.
3. The original file is not stored.
4. The converted image is saved successfully.
5. Existing upload tests still pass.
```

Clear success criteria help Claude know when the task is actually finished.

## Useful Coding Tips

Be specific with your prompt. A detailed prompt usually saves context and time because Claude does not have to guess.

Give Claude access to useful tools when appropriate.

For web UI work, a browser tool can help Claude test the interface directly.

For backend work, tests are very important. Claude can write tests, but you should make sure the tests actually verify the correct behavior.

If Claude repeatedly runs into the same issue, ask it to save the solution to `CLAUDE.md`.

Example:

```text
Save this rule to CLAUDE.md: this project uses server actions instead of API routes whenever possible.
```

## Commit

After Claude finishes the implementation, test the changes yourself.

Before committing, ask a code-review subagent to review the changes.

A subagent is useful because it has a fresh context window. It does not carry the same assumptions as the main Claude session that wrote the code.

A good review prompt:

```text
Use a read-only code review subagent to review the current changes. Look for bugs, security issues, missing tests, broken conventions, and unnecessary complexity. Do not edit files. Return a prioritized list of issues.
```

After reviewing and fixing any issues, ask Claude to generate a commit message.

Example:

```text
Write a clear commit message for these changes using my usual style.
```

## Context Management

Context is Claude’s working memory.

Every prompt, file, command output, and tool result uses space in the context window. Since this space is limited, you need to manage it carefully.

When the context window gets too full, Claude Code may compact the conversation. Compaction summarizes previous information and removes details to free up space.

This is useful, but some details can be lost during compaction.

## Useful Context Commands

Use this command to manually compact the conversation:

```bash
/compact
```

Use this when you are still working on the same feature but need to free up context space.

Use this command to completely clear the session:

```bash
/clear
```

Use this when you are starting a new feature and do not want the previous conversation to influence Claude.

Use this command to check context usage:

```bash
/context
```

This shows how much context is being used and what is taking up space.

## When to Use /compact vs /clear

Use `/compact` when you are continuing the same feature and want Claude to keep a summary of the previous work.

Use `/clear` when you are starting a new task or feature and want a clean session.

Important long-term project information should go into `CLAUDE.md`, not just the conversation. That way Claude does not need to rediscover it every session.

## Saving Context Space

To save context, write specific prompts.

A vague prompt may look shorter, but it can cause Claude to explore more files and use more context. A detailed prompt can actually save space because Claude knows exactly what to look for.

Also manage MCP servers carefully. MCP servers can add tool definitions to the context window even when they are not being used.

Disable MCP servers that are not relevant to the current task.

Use subagents when you only need a summary of a task. For example, a subagent can answer:

```text
Where are the authentication endpoints located?
```

Then it can return only the useful summary to the main Claude session.

## Code Review

Before pushing a pull request, use a code-review subagent.

The reviewer should use read-only tools. Its job is to identify issues, not change files.

A good reviewer should check for:

* Bugs
* Security problems
* Broken conventions
* Missing tests
* Overly complex code
* Incorrect assumptions
* Poor error handling

## Commit, Push, and PR

Claude Code can help with the Git workflow.

A commit/push/PR skill can handle:

```text
Commit → Push → Create Pull Request
```

If a Slack MCP server is configured and channels are listed in `CLAUDE.md`, Claude can also post the PR link to the team channel.

## Resuming Work From a PR

If Claude creates a PR using GitHub CLI, the session can be linked to that PR.

To resume work later, use:

```bash
claude --from-pr <PR_NUMBER>
```

This helps Claude pick up the context from that pull request.

## Recap

The best daily Claude Code workflow is:

```text
Explore → Plan → Code → Commit
```

Explore the codebase before making changes.

Use Plan Mode for complex tasks.

Define success criteria before coding.

Use tests to verify the work.

Use subagents for code review.

Use `/compact`, `/clear`, and `/context` to manage context.

Use `CLAUDE.md` for long-term project memory.
