# Own the Browser

An open, structured dataset of browser profiles for enterprise security and IT teams.

## Purpose

This repository provides machine-readable browser profiles that help organizations:

- **Evaluate browsers** for enterprise deployment readiness
- **Compare capabilities** across mainstream, privacy, and enterprise browsers
- **Make informed decisions** based on objective, sourced assessments

## Structure

```
ownthebrowser/
├── browsers/              # Browser profile directories
│   ├── chrome/
│   │   ├── browser.json   # Core structured data
│   │   ├── description.md # Profile overview
│   │   ├── deployment.md  # Deployment guidance
│   │   └── risk-analysis.md # Risk assessment
│   ├── edge/
│   ├── firefox/
│   └── ...
├── data/                  # Reference data
│   ├── dimensions.json    # Assessment dimensions
│   ├── tags.json          # Browser category tags
│   └── capabilities.json  # Enterprise capabilities
└── schemas/               # JSON Schema definitions
    └── browser.json       # Browser profile schema
```

## Browser Directory Structure

Each browser has its own directory containing:

| File | Purpose | Required |
|------|---------|----------|
| `browser.json` | Core structured data (identity, assessment, sources) | Yes |
| `description.md` | Browser overview, history, market position | No |
| `deployment.md` | IT deployment guidance, may include tables | No |
| `risk-analysis.md` | Security risks and considerations | No |

## Browser Profile Schema

The `browser.json` file includes:

- **Identity**: id, name, vendor, engine, platforms
- **Profile**: summary, archetype, differentiator, popularity
- **Deployment**: posture, rating, best-fit and caution scenarios
- **Assessment**: 9 dimensions scored 1-5 with rationale
- **Sources**: citations for claims

### Deployment Postures

| Posture | Description |
|---------|-------------|
| `enterprise-native` | Purpose-built for enterprise with native management |
| `enterprise-tolerable` | Acceptable for enterprise with configuration effort |
| `consumer-first` | Consumer-focused, limited enterprise readiness |
| `specialized` | Niche use case (privacy, research, etc.) |

### Assessment Dimensions

| Dimension | Question |
|-----------|----------|
| Security | How well does the browser reduce attack surface by default? |
| Reliability | Does it behave predictably across updates? |
| Performance | How efficiently does it use system resources? |
| Usability | How intuitive is the experience? |
| Compatibility | How well does it work with modern web apps? |
| Maintainability | How easy is it for IT to manage at scale? |
| Portability | How consistently does it work across platforms? |
| Functional Suitability | Does it meet core business browsing needs? |
| Enterprise Readiness | Is it designed for governance and compliance? |

## Contributing

Contributions welcome. Please ensure:

1. Profiles follow the schema in `schemas/browser.json`
2. Claims include sources where possible
3. Assessments are objective and defensible

## License

MIT License - see [LICENSE](LICENSE) for details.
