# annotated-bibliography

Research skill for the TritonAI harness (Codex-based) that creates comprehensive, faithful annotated bibliographies — representing what sources actually claim and classifying connections as direct evidence, reasonable inference, or interpretive connection.

## Origins

- **Author**: Doug Worsham, Digital Experience Manager, UC San Diego Library; developed with AI assistance.
- **First version**: 2026-02-12 (package metadata). No standalone creation record exists for this skill.
- **Motivation**: counter the "helpful but unfaithful" failure mode in which AI bibliographies distort or exaggerate sources to fit a hypothesis. Shares its three-level evidence classification with the companion skill `claim-evaluation-skill`.
- **Domain signals**: worked examples reference design and UX research (e.g., Cross 2004; Wiltschnig et al., 2013), consistent with the author's digital experience role at UC San Diego Library.

## Development History

- **2026-02-12** — Initial version, distributed as a Claude-style `.skill` ZIP archive (`annotated-bibliography.skill`).
- **2026-09-15** — Brought into `dx-tools` (commit `128176c`) as a plain skill directory; the `.skill` ZIP was removed and this directory became the source of truth.
- **2026-09-15** — Adapted for the TritonAI/Codex harness: the `web_fetch` instruction was replaced with the collaborative browser (`preview_navigate` / `preview_snapshot` / `preview_evaluate`) and `exec_command` guidance for reading sources.

## Status

Ready for harness use. Not yet installed into `~/.tritonai-harness/codex/skills/` — see the repo root README for install steps.
