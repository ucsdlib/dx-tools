# DX Tools — Skills for TritonAI / Codex

A small collection of skills for the TritonAI harness (a Codex-based agent). These directories are the source-controlled versions of the skills and are synced to GitHub for sharing with the team. Each skill is a standard Codex skill: a directory containing a `SKILL.md` with `name` and `description` frontmatter, plus optional `references/`.

## Skills

| Skill | Purpose | Origin | Harness status |
|---|---|---|---|
| [`annotated-bibliography`](annotated-bibliography/) | Research-grade annotated bibliographies that represent sources faithfully and classify evidence | 2026-02-12 | Ready; not yet installed |
| [`claim-evaluation-skill`](claim-evaluation-skill/) | Claim verification: evidence classification, source checks, confidence ratings | 2026-02-12 | Ready; not yet installed |
| [`creation-record`](creation-record/) | Creation notes/records documenting AI and human contribution, incl. JSON-LD | 2026-06-04 (v1.3) | Installed |
| [`uc-library-search`](uc-library-search/) | High-fidelity search strategies and direct links for UC Library Search (Primo VE); adapted from the TritonGPT query generator, with URLs verified live against search-library.ucsd.edu | 2026-09-15 | Installed |

## Installing into the TritonAI harness

Copy or symlink each skill directory into the harness skills location:

```bash
cp -R annotated-bibliography claim-evaluation-skill creation-record uc-library-search ~/.tritonai-harness/codex/skills/
```

Skills load on the next turn or session. `creation-record` is already installed there.

## Origins and development

- Authored by **Doug Worsham**, Digital Experience Manager, UC San Diego Library, with AI assistance (developed iteratively with Claude, Anthropic).
- `creation-record` documents its own creation in [`creation-record/references/skill-creation-record.md`](creation-record/references/skill-creation-record.md).
- `annotated-bibliography` and `claim-evaluation-skill` were built to counter "helpful but unfaithful" AI behavior in research and writing tasks; they share a three-level evidence classification (direct evidence / reasonable inference / interpretive connection).
- **2026-09-15** — the collection was added to this repo (commit `128176c`). Skills were previously distributed as Claude-style `.skill` ZIP files; the plain directories here are now the source of truth and the ZIPs were removed.
- **2026-09-15** — adapted for the TritonAI/Codex harness: search/read guidance now maps to the collaborative browser (`preview_*`) and `exec_command`, and `creation-record` model identification is provider-agnostic (Codex/OpenAI alongside Claude/Anthropic).
- **2026-09-15** — added `uc-library-search`, adapted from the TritonGPT "UC Library Search Query Generator" system prompt with the values-based workflow preserved (never summarize literature; clarify first, scaled to the request; high-precision strategies). Primo VE URL mechanics were verified live against `search-library.ucsd.edu`: links use the single-parameter `query=` format, and the chained `query=...,AND&query=...` format is documented as unreliable on this instance. `scripts/build_url.py` builds verified links deterministically. Testing log: [`uc-library-search/.testing-log.md`](uc-library-search/.testing-log.md).

## Rebuilding a `.skill` ZIP (optional)

Claude Code consumes skills as single-file `.skill` ZIP packages. Rebuild one from its directory if needed:

```bash
zip -r annotated-bibliography.skill annotated-bibliography/
```

## License

`creation-record` is MIT-licensed (© 2026 Doug Worsham). The other three skills do not yet carry a license — decide and add one before public sharing if needed.

## Creation record — `uc-library-search`

**Work identification**
- Title: UC Library Search skill (`uc-library-search`)
- Type: TritonAI/Codex skill — Markdown guidance, Python helper script, documentation
- Date: 2026-09-15 (v1.0)
- Audience: UC San Diego Library digital experience team and the TritonAI/Codex harness
- Stage: Finalized

**AI contribution summary**
- Contribution: AI-Assisted (multi-party) — human-authored framework with substantial AI
  implementation and verification
- AI systems and roles:
  - **Claude (Anthropic; version unspecified)** — co-authored the source TritonGPT system
    prompt with Doug: research into search-query best practices, Primo VE syntax drafting,
    and workflow design (Writing – Original Draft)
  - **Codex (OpenAI Codex CLI harness, served via TritonAI as `api-deepseek-v4-flash`)** —
    adapted the system prompt into a skill package: authored `SKILL.md`, `references/`, and
    `scripts/build_url.py`; performed live URL verification against `search-library.ucsd.edu`
    (Technical Documentation, Software, Validation/Testing and QA)
- Prompt characterization: iterative with human source material — Doug's expert-authored
  system prompt was the source; multiple directed rounds refined structure, content, and policy

**Human contribution summary**
- **Doug Worsham** — Digital Experience Manager, UC San Diego Library
  - Roles: Conceptualization, Methodology, Writing – Original Draft (with Claude), Supervision
  - Contribution: researched and authored the source system instructions (co-authored with
    Claude) covering high-fidelity search best practices and Primo VE syntax; set the
    values-based requirements (no literature summarization, staged clarifying workflow, balanced
    precision/recall); directed the technical-accuracy work; and made the product decisions —
    needs-based clarifying questions, verified single-parameter URL format only, filtered URL
    variants, and placement in `dx-tools` for team sharing
- Reviewed and approved by: Doug Worsham

**Process narrative**
The tool began as a TritonGPT system prompt Doug co-authored with Claude, defining how an
assistant should build UC Library Search strategies. Before adapting it, the Codex agent
verified the prompt's URL-construction claims live against `search-library.ucsd.edu`,
confirming the single-parameter `query=` format, field codes, and filter parameters — and
discovering that the prompt's chained-parameter example URLs mis-execute on the live instance.
That evidence set the technical baseline for the skill.

The Codex agent then restructured the prompt into the skill package — core workflow in
`SKILL.md`, a verified syntax reference, a response template with a worked example, and a
deterministic URL builder script with self-tests — under Doug's direction. Doug reviewed the
testing results, refined the clarifying-question policy to scale with request detail, and
approved sharing the skill through this repo. Testing evidence is logged in
[`uc-library-search/.testing-log.md`](uc-library-search/.testing-log.md).

**Responsibility statement**
Doug Worsham, Digital Experience Manager, UC San Diego Library, reviewed and approved this
work and accepts responsibility for its accuracy and fitness for its intended use.
