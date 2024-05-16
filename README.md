# Workflow Plone Test Matrix

use with plone/meta

## use plonetests

add the snippet to `.meta.toml`

```toml
[github]
extra_lines = """
  plonetests:
    uses: collective/workflow-plonematrix/.github/workflows/plonetest-matrix.yml@main
"""

[tox]
use_mxdev = true
config_lines = """
[gh-actions]
python =
    3.8: py38
    3.9: py39
    3.10: py310
    3.11: py311
    3.12: py312
"""
```

## use codecov

generate a token on codecov.io for your package

add the token to settings -> secrets -> actions

add the snippet to `.meta.toml`

```toml
[github]
extra_lines = """
  codecov:
    uses: collective/workflow-plonematrix/.github/workflows/codecov.yml@main
    secrets:
       codecov-token: ${{ secrets.CODECOV_TOKEN }}
"""
```
