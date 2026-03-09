# TGG Claude Code Plugins

Plugin marketplace for the Translational Genomics Group, providing genomics analysis capabilities for Claude Code.

## Installation

Add the marketplace to Claude Code:

```shell
/plugin marketplace add /path/to/tgg-llm-plugins
```

Or via GitHub (once pushed):

```shell
/plugin marketplace add your-org/tgg-llm-plugins
```

## Available Plugins

### variant-interpreter

Comprehensive variant pathogenicity interpretation using gnomAD population data, gene constraint metrics, and ACMG/AMP guidelines.

**Install:**
```shell
/plugin install variant-interpreter@tgg-plugins
```

**Usage:**
```shell
/variant-interpret
```

**Requires:** The `gmd-agent` MCP server (automatically configured by the plugin).

**Features:**
- Population frequency analysis with ACMG/AMP thresholds (BA1, BS1)
- Disease-specific maximum credible allele frequency calculation (Whiffin et al.)
- Gene constraint evaluation (pLI, o/e ratios)
- In silico prediction synthesis (REVEL, CADD, SpliceAI, etc.)
- Transcript expression (pext) analysis
- Compound heterozygosity phase inference
- Mendelian disease associations
- GWAS/QTL evidence integration

## Development

### Directory Structure

```
tgg-llm-plugins/
├── .claude-plugin/
│   └── marketplace.json          # Marketplace catalog
└── plugins/
    └── variant-interpreter/
        ├── .claude-plugin/
        │   └── plugin.json       # Plugin manifest
        └── skills/
            └── variant-interpret/
                └── SKILL.md      # Skill definition
```

### Adding New Plugins

1. Create a new directory under `plugins/`
2. Add `.claude-plugin/plugin.json` with plugin metadata
3. Add skills, hooks, or other components as needed
4. Register the plugin in `.claude-plugin/marketplace.json`

## License

Internal use - Translational Genomics Group
