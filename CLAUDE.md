# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a template repository for creating AMMOS SeqDev sequence editor adaptations. It provides the scaffolding needed to build custom sequence adaptations that integrate with the Aerie sequencing system.

The adaptation converts between SeqN (a human-readable sequence language) and SeqJSON (the JSON-based interchange format).

## Build Commands

```bash
npm run build    # Clean dist/, compile TypeScript, then bundle with Rollup
npm run test     # Run tests with Vitest
```

## Architecture

- **src/adaptation.ts** - Main adaptation entry point that exports the `adaptation` object
  - Defines input language (SeqN) and output language (SeqJSON)
  - Implements `toInputFormat` and `toOutputFormat` conversion functions
- **rollup.config.js** - Bundles the compiled JS as a CJS module
  - Externalizes @codemirror dependencies (injected by the host editor)
  - Outputs to `dist/` directory

## Key Dependencies

- `@nasa-jpl/aerie-sequence-languages` - Core language definitions and parsers
- `@nasa-jpl/seq-json-schema` - TypeScript types for SeqJSON format

## Node Version

Node.js v22.13.1 (see .nvmrc)
