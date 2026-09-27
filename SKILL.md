---
name: proportionate-research
description: "Proportionate Research - Obtain sufficient reliable evidence to answer the user's actual question correctly, using the minimum necessary research effort."
version: 3.0.0
author: Hermes Agent
platforms: [linux, macos, windows]
metadata:
  hermes:
    tags: [research, proportionate, investigation, document-analysis, media-retrieval, technical-investigation]
---
# Proportionate Research

## Purpose

Govern research, browsing, information retrieval, document analysis, media retrieval, and technical investigation.

The goal is **not** to retrieve as much information as possible.

The goal is:

> **Obtain sufficient reliable evidence to answer the user's actual question correctly, using the minimum necessary work.**

Research should optimize for **accuracy, relevance, evidence quality, and efficiency**.

Use this operating loop:

> **UNDERSTAND → CLASSIFY → PLAN → RETRIEVE → EVALUATE → UPDATE → VERIFY → STOP**

Do not confuse more searches, more sources, more tool calls, or more text with better research.

The central question is:

> **What required claim remains insufficiently established?**

Not:

> "What else can I search for?"

---

# 1. Research Invariants

These rules apply throughout the research process.

1. **Every significant retrieval must have an identifiable purpose.**
2. **Every retrieval should target an open required question or claim.**
3. **Use the cheapest reliable method capable of answering that question.**
4. **A source reporting a claim does not automatically establish the claim.**
5. **Source quality depends on authority, relevance, temporal fit, independence, and methodology.**
6. **Search results and snippets are primarily discovery mechanisms, not automatically evidence.**
7. **Multiple sources repeating the same underlying claim do not necessarily provide independent confirmation.**
8. **Failure to find evidence is not evidence of absence unless the search had sufficient coverage to support an absence claim.**
9. **Important contradictions must be resolved or explicitly reported.**
10. **Do not silently fill evidence gaps with assumptions.**
11. **Research depth must be proportional to the user's requested depth, uncertainty, consequence, and sensitivity of the answer to factual errors.**
12. **Stop when all required claims have sufficient evidence and no material unresolved contradiction remains.**
13. **Optional unanswered questions are not a reason to continue researching once the user's actual request is sufficiently answered.**

---

# 2. Understand the Request

Before significant tool use, determine:

1. What exactly is the user asking?
2. What answer or deliverable do they actually need?
3. What claims must be established to provide that answer?
4. What information is already available from:
   - the conversation
   - user-provided files
   - already retrieved sources
   - established knowledge, when freshness is not important
5. What information is missing?
6. Does the question require current information?
7. How consequential would an incorrect answer be?
8. Has the user requested a particular research depth?

 Do not research information merely because it is related to the topic.

 Research only what is necessary to satisfy the user's actual request, plus limited context that materially improves the answer.

---

# 3. Decompose the Question Into Required Claims

For non-trivial research, convert the user's question into a small set of claims or questions that must be established.

Use:

> **Question → Required claims → Evidence**

Example:

**Question:**\
 "Does API X support feature Y in version 4?"

**Required claims:**

 - Feature Y exists.
- API X supports feature Y.
- Version 4 supports it.
- Any relevant limitation or configuration requirement.

This prevents one broad source from being treated as evidence for several unsupported details.

Classify each item as:

### Required

Necessary to answer the user's question correctly.

Coverage

Which relevant evidence categories, search dimensions, populations, time periods, terminology, or source types have been investigated, and which remain uncovered.

Contextual

Useful background that improves understanding but is not necessary.

Optional

Interesting but unnecessary information.

Blocked

Required information that cannot currently be established without additional user input, access, or evidence.

Prioritize required claims.

Do not spend substantial research effort on contextual or optional claims while required claims remain unresolved.

---

# 4. Determine Research Depth

Match research effort to the task.

### Lightweight

Examples:

 - simple factual questions
- dates
- definitions
- authors
- straightforward current-version lookups
- finding a small number of sources

Use focused retrieval.

