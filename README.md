# Workflow Plone Test Matrix

use with plone/meta

add the snippet to `.meta.toml`
```toml
[github]
extra_lines = """
  plonetests:
    uses: 1letter/workflow-plonematrix/.github/workflows/plonetest-matrix.yml@main
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
