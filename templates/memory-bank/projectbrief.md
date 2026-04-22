# Project Brief

## Overview
[Project name]: [One-line description]

## Tech Stack
- [Language/framework]
- [Key libraries]
- [Build tools]

## Architecture
- [Component/layer 1]
- [Component/layer 2]
- [Data flow summary]

## Structure
[Folder tree with descriptions. Every folder gets a description that tells an agent
exactly what it contains and WHY it would go there. Be specific, not vague.]

[Example format:]
src/
  api/              — HTTP client, endpoint definitions, request/response handlers
  components/
    layout/         — App shell components: Sidebar nav, Breadcrumbs, PageHeader
    screens/        — Full-page views: UploadScreen, ResultsScreen, MarketTable
    shared/         — Reusable UI primitives: Button, Badge, LoadingBar
  data/             — Mock datasets, seed files, sample_results.xlsx for dev
  store/            — Zustand stores: app state, portfolio selections, run history
  types/            — TypeScript interfaces for Portfolio, Property, RunConfig, Market
  utils/            — Data aggregation, market clustering, formatting helpers

[Update this section when new top-level folders are created or major reorganization occurs.
Do NOT update for individual file additions within existing folders.]

## Constraints
- [Non-negotiable requirements]

## Conventions
- [Coding patterns established so far]
