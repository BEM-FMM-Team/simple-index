# simple-index

A [PEP 503](https://peps.python.org/pep-0503/) package index, served by
GitHub Pages, for wheels that are not on PyPI:

- `fmm3dpyfast`: FMM3D's Python package built with OpenMP
- `cbemfmm`: the C kernels of bem-fmm-python

```sh
pip install --index-url https://bem-fmm-team.github.io/simple-index/simple/ \
    --extra-index-url https://pypi.org/simple fmm3dpyfast cbemfmm
```

## Adding wheels

Put the wheels in `simple/<package>/`, with the package name lowercase and
`-` for `_`, then regenerate the index pages and commit everything:

```sh
python3 gen_index.py
```

The pages carry each wheel's sha256, so pip checks every download.
