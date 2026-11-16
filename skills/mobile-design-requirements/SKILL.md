---
name: mobile-design-requirements
description: "Helps define clear Functional Requirements (FR), Non-Functional Requirements (FNR), and Out of Scope for mobile app features using a lightweight or full SCADET approach, tailored to design systems and Flutter/native constraints. Use when planning features, building or extending a design system, clarifying scope, or preparing component contracts."
type: workflow
lifecycle: active
---

# Mobile Design Requirements

Helps produce structured, mobile-aware requirements and architectural thinking (FR, FNR, Out of Scope + lightweight SCADET) that directly inform design system decisions. Use this when starting a new feature, refining product scope before UI work, or ensuring design tokens and components respect real platform constraints.

## When to Use

Trigger on requests involving:
- Defining or refining requirements for a mobile feature or screen
- Preparing inputs for a design system (components, tokens, patterns)
- Clarifying what is in/out of scope for a phase
- Reviewing vague feature descriptions for completeness
- Mapping product needs to Flutter, iOS, or Android constraints
- Applying SCADET (lightweight or full) to a feature

Do **not** use for pure visual design critiques, pure code implementation, or non-mobile web requirements.

## Core Workflow

Choose the depth based on the request:

### Lightweight SCADET (default for daily work — 5–10 min)
Use for most features. Output a concise version of all five steps.

1. **S – System requirements**
   - 3–5 clear, testable FR with short acceptance criteria
   - 2–3 measurable FNR that actually matter (performance, accessibility, platform, offline, etc.)
   - Explicit Out of Scope

2. **C – Design considerations**
   - 1–2 key decisions (reuse existing component vs new, server-driven vs local, platform gating, etc.)

3. **AD – Architecture & API**
   - Quick data-flow sketch and which existing pieces will be reused

4. **E – Evaluation**
   - 1–2 concrete ways you will know it is done

5. **T – Trade-offs**
   - The main trade-off being accepted

### Full SCADET (for larger or riskier work)
Expand each step with more detail, tables, and design-system mapping. Follow the original detailed workflow below when the user asks for depth or the feature is complex.

### Detailed Requirements Workflow (used inside S or when SCADET is not requested)

1. **Gather Context**
   - Feature or user story description
   - Target platforms (Flutter primary, iOS, Android, or hybrid)
   - Audience and constraints (localization, offline, performance budget, team size, etc.)
   - Existing design system elements if any

2. **Extract Functional Requirements (FR)**
   - Write clear, testable statements of what the system must do
   - Include primary flows, edge cases, and error states
   - Prefer user-story or “The system shall…” format with acceptance criteria
   - Note platform-specific behavior only when it differs

3. **Define Non-Functional Requirements (FNR)**
   - Cover performance, reliability, usability, accessibility, security, localization, and maintainability
   - Make them measurable where possible (e.g., “Scroll list of 200 items at 60 fps on mid-range Android”)
   - Prioritize those that affect design system decisions (animation budgets, touch targets, RTL, color contrast, offline states)
   - See `references/mobile-fnr-checklist.md` for mobile-specific items

4. **Set Explicit Out of Scope**
   - List features, platforms, or qualities deliberately excluded from this phase
   - Include future considerations that must not influence current component design
   - Prevents scope creep into tokens and components

5. **Map to Design System Implications**
   - Identify required components, variants, tokens, or platform channels
   - Note constraints that affect animation, layout, or native bridges
   - Flag any gaps in the current design system

6. **Output Structured Document**
   - Produce a clean Markdown summary
   - Prefer the lightweight SCADET format by default
   - Use the full template in `assets/requirements-template.md` when more detail is requested
   - Always include a short “Design System Impact” or equivalent inside the relevant SCADET step
   - Highlight open questions or risks

## Output Guidelines

- Default to the lightweight SCADET format unless the user asks for full detail
- Keep language precise and free of implementation details unless they are constraints
- Use tables for FNR, considerations, evaluation, and trade-offs when they improve scanability
- Always include at least one measurable performance or accessibility FNR for mobile
- Call out Flutter-specific realities (widget rebuilds, Impeller/Skia, Platform Channels cost) when relevant
- Prefer short, scannable sections over long prose

## Commands

Slash commands live in the plugin's `commands/` folder (e.g. `/msd:scadet-full`): `scadet`, `scadet-full`, `requirements`, `ds-impact`, `nfr`, `review`, `chart`. Also honor close natural-language equivalents. Plain `scadet` is the default lightweight mode.

### `chart` command details

When the user asks for a chart (or uses the `chart` command), generate one or more Mermaid diagrams. Prefer:

- Requirement coverage (mindmap or flowchart)
- SCADET flow
- Design system impact
- Trade-off quadrant or flowchart
- Priority / risk view

**Styling rules for charts**
- Default: clean built-in theme (`default` or `neutral`)
- When color-coding categories (FR / FNR / Out of Scope / risk): use `classDef`
- When the user asks for a branded or high-contrast chart: use frontmatter with `theme: base` + `themeVariables`
- Always produce valid Mermaid that works in GitHub, Notion, Obsidian, and mermaid.live

Example classDef set:
```
classDef fr fill:#dbeafe,stroke:#1d4ed8,color:#1e3a8a
classDef fnr fill:#dcfce7,stroke:#166534,color:#14532d
classDef oos fill:#fee2e2,stroke:#b91c1c,color:#7f1d1d
```

## References

- `references/mobile-fnr-checklist.md` — Mobile and Flutter non-functional checklist
- `references/design-system-mapping.md` — How requirements translate into tokens and components
- `references/examples.md` — Good vs weak requirement examples
- `references/scadet-lightweight.md` — Lightweight daily SCADET checklist
- `references/chart-guide.md` — Mermaid chart types and styling




## Common Issues

| Issue | Fix |
|-------|-----|
| Vague FR (“user can manage data”) | Ask for concrete actions, success criteria, and edge cases |
| Missing performance FNR | Add at least one frame-rate or load-time target |
| Out of Scope empty | Explicitly state deferred features and platforms |
| No design system link | Add a short impact note even if “no new components needed” |
| Over-engineering small tickets | Switch to lightweight SCADET and keep each step to a few bullets |