### Analytical

Examples:

 - comparisons
- explanations
- paper analysis
- technical investigations
- consistency checks
- methodology questions

Retrieve the evidence needed for the relevant claims and analyze it.

### Comprehensive

Examples:

 - literature reviews
- exhaustive investigations
- broad technical reviews
- "find all major approaches"
- systematic comparisons

Use broader retrieval and explicit coverage criteria.

Never silently turn a simple request into a comprehensive investigation.

---

# 5. Allocate a Proportionate Research Budget

Before expensive or extensive retrieval, consider:

 - **Complexity** — how many claims must be established?
- **Uncertainty** — how difficult is the information to establish?
- **Consequence** — how harmful would an incorrect answer be?
- **Freshness** — how quickly might the information change?
- **Requested depth** — how comprehensive did the user ask to be?

Use the smallest research budget that can produce sufficient confidence.

A simple low-consequence fact may require one authoritative source.

A consequential, disputed, rapidly changing, or technically sensitive claim may require multiple sources, primary evidence, or direct verification.

Do not spend extensive research effort merely because additional information is available.

---

# 6. Source and Evidence Quality

Prefer evidence appropriate to the claim.

## Primary or authoritative evidence

Prefer when applicable:

 - official documentation
- original research papers
- original datasets
- legislation and regulations
- court or government records
- official technical specifications
- first-party announcements
- direct statements
- source code or official repositories

## High-quality secondary evidence

Useful when primary evidence is unavailable or insufficient:

 - systematic reviews
- scholarly reviews
- reputable technical references
- established journalism
- expert analysis

## Discovery-oriented sources

Useful for locating evidence:

 - search results
- snippets
- forums
- Reddit
- blogs
- aggregators
- social media
- discussion threads

Discovery sources may sometimes be sufficient evidence for low-stakes claims, but do not automatically treat them as authoritative.

### Source quality is claim-dependent

A source that is authoritative for one question may not be authoritative for another.

For example, an official software issue tracker may be excellent evidence about a specific bug but not necessarily about broader industry practices.

Always evaluate whether the source is appropriate for the particular claim.

---

# 7. Evaluate Evidence Before Treating It as Established

For every important claim, consider:

### Authority

Is the source qualified or authoritative for this claim?

### Relevance

Does the source actually address the specific claim?

### Directness

Does it directly establish the claim, or merely imply it?

### Temporal fit

Does the evidence apply to the relevant date, period, version, or state?

### Independence

Is the evidence genuinely independent, or are multiple sources repeating the same underlying information?

**If multiple secondary sources derive their claims from the same primary source, press release, wire report, dataset, benchmark, study, or other underlying evidence, treat them as a single source of evidence rather than independent corroboration.**

### Methodology

Where applicable, is the method capable of supporting the conclusion?

### Completeness

Does the evidence establish the whole claim, or only part of it?

Do not upgrade a weak source into strong evidence merely by finding several copies of the same claim.

---

# 8. Evidence States

For important claims, distinguish between:

### Established

Strong evidence directly supports the claim.

### Corroborated

The claim is supported by multiple sufficiently independent credible sources.

### Supported but uncertain

Evidence supports the claim, but meaningful uncertainty remains.

### Indirectly supported

Evidence strongly suggests the claim but does not directly establish it.

### Contradicted

Credible evidence conflicts with the claim.

### Unverified

Insufficient evidence has been found.

Do not present uncertain, indirect, or unverified claims using language appropriate for established facts.

---

# 9. Escalate Gradually

Use the lightest reliable method first.

### Level 0 — Existing information

Use:

 - conversation context
- user-provided files
- already retrieved information
- established knowledge when freshness is not important

Do not repeat research unnecessarily.

### Level 1 — Focused search

Use:

 - targeted web searches
- metadata
- abstracts
- search indexes
- documentation search
- API metadata

Often sufficient for simple questions.

### Level 2 — Targeted source retrieval

Retrieve only the relevant:

 - webpage
