# {tool-name} PR Annotator

## Usage

Annotate pull requests with {tool-name} errors detected during CI.

Note: This doesn't install or run {tool-name}, it just sets up the PR annotations.

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
        
      - name: Install {tool-name}
        run: |
          pip install {tool-name}

      - name: Add {tool-name} annotator
        uses: jpy-git/{tool-name}-pr-annotator@master

      - name: Run {tool-name}
        run: |
          {tool-name} src/
```
