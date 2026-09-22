# Product

<!-- impeccable:product-schema 1 -->

## Platform

web

## Stack

Static HTML/CSS/JS, deployed as a GitHub Pages site (GitHub repo, no build framework, no server).

## Users

Primary: the user's dissertation defense committee — reviewers who need to quickly understand what PhyloCrates does and where it deliberately stops, during a live defense demo.

Secondary (after the defense): phylogenetic comparative biologists who could use PhyloCrates themselves — evaluating whether its Socratic hypothesis-refinement protocol fits their workflow before a comparative study.

## Product Purpose

PhyloCrates is a standalone Socratic hypothesis-refinement agent for phylogenetic comparative biology. It takes a researcher from an initial biological observation or uncertainty to a structured, critically examined hypothesis set, through an eight-stage protocol: Observation/Problem → Question → Assumptions → Alternatives → Predictions → Discriminating expectations → Scope of claim → Refined hypothesis set. It ends in a structured Hypothesis Reasoning Record.

Success for this website: a defense committee member (or a researcher) can, in a few minutes, state accurately what PhyloCrates does, what the eight stages are, and what it refuses to do.

## Positioning

Existing tools and general-purpose assistants move straight to method selection ("use PGLS," "run BiSSE") or study design. PhyloCrates enforces a hard, explicit scope boundary instead: it refines the biological hypothesis and stops before any phylogenetic comparative method, sample size, measurement protocol, or analysis pipeline is chosen — and it holds that boundary under pushback, urgency, or reframing. No neighboring hypothesis tool documents and defends a scope boundary this explicitly, or produces a structured, auditable Hypothesis Reasoning Record as its terminal artifact.

## Operating Context

A researcher runs PhyloCrates as a conversational skill/agent before designing a comparative study — currently shipped as a Claude Code plugin, a ChatGPT Custom GPT, and a Gemini Gem / Gemini CLI extension, all wrapping the same core protocol and scope rules. The interaction is Socratic: one focused question at a time, following elicit → challenge → supplement → synthesize, ending in a Hypothesis Reasoning Record.

## Capabilities and Constraints

- Eight canonical stages (see Product Purpose); each stage has a defined output.
- Governing scope boundary: MAY clarify the problem, question, assumptions, alternatives, predictions, discriminating expectations, and scope of claim, and produce the Hypothesis Reasoning Record. MUST NOT recommend a named phylogenetic comparative method (PIC, PGLS, PGLMM, BM, OU, Mk, ASR, BiSSE, HiSSE, BAMM, etc.), select a PCM family, specify sample size/taxon sampling/power/data-collection protocol, decide operational measurement, specify tree/branch-length requirements/priors/diagnostics/sensitivity analyses, or build an analysis pipeline.
- The boundary holds under pushback, urgency, seniority claims, or rephrasing — stated in one clause, then reasoning continues within scope.
- Available identically (same protocol and scope rules) across Claude Code, ChatGPT, and Gemini.
- This website documents PhyloCrates only. It does not describe or reference "phyloSophos" (a separate, unrelated demo) as content — only its visual register was requested as a design reference, not its subject matter.

## Evidence on Hand

Real, accurate source material exists in the sibling `phylocrates-plugin/skills/phylocrates/` package: `SKILL.md`, `PHYLOCRATES_SPEC.md`, `instructions.md`, the `knowledge/` reasoning modules, `output/HYPOTHESIS_RECORD_SCHEMA.md`, and a worked `output/example-record.yaml`. Site copy must be sourced from these files, not invented.

A real, complete 15-turn transcript now exists: `phylocrates-plugin/tests/reports/functional-F1-cross-taxon.md` — an actual run of the shipped skill (not a mockup or scripted demo) against the seed observation "I've noticed that species living in more complex social groups seem to have bigger brains. I think social complexity drives brain size evolution," produced during this project's functional test pass and independently graded PASS against the completion criteria. This is now the site's primary worked example.

No screenshots or third-party testimonials exist. Do not fabricate any.

## Product Principles

1. Show the boundary, don't just assert it — the scope limit (what PhyloCrates refuses to do) is the core differentiator and must be as visible as the protocol itself.
2. The eight stages read as a literal pipeline position indicator, not decorative steps — this is a defense-demo audience that will map the diagram to the real protocol.
3. Describe only what the shipped skill actually does. A committee member may open the real package alongside the site; nothing here may overstate it.
4. One consistent protocol across platforms — do not imply Claude/ChatGPT/Gemini versions behave differently.

## Accessibility & Inclusion

WCAG AA contrast minimum (explicit user requirement, carried into DESIGN.md token choices).
