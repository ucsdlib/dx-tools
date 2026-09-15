---
name: annotated-bibliography
description: Create comprehensive, research-grade annotated bibliographies that accurately represent sources and distinguish between direct evidence, reasonable inference, and interpretive connection. Use when user requests "annotated bibliography on [topic]", "comprehensive research on [question]", "sources for and against [claim]", literature reviews, or "what does research say about [topic]".
---

This skill guides creation of faithful, comprehensive annotated bibliographies that prioritize accurate source representation over making arguments work. The user provides a research question or topic requiring multiple sources with critical analysis.

## Core Principles

### 1. Faithful Over Helpful
- Represent what sources actually claim, not what would support hypotheses
- Use direct quotes extensively
- Flag when making inferences beyond source text
- Report null findings or absence of evidence honestly
- **NEVER manufacture controversy** - report honestly what literature shows

### 2. Comprehensive Search Strategy
Search across MULTIPLE perspectives in phases:
- **Phase 1 (3-5 searches)**: Core concepts directly
- **Phase 2 (2-4 searches)**: Contrasting views - "critique of [X]", "[X] limitations", alternative frameworks
- **Phase 3 (2-3 searches)**: Different methods - empirical studies, reviews, theoretical papers, practitioner sources
- **Phase 4 (1-3 searches)**: Fill gaps - historical sources, recent developments, related domains

**Total: 8-15 searches for comprehensive work**

### 3. Verify Before Annotating
- Always search and access original sources
- Read full text when available, abstracts when necessary
- Never rely on memory about sources
- Note access level (full text / abstract only)
- Read complete articles when URLs are provided: open them in the collaborative browser
  (`preview_navigate` -> `preview_snapshot` / `preview_evaluate` to extract text); read
  local files directly with `exec_command`. This harness has no `web_search`/`web_fetch`
  tools - run searches through the browser (e.g., Google Scholar, publisher sites,
  library databases) for any web-sourced content.

## Understanding the Research Question

Before searching, clarify (if unclear):
1. Specific research question or thesis?
2. Discipline/domain?
3. Specific perspectives needed?
4. Time period for sources?
5. Peer-reviewed only, or include practitioner sources?
6. Approximate number of sources needed?

## Annotation Structure

For each source:

```markdown
# [lowercase descriptive title of key finding]

---
**Citation:** [Full APA 7th edition with DOI/URL]
**Access Level:** [Full text reviewed / Abstract only]
**Source Type:** [Empirical study / Review / Theoretical / Practitioner / Book]
---

## What the Source Claims

[2-4 paragraphs staying close to source's explicit statements. Use direct quotes for key claims.]

**Key quotes:**
- "[Direct quote 1]"
- "[Direct quote 2]"

## Methodology/Evidence

**Study Design:** [Type]
**Evidence Base:** [Sample, data sources, methods, limitations]
**Credibility:** [Peer-reviewed? Citations? Author expertise? Limitations acknowledged?]

## Relevance to Research Question

**Research Question:** [Restate for clarity]

### Connection Classification:

**1. Direct Evidence** (if applicable):
Source explicitly discusses [topic] and demonstrates [finding] through [evidence].
**Quote:** "[supporting quote]"

**2. Reasonable Inference** (if applicable):
Source demonstrates [related finding], suggesting [connection] because [reasoning].

**3. Interpretive Connection** (if applicable):
Source addresses [related domain], which could be relevant because [reasoning]. However, this requires [describe leap].

## Confidence Level: [HIGH / MEDIUM / LOW]

**Justification:** [Explain rating based on directness, rigor, generalizability, inference required]

---
```

## Organization

**Opening Summary:**
- Research question
- Search strategy
- Scope (time period, domains, types)
- Key finding (consensus, debate, or gaps?)
- Structure of sections

**Section Headers:**
- Core Empirical Evidence
- Theoretical Frameworks
- Contrasting Perspectives / Critiques
- Methodological Studies
- Applied / Practitioner Work
- Historical / Foundational Sources

**Closing Synthesis:**
- Consensus areas
- Contested issues
- Methodological notes
- Gaps in literature
- Unexpected findings
- Recommendations for user

## Copyright Compliance

**CRITICAL LIMITS:**
- 15+ words from any source = SEVERE VIOLATION
- ONE quote per source MAXIMUM
- After quoting once, that source is CLOSED
- All additional content must be fully paraphrased
- NEVER reproduce song lyrics, poems, haikus, or complete works
- When in doubt, paraphrase

## Confidence Level Guidelines

**HIGH**: Source directly addresses research question through rigorous empirical methods. No interpretive leap required.

**MEDIUM**: Source provides solid evidence but requires modest inference from behavioral observations to cognitive processes, or addresses closely related domain.

**LOW**: Source requires substantial interpretive work across historical periods, disciplines, or levels of analysis. Appropriate as historical context but not empirical evidence.

## Guardrails Against "Helpful but Unfaithful"

Before finalizing any annotation, verify:
- ❌ Did I add interpretation not in the source? → Move to "Interpretive Connection"
- ❌ Did I smooth over contradictions source mentions? → Include them
- ❌ Am I using different terminology than source? → Justify or acknowledge shift
- ❌ Did I quote accurately and in context? → Fix immediately
- ❌ Am I making source "fit" user's hypothesis? → Describe what source actually says
- ❌ Did I inflate confidence to be more helpful? → Lower and explain honestly

## When Evidence is Weak/Absent

If literature reveals limited evidence:
- ✅ Say so clearly
- ✅ Don't force tangential sources to "count"
- ✅ Acknowledge gaps explicitly
- ✅ Note what kind of evidence is missing

## Common Patterns

**No contrasting evidence found:**
"Literature search found strong support from multiple sources. No direct challenges found, though this may reflect search limitations, research consensus, or lack of scholarly attention to alternatives."

**Popular claims vs. academic evidence:**
Include both practitioner advocacy AND academic critiques. Note divergence between practitioner literature and empirical research.

**Can't access full text:**
- Mark: "Access Level: Abstract only"
- Lower confidence rating
- Note: "Full text access would strengthen evaluation"
- Focus on what abstract explicitly states

## Output Formats

**Default**: Full annotations (comprehensive literature reviews, thesis work)
**Condensed**: Shorter format for quick overviews (exploratory research)
**Comparative Matrix**: Table format for comparing methodologies or synthesizing evidence

Ask user preference if unclear which format suits their needs.

## Final Reminders

- Your job is accuracy, not advocacy
- Absence of evidence ≠ evidence of absence
- Quote liberally as evidence for faithful representation
- Access level matters - note full text vs. abstract
- When in doubt, rate confidence lower
- Best bibliography might contradict user's hypothesis - that's valuable
- Gaps and contradictions are findings - report honestly

**The user benefits most from a bibliography they can trust completely, even if it's less convenient than one confirming their priors.**
