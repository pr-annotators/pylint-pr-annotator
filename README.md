# Pylint PR Annotator

## Usage

Annotate pull requests with pylint errors detected during CI.

Note: This doesn't install or run pylint, it just sets up the PR annotations.

### Example workflow

```yaml
name: My Workflow
on: [push, pull_request]
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@master

      - name: Set up Python 3.8
        uses: actions/setup-python@v2
        with:
          python-version: "3.8"
        
      - name: Install pylint
        run: |
          pip install pylint

      - name: Add pylint annotator
        uses: jpy-git/pylint-pr-annotator@master

      - name: Run pylint
        run: |
          pylint src/
```
