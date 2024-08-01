# Workflows

This repository contains **reusable** GitHub Action workflows. 

## Core concepts:

- Workflows meant to configure **what** and **how** to run workflows, not **when**. Repositories that inherit from these configurations are responsible for configuring **when**. This is mainly because different repositories/services may have different needs and want to have flexibility of triggering them on different branches or events.
- Workflows define multiple variables in order to be highly configurable by child workflows.
- Workflows that are stored in one place are easy to update or patch.

## Example 

Workflow which uses `go.yml` CI configuration:

```yml
name: "Workflow for Feature branches"

on:
  push:

jobs:
  go:
    uses: svlabsinfra/workflows/.github/workflows/go.yml@main
    with:
      go-version: 1.22
```