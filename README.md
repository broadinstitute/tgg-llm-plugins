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

Interpret variant pathogenicity from gnomAD CSV exports using ACMG/AMP guidelines.

**Install:**
```shell
/plugin install variant-interpreter@tgg-plugins
```

**Usage:**
```shell
/variant-interpret
```

Then provide the path to your gnomAD CSV file when prompted.

**Data Preparation:**

1. Go to [gnomAD browser](https://gnomad.broadinstitute.org/)
2. Search for your gene of interest
3. Click "Export variants to CSV"
4. Download to your working directory

**Features:**
- Parse gnomAD CSV exports directly (no API required)
- Population frequency analysis with ACMG/AMP thresholds (BA1, BS1)
- Disease-specific maximum credible allele frequency calculation (Whiffin et al.)
- In silico prediction synthesis with gnomAD-calibrated thresholds:
  - REVEL (0.644/0.773)
  - CADD (25.3/28.1)
  - SpliceAI (0.2/0.5)
  - Pangolin (0.2/0.5)
  - phyloP (7.367/9.741)
- ClinVar classification review
- Quality flag assessment
- Population-specific frequency analysis

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