- section
- table
- documentation page
- paper section
- transcript portion
- dataset subset

Prefer targeted extraction over full-document processing.

### Level 3 — Deep analysis

Use when the answer depends on:

 - methodology
- equations
- implementation details
- experimental conditions
- complete arguments
- detailed results
- information unavailable through lightweight retrieval

### Level 4 — Multi-source reconciliation

Use when:

 - credible sources conflict
- independent confirmation materially matters
- the user requests comprehensive coverage
- the task genuinely requires extensive processing

Do not automatically progress through every level.

Stop at the lowest level that provides sufficient reliable evidence.

---

# 10. Web Research

Start with a focused query targeting an unresolved claim.

Broaden only when:

 - results are insufficient
- the subject is difficult to locate
- credible sources conflict
- the current source does not establish the required claim
- broader coverage was explicitly requested

Each additional search should have an identifiable purpose:

 - find missing evidence
- resolve a contradiction
- improve freshness
- verify a consequential claim
- improve coverage required by the user

Do not search the same question repeatedly without a new purpose.

Do not follow links merely because they exist.

Do not treat search-engine ranking as evidence of source quality.

Search snippets are discovery aids unless the snippet itself constitutes the authoritative source being queried.

### Search Saturation

For broad or multi-round research, track whether successive search rounds produce materially new evidence.

Consider the search space approaching saturation when:

- new searches mostly return previously encountered sources or domains
- few or no new required claims are being discovered
- no important contradictory evidence is emerging
- relevant coverage areas have been adequately investigated

A source-overlap rate of approximately 70–80% across successive rounds may be used as a heuristic signal of saturation, but it is not an automatic stopping rule.

Do not stop solely because of high source overlap if:

- a required claim remains unresolved
- an important coverage area remains unexplored
- credible sources conflict
- source quality is inadequate
- a different terminology, database, population, period, or research community may contain materially different evidence

The primary stopping signal is:

> **Are additional searches still producing materially new evidence relevant to unresolved required claims?**

This is the adjustment I would make instead of adopting the proposed rigid "80% = stop."

---

---

# 11. Temporal and Version Awareness

For information that can change, determine:

 - when the claim was true
- when the source was published or updated
- which version or state it describes
- whether the user is asking about the current state or a historical state

This is especially important for:

 - software
- APIs
- laws and regulations
- prices
- product availability
- company information
- political information
- security issues
- scientific consensus

A credible source can still be unsuitable if it describes the wrong time period or version.

---

# 12. Contradictions

When credible sources disagree:

 1. identify the exact disagreement
2. check publication dates
3. check versions or relevant time periods
4. check definitions
5. check populations and conditions
6. check measurement methods
7. check whether the sources are actually independent
8. determine which evidence applies to the user's question
9. investigate further if the contradiction materially affects the answer

Do not silently combine incompatible information.

Do not average conflicting technical values merely to produce a single number.

If the contradiction cannot be resolved, report the disagreement and explain the relevant uncertainty.

---

# 13. Negative Claims and Absence

Be careful with statements such as:

 - "X does not exist."
- "No study has found X."
- "There are no examples of X."
- "This software cannot do X."

Failure to find evidence does not establish absence unless the research had sufficient coverage to support that conclusion.

For absence claims, consider whether:

 - the relevant sources were searched
- the search terms were sufficiently broad
- the source population was appropriate
- the requested scope was actually covered

Use appropriately qualified language when coverage is incomplete.

---

# 14. Documents, Video, and Audio

Use the cheapest representation capable of answering the question.

## Documents

Prefer:

 - relevant sections
- relevant pages
- tables
- searchable text
- targeted extraction

Do not automatically process entire documents.

## Video and audio

Check first for:

 - metadata
- descriptions
- captions
- transcripts
- timestamps
- reliable external references

Retrieve actual media only when the task requires it.

Actual media retrieval is justified for tasks such as:

 - visual analysis
- frame analysis
- object tracking
- scene analysis
- movement analysis
- audio-specific analysis

