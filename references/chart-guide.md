# Chart Command Guide

## Preferred diagram types

| Goal | Diagram type | Starter |
|------|--------------|---------|
| Requirement tree | mindmap | `mindmap` + `root((Feature))` |
| Process / SCADET | flowchart | `flowchart TD` |
| API / interaction | sequenceDiagram | `sequenceDiagram` |
| Trade-offs | quadrantChart | `quadrantChart` |
| UI states | stateDiagram-v2 | `stateDiagram-v2` |

## Styling

### Built-in theme
```mermaid
---
config:
  theme: neutral
---
flowchart LR
    A --> B
```

### Category colors with classDef
```mermaid
flowchart LR
    A[FR] --> B[FNR] --> C[Out of Scope]
    classDef fr fill:#dbeafe,stroke:#1d4ed8,color:#1e3a8a
    classDef fnr fill:#dcfce7,stroke:#166534,color:#14532d
    classDef oos fill:#fee2e2,stroke:#b91c1c,color:#7f1d1d
    class A fr
    class B fnr
    class C oos
```

### Custom theme (base only)
```mermaid
---
config:
  theme: base
  themeVariables:
    primaryColor: "#e0f2fe"
    primaryTextColor: "#0c4a6e"
    primaryBorderColor: "#0284c7"
    lineColor: "#64748b"
---
flowchart TD
    A --> B
```

Keep diagrams small and focused. One clear idea per chart.
