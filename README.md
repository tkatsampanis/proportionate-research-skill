# Proportionate Research Skill — Overview

**Hermes Agent Skill | Version 3.0.0**

## Description

Proportionate Research — Obtain sufficient reliable evidence to answer the user's actual question correctly, using the minimum necessary work.

**Core operating loop:** UNDERSTAND → CLASSIFY → PLAN → RETRIEVE → EVALUATE → UPDATE → VERIFY → STOP

**Goal:** Not to retrieve as much information as possible, but to obtain sufficient reliable evidence using the minimum necessary work. Research optimizes for accuracy, relevance, evidence quality, and efficiency.

## Key Features

### 26-Section Methodology
Full detailed skill covering:
- Research invariants and invariants throughout the process
- Understanding the request and classifying required information
- Decomposing questions into required claims with coverage tracking
- Determining research depth (lightweight/analytical/comprehensive)
- Allocating proportionate research budgets
- Source and evidence quality evaluation (primary, secondary, discovery sources)
- Evidence states (established/corroborated/supported but uncertain/etc.)
- Escalation gradation (Level 0–4 methods)
- Web research with search saturation awareness
- Contradiction handling and negative claims management
- Temporal and version awareness
- Planning and persistent research state management
- Cost management before expensive operations
- Computational work principles
- Comprehensive vs. exhaustive research distinctions
- Avoiding research loops
- Asking the user when necessary
- Decision sensitivity prioritization
- Verification matching claim importance
- Stopping rules with novelty evaluation
- Accuracy beats minimality principle
- File and system safety
- Output discipline

### Quick-Start Support Materials
- **Cheat sheet** (cheat-sheet.txt): One-page reference of operating loop, key questions, stopping conditions, research depth tiers, primary stopping signals, 12 common pitfalls, evidence states
- **Research scenarios** (scenarios-and-condensed.txt): Three detailed worked examples (simple factual, analytical, comprehensive) showing framework application step-by-step, plus a 15-section condensed mode version

### Recent Enhancements (v3.0.0)
- Coverage category in question classification (tracks investigated vs. uncovered evidence dimensions)
- Search Saturation section (70–80% overlap heuristic as signal, not rule; primary stopping signal: "Are additional searches producing materially new evidence relevant to unresolved required claims?")
- Novelty evaluation in stopping rule (assess whether further research likely produces new required claims, new evidence, contradictory evidence, better source quality, or unexplored coverage)
- All prior v2.0.0 enhancements from technical-verification skill integration

## Usage

```yaml
# Load the skill in Hermes:
skill_view(name='proportionate-research')
```

Or via the Hermes desktop app skills library.

**For simple queries:** Refer to the cheat sheet for quick guidance on the operating loop and stopping rules.

**For complex multi-step research:** Use the full 26-section skill with persistent research state management (Planning with Files system).

**For rapid prototyping or training:** Use the 15-section condensed mode covering all core principles.

## Output Discipline

The user normally wants the answer, not a diary of internal operations. Provide:
- The answer
- Important evidence
- Relevant assumptions
- Meaningful uncertainty
- Citations when appropriate

Never imply research, retrieval, verification, computation, or source consultation that did not actually occur.

## Version History

| Version | Date | Changes |
|---------|------|---------|
| 1.0.0 | — | Initial release |
| 2.0.0 | Sept 27 | Enhanced with technical-verification additions: research questions, final check expansion, core flow with PLAN step |
| 3.0.0 | Sept 27 | Complete rewrite with all adjustments from pasted content: operating loop reflow (UNDERSTAND→CLASSIFY→PLAN→RETRIEVE→EVALUATE→UPDATE→VERIFY→STOP), new sections 1–5, 6–8, 10–26, coverage category, search saturation, novelty evaluation |

## Citation

If using this skill in published work or shared resources, please cite:

> Hermes Agent (2026). Proportionate Research Skill (v3.0.0). Nous Research. https://hermes-agent.nousresearch.com/docs

---

*This skill is designed to prevent unnecessary research work while maintaining appropriate reliability. The goal is always: obtain sufficient reliable evidence using the minimum necessary work.*