A request for a complete spoken-content summary may justify retrieving a full transcript.

Do not retrieve every language, caption track, or media representation unless necessary.

---

# 15. Planning and Persistent Research State

For genuinely multi-step research, maintain explicit research state.

Use persistent planning when the task is complex enough that information, contradictions, evidence, or next steps may otherwise be lost.

Do not create unnecessary planning overhead for simple tasks.

The research state should contain:

### Objective

 The user's actual goal.

### Required deliverable

 What must ultimately be provided.

### Required questions/claims

 What must be established.

### Known information

 What is already established from the conversation or prior work.

### Evidence

 Which sources support which claims.

### Open questions

 Required claims that remain unresolved.

### Contradictions

 Important conflicts between credible sources.

### Assumptions

 Information being temporarily assumed rather than established.

### Blocked questions

 Required questions that cannot currently be answered without additional information.

### Next action

 The retrieval or analysis step most likely to resolve an open required question.

### Stopping condition

 What must be true before research is complete.

After every meaningful research action:

 1. record what was established
2. update evidence states
3. mark answered questions
4. record meaningful contradictions
5. identify remaining open required questions
6. choose the next action based on those questions

Do not continue from habit or momentum.

---

# 16. Cost Before Expensive Operations

Before performing an expensive operation, ask:

> **Which unresolved required question will this answer, and why is a cheaper representation insufficient?**

Expensive operations include:

 - large downloads
- full videos
- full transcripts
- large PDFs
- many papers
- website crawling
- recursive link following
- large datasets
- long computations
- repeated searches

Prefer:

 - metadata instead of full files
- relevant PDF pages instead of entire PDFs
- relevant transcript sections instead of full transcripts
- dataset subsets instead of complete datasets
- targeted pages instead of website-wide crawling

Never perform broad or destructive operations without a clear information need.

---

# 17. Computational Work

Use computation when it is necessary for correctness.

Avoid:

 - unnecessary simulations
- repeated calculations
- brute-force searches when a smaller calculation is sufficient
- redundant processing

Reuse valid results when appropriate.

For potentially expensive computation:

 1. identify the exact question it answers
2. determine whether a smaller calculation is sufficient
3. record assumptions that materially affect the result
4. verify important outputs where appropriate

Do not perform computation merely because it is available.

---

# 18. Comprehensive and Exhaustive Research

When the user explicitly requests comprehensive or exhaustive research, do not prematurely stop.

First define the requested coverage.

For example:

 - major approaches
- relevant time period
- geographic scope
- competing theories
- important papers
- major implementations
- known limitations

Search systematically across those dimensions.

For broad searches, track covered categories and remaining gaps.

Stop when:

 - the requested scope has been covered
- major categories have been investigated
- additional searches mostly return duplicate evidence or low-relevance material
- no important required evidence gap remains

"Exhaustive" does not mean following every possible link indefinitely.

---

# 19. Avoid Research Loops

Do not repeatedly:

 - search the same query
- fetch the same page
- retrieve the same document
- inspect increasingly irrelevant results
- process additional material without a clear information need
- retry identical failed operations
- follow links without an unresolved question

If repeated research produces no materially new evidence:

 1. identify the remaining uncertainty
2. determine whether another retrieval method could resolve it
3. escalate only if justified
4. otherwise report the uncertainty and stop.

---

# 20. Ask the User When Necessary

Do not invent missing user-specific information merely to keep research moving.

Ask the user when a missing parameter:

 - materially changes the answer
- cannot reasonably be inferred
- cannot be resolved through available evidence

If the missing information does not materially affect the answer, make a clearly stated reasonable assumption instead of unnecessarily interrupting the user.

---

# 21. Decision Sensitivity

Prioritize verification for facts where an error could materially change:

 - the user's decision
- the user's action
- the final conclusion
- safety
- legality
- financial consequences
- technical correctness
- interpretation of important evidence

A minor contextual fact does not require the same verification budget as a fact on which the entire answer depends.

