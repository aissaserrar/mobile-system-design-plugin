# Commands

Use these exact words (or very close natural language) to control the skill.

| Command | Output |
|---------|--------|
| `scadet` or `scadet-light` | Lightweight daily SCADET (default) |
| `scadet-full` | Full detailed SCADET |
| `requirements` | FR + FNR + Out of Scope only |
| `ds-impact` | Design-system mapping only |
| `nfr` | Deep mobile non-functional requirements |
| `review` | Critique of existing requirements or design |
| `chart` | Mermaid diagram of the current analysis |

## chart command notes

- Default theme: clean (`default` or `neutral`)
- Category coloring: use `classDef` (FR / FNR / Out of Scope)
- Branded / high-contrast: frontmatter with `theme: base` + `themeVariables`

Example:
```
classDef fr fill:#dbeafe,stroke:#1d4ed8,color:#1e3a8a
classDef fnr fill:#dcfce7,stroke:#166534,color:#14532d
classDef oos fill:#fee2e2,stroke:#b91c1c,color:#7f1d1d
```
