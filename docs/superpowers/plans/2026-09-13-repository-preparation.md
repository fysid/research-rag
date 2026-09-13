# Repository Preparation Implementation Plan

**Goal:** Prepare fysid/research-rag for LLM-driven development on AnythingLLM.

**Architecture:** Preserve the upstream application and history. Add contribution metadata and CI restrictions, then publish one reviewable preparation PR.

**Tech stack:** Git, GitHub, Markdown, YAML, existing AnythingLLM scripts.

**Spec:** [repository design](../specs/2026-09-13-repository-design.md).

## Constraints

- Repository `fysid/research-rag`; base `master`; branch `codex/repository-bootstrap`.
- No application behavior changes, model installation or paid LLM automation.
- Preserve LICENSE and existing application checks.

## Task 1: Metadata and fork policy

- [ ] Add AGENTS.md, docs/LLM_DEVELOPMENT.md, docs/UPSTREAM.md and docs/ROADMAP.md.
- [ ] Add README/CONTRIBUTING introductions, CODEOWNERS and LLM Issue form; replace PR template.
- [ ] Extend .gitignore for local RAG data and agent scratch files.
- [ ] Gate upstream publication/cleanup/sponsor jobs; add Repository checks with a verified checkout SHA.
- [ ] Parse YAML, verify links/files and run `git diff --check`; independently review the diff.

## Task 2: Publish and verify

- [ ] Publish one commit on codex/repository-bootstrap.
- [ ] Enable Issues; open PR against this fork's master.
- [ ] Keep publication workflows inactive, enable Actions and observe Repository checks.
- [ ] Configure master PR/check requirements if available and verify actual settings.
- [ ] Report repository/PR links, checks and limitations for owner acceptance.
