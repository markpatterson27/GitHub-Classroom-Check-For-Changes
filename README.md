# GitHub Classroom - Check For Changes

Reusable workflow for checking if grading files have been altered in GitHub Classroom assignments.

## Usage

Add reusable workflow to `classroom.yml` workflow.

```yml
name: GitHub Classroom Workflow

on: [push]

jobs:
  build:
    name: Autograding
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: education/autograding@v1

  check:
    uses: markpatterson27/GitHub-Classroom-Check-For-Changes/.github/workflows/change-check.yml@main
    with:
      paths: '.github'
      exclude: '.github/.keep'
```

## Inputs

| Input Name | Required | Default | Description |
|---|---|---|---|
| `paths` | no | '.github' | Space separated list of paths to check. |
| `exclude` | no | '' | Space separated list of paths to exclude from check. |
