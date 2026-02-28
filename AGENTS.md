# Session bootstrap

- At the start of every new session, read:
  - `/Users/saeed/Projects/8-clawb/.codex/memory/initialize.md`
  - `/Users/saeed/Projects/8-clawb/.codex/memory.md`
- Use that memory as persistent context before editing docs.
- If a memory file is missing, continue and report once.
- Never write secrets into git-tracked files.

# Docs mission

- This repo is for `docs.clawb.ai`.
- Primary audience: junior software engineers at enterprise companies integrating many agents.
- Canonical language: workspace / enterprise security / control plane.
- Avoid outdated terminology unless required by API field names.

## Mintlify rules

- Configuration lives in `docs.json`; review it before structural changes.
- Use MDX and Mintlify components.
- Prefer `<CodeGroup>` for code snippets:
  - Use it for multi-language alternatives (`Python SDK`, `curl`, `TypeScript`).
  - Use it for single snippets too, so language labels are visible above code.
  - Keep code inside `<RequestExample>` / `<ResponseExample>` unchanged unless explicitly requested.
- Use `<Tabs>` for platform or conceptual variants, not language-only code examples.

## Writing style

- Use active voice and second person ("you").
- Keep sentences concise.
- Use sentence case headings.
- Use realistic enterprise examples (`agent_id`, policies, audit/trace context).
- Prefer concrete action/context examples (for example refund amount, actor, approval path).

## Content requirements

- Add frontmatter (`title`, `description` when needed).
- Include prerequisites and expected outcomes for implementation pages.
- Include at least one happy-path plus one failure-handling note for major workflows.
- Use exact endpoint/method notation (`POST /v1/check`, `POST /v1/verify`).

## Don’ts

- Don’t edit `docs.json` blindly.
- Don’t remove pages without checking inbound links.
- Don’t use placeholders like `foo` / `bar` in primary examples.
- Don’t use `provider` as the actor term unless it is an actual API field.

# Delivery workflow

1. Create a branch.
2. Commit with clear scope.
3. Push and open PR to `main`.
4. Use squash merge.
5. Merge only if checks pass or no checks are required.
6. Switch back to `main` and pull latest.

## PR policy

- Title format: `<type>: <short summary>`.
- PR body sections: `Summary`, `Testing`, `Risks`.

## Safety

- Do not auto-merge if there are merge conflicts.
- Do not auto-merge if required checks fail.
- Do not auto-merge draft PRs.
