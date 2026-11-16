# mobile-system-design-plugin

Claude Code plugin for mobile design requirements (FR / FNR / Out of Scope + SCADET).

## Install

```bash
claude plugin marketplace add aissaserrar/mobile-system-design-plugin
claude plugin install msd@mobile-system-design-plugin
```

Or from a local clone:

```bash
claude plugin marketplace add /path/to/mobile-system-design-plugin
claude plugin install msd@mobile-system-design-plugin
```

## Skill

`mobile-design-requirements` — use when planning mobile features, clarifying scope, or preparing design-system component contracts.

## Commands

| Command | Output |
|---------|--------|
| `/msd:scadet` | Lightweight daily SCADET |
| `/msd:scadet-full` | Full SCADET |
| `/msd:requirements` | FR + FNR + Out of Scope |
| `/msd:ds-impact` | Design-system mapping |
| `/msd:nfr` | Deep mobile NFRs |
| `/msd:review` | Critique existing requirements |
| `/msd:chart` | Mermaid diagram |