When multiple claims are required, spend the most research effort on the claims with the greatest **decision sensitivity**.

---

# 22. Verification

Verification effort should match:

 - claim importance
- uncertainty
- source quality
- source independence
- freshness
- contradiction
- user-requested depth
- consequence of being wrong

Possible verification methods include:

 - authoritative sources
- independent confirmation
- original documents
- primary research
- version/date checks
- calculation checks
- reproducing a result
- direct inspection of relevant material

Do not manufacture certainty by accumulating redundant sources.

Do not claim something was verified unless the verification actually occurred.

---

# 23. Stopping Rule

After every meaningful retrieval or analysis stage, ask:

> **Do I now have enough reliable evidence to answer the user's actual question without guessing?**

If YES:

> **STOP.**

If NO:

 1. identify the exact unresolved required claim
2. determine what evidence is missing
3. retrieve only what is necessary to address it
4. reassess

Research is complete when:

 - all required claims are sufficiently established
- important contradictions are resolved or explicitly reported
- requested scope has been satisfied
- assumptions are clearly identified
- no essential evidence gap remains

Do not continue researching merely because optional questions remain.

When additional research is being considered, evaluate whether it is likely to produce:

- new required claims
- new evidence for an unresolved claim
- meaningful contradictory evidence
- materially better source quality
- coverage of an important unexplored area

If additional retrieval is only likely to produce duplicate or derivative information, stop.

---

# 24. Accuracy Beats Minimality

Efficiency does not mean doing as little work as possible.

It means:

> **Do as little unnecessary work as possible while maintaining appropriate reliability.**

If lightweight research is insufficient, escalate.

If deep research is necessary, perform it.

If evidence remains uncertain, state the uncertainty.

Never guess to save tool usage.

Never claim verification that did not occur.

Never sacrifice correctness merely to satisfy a minimal research budget.

---

# 25. File and System Safety

When creating temporary research artifacts:

 - prefer temporary or task-specific locations
- avoid unnecessary large files
- remove temporary files created by the agent when finished

Never delete, overwrite, or modify user-created files merely because they were encountered.

Never perform broad destructive cleanup.

Before deleting anything, establish that:

 1. the agent created the file for the current task, and
2. it is no longer needed.

If uncertain, leave it alone.

---

# 26. Output Discipline

The user normally wants the answer, not a diary of internal operations.

Do not overwhelm the final response with:

 - every search query
- failed URLs
- internal commands
- discarded sources
- irrelevant intermediate results
- the entire research plan

Provide:

 - the answer
- the important evidence
- relevant assumptions
- meaningful uncertainty
- citations when appropriate

If the user asks for the research trail, provide it.

Never imply research, retrieval, verification, computation, or source consultation that did not actually occur.

Research state is working state, not a substitute for the final answer.

---

# Core Algorithm

For every research task:

### 1\. UNDERSTAND

Identify the actual user question and required deliverable.

### 2\. CLASSIFY

Determine required claims, freshness, consequence, uncertainty, and requested depth.

### 3\. PLAN

Identify what is already known, what is missing, and what evidence is needed.

### 4\. RETRIEVE

Use the cheapest reliable method capable of resolving an open required claim.

### 5\. EVALUATE

Assess evidence for authority, relevance, directness, temporal fit, independence, methodology, and completeness.

### 6\. UPDATE

Mark claims as established, corroborated, uncertain, indirect, contradicted, or unverified.

### 7\. VERIFY

Increase verification only when the claim's importance, uncertainty, contradiction, freshness, or requested depth warrants it.

### 8\. STOP

When all required claims have sufficient evidence and no material unresolved contradiction remains, answer the user.

> **Research the unanswered questions, not the topic.**
>
>  **Retrieve evidence, not information for its own sake.**
>
>  **Escalate only when the evidence requires it.**
>
>  **Stop when the answer is sufficiently established.**
>
>  **Accuracy beats minimality; unnecessary work is the thing to minimize.**