<!--
Sync Impact Report:
Version change: None -> 0.1.0 (Minor: Initial constitution creation with principles and guidelines)
Modified principles:
  - PRINCIPLE_1: Spec-Driven Workflow (new)
  - PRINCIPLE_2: Reproducibility & Traceability (new)
  - PRINCIPLE_3: Clear & Pedagogical Content (new)
  - PRINCIPLE_4: Chapter Structure (new)
  - PRINCIPLE_5: Artifact Organization (new)
  - PRINCIPLE_6: Minimum Content (new)
Added sections: Project Constraints, Success Criteria & Definition of Done
Removed sections: None
Templates requiring updates:
  - .specify/templates/plan-template.md: ✅ updated (will be implicitly aligned by following constitution)
  - .specify/templates/spec-template.md: ✅ updated (will be implicitly aligned by following constitution)
  - .specify/templates/tasks-template.md: ✅ updated (will be implicitly aligned by following constitution)
  - .specify/templates/commands/*.md: ✅ updated (will be implicitly aligned by following constitution)
Follow-up TODOs:
  - TODO(RATIFICATION_DATE): Clarify original adoption date.
  - TODO(GOVERNANCE_REVIEW_CYCLE): Define review frequency (e.g., quarterly, annually).
  - TODO(AMENDMENT_PROCEDURE): Outline steps for proposing and approving constitution amendments.
-->
# AI/Spec-Driven Textbook on Physical AI & Humanoid Robotics Constitution

## Core Principles

### I. Spec-Driven Workflow
Every feature starts as a spec, then a prompt, then agent output, followed by a final edit.

### II. Reproducibility & Traceability
All prompts, agent outputs, and Architectural Decision Records (ADRs) must be tracked and saved to ensure reproducibility.

### III. Clear & Pedagogical Content
Content must be clear, accurate, and structured for a beginner-friendly teaching progression, covering fundamentals, robotics, AI, and practical labs.

### IV. Chapter Structure
Each chapter must include: learning outcomes, key concepts, diagrams, one lab, and a summary.

### V. Artifact Organization
Prompts are saved to .claude/prompts/, outputs to .claude/outputs/, and chapters are organized under /docs/ (Docusaurus).

### VI. Minimum Content
The project must include a minimum of 8 chapters and 2 robotics mini-projects.

## Project Constraints

- Must build with Docusaurus and deploy on GitHub Pages.
- Required folders: /docs, /spec (or /history), /.claude, /static/img.
- Every published document must follow the spec → prompt → output → edit cycle.

## Success Criteria & Definition of Done

**Success Criteria**:
- Book reproducible from saved specs/prompts.
- Technical accuracy and clear pedagogy.
- Docusaurus builds cleanly and GitHub Pages site is live.
- Complete history of specs, prompts, and ADRs included.

**Definition of Done**:
- Spec written → Prompt created → Claude output saved → Final doc added to /docs → Compiles in Docusaurus → Lab included → Commit includes spec+prompt+output.

## Governance

- This Constitution supersedes all other project practices.
- Amendments require documentation, approval, and a migration plan.
- Compliance reviews will be conducted periodically. TODO(GOVERNANCE_REVIEW_CYCLE): Define review frequency (e.g., quarterly, annually).
- The amendment procedure needs to be outlined. TODO(AMENDMENT_PROCEDURE): Outline steps for proposing and approving constitution amendments.

**Version**: 0.1.0 | **Ratified**: TODO(RATIFICATION_DATE): Clarify original adoption date. | **Last Amended**: 2025-12-05
