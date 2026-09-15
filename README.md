# DX Tools — Skills for TritonAI / Codex

A small collection of skills for the TritonAI harness (a Codex-based agent). These directories are the source-controlled versions of the skills and are synced to GitHub for sharing with the team. Each skill is a standard Codex skill: a directory containing a `SKILL.md` with `name` and `description` frontmatter, plus optional `references/`.

## Skills

| Skill | Purpose | Origin | Harness status |
|---|---|---|---|
| [`annotated-bibliography`](annotated-bibliography/) | Research-grade annotated bibliographies that represent sources faithfully and classify evidence | 2026-02-12 | Ready; not yet installed |
| [`claim-evaluation-skill`](claim-evaluation-skill/) | Claim verification: evidence classification, source checks, confidence ratings | 2026-02-12 | Ready; not yet installed |
| [`creation-record`](creation-record/) | Creation notes/records documenting AI and human contribution, incl. JSON-LD | 2026-06-04 (v1.3) | Installed |

## Installing into the TritonAI harness

Copy or symlink each skill directory into the harness skills location:

```bash
cp -R annotated-bibliography claim-evaluation-skill creation-record ~/.tritonai-harness/codex/skills/
```

Skills load on the next turn or session. `creation-record` is already installed there.

## Origins and development

- Authored by **Doug Worsham**, Digital Experience Manager, UC San Diego Library, with AI assistance (developed iteratively with Claude, Anthropic).
- `creation-record` documents its own creation in [`creation-record/references/skill-creation-record.md`](creation-record/references/skill-creation-record.md).
- `annotated-bibliography` and `claim-evaluation-skill` were built to counter "helpful but unfaithful" AI behavior in research and writing tasks; they share a three-level evidence classification (direct evidence / reasonable inference / interpretive connection).
- **2026-09-15** — the collection was added to this repo (commit `128176c`). Skills were previously distributed as Claude-style `.skill` ZIP files; the plain directories here are now the source of truth and the ZIPs were removed.
- **2026-09-15** — adapted for the TritonAI/Codex harness: search/read guidance now maps to the collaborative browser (`preview_*`) and `exec_command`, and `creation-record` model identification is provider-agnostic (Codex/OpenAI alongside Claude/Anthropic).

## Rebuilding a `.skill` ZIP (optional)

Claude Code consumes skills as single-file `.skill` ZIP packages. Rebuild one from its directory if needed:

```bash
zip -r annotated-bibliography.skill annotated-bibliography/
```

## License

`creation-record` is MIT-licensed (© 2026 Doug Worsham). The other two skills do not yet carry a license — decide and add one before public sharing if needed.
