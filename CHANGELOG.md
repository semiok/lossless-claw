# @martian-engineering/lossless-claw

## 0.3.1

### Patch Changes

- 6c54c7b: Declare explicit OpenClaw tool names for the LCM factory-registered tools so
  plugin metadata and tool listings stay populated in hosts that require
  `registerTool(..., { name })` hints for factory registrations.
- 9ee103a: Fix condensed summary expansion so replay walks the source summaries that were compacted into a node, and skip proactive compaction when turn ingest fails to avoid compacting a stale frontier.
- 45f714c: Forward delegated `lcm_expand_query` provider and model overrides to OpenClaw subagent runs.
  This fixes expansion override settings that were parsed from config but not applied at runtime.
- 7fae41c: Fix assembler round-tripping for tool results so structured `tool_result` content is preserved and normalized tool metadata no longer inflates context token budgeting.
- 82becaf: Remove hardcoded non-LCM recall tool names from the dynamic summary prompt so
  agents rely on whatever memory tooling is actually available in the host
  session.
- 828d106: Improve LCM summarization model resolution so configured `summaryModel`
  overrides, OpenClaw `agents.defaults.compaction.model`, and newer
  `runtimeContext` inputs are honored more reliably while preserving
  compatibility with older `legacyCompactionParams` integrations.

## 0.3.0

### Minor Changes

- f1dfa5c: Catch up the release notes for work merged after `0.2.8`.

  This release adds Anthropic OAuth setup-token support in the TUI, resolves
  SecretRef-backed auth-profile credentials and provider-level custom provider
  configuration during summarization, and formats LCM tool timestamps in the local
  timezone instead of UTC.
