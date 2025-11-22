# Textract-py3

This is a minimally maintained fork of [deanmalmgren/textract](https://github.com/deanmalmgren/textract) to replace '*' dependencies because they block usage of `asdf`, `uvx` and modern `pip` (open issue: https://github.com/deanmalmgren/textract/issues/461).

## Installation

### Using conda or pixi (recommended for conda users)

For users who prefer conda package management, a conda recipe is available in the `conda-recipe/` directory. See [conda-recipe/README.md](conda-recipe/README.md) for details on building and submitting to conda-forge.

Once available on conda-forge, install with conda:

```bash
conda install -c conda-forge textract-py3
```

Or using [pixi](https://pixi.sh) (which uses conda-forge by default):

```bash
# Add to your project
pixi add textract-py3

# Or install globally as a CLI tool
pixi global install textract-py3
```

### Using modern package managers

Install with `asdf plugin add textract-py3 https://github.com/amrox/asdf-pyapp.git` and `asdf install textract-py3 latest` or with `uvx` (`uv tool install textract-py3`), `mise`, etc.

### Using pip

```bash
pip install textract-py3
```

## Development

This fork has been migrated to `poetry` and does not have CI/CD. To run locally and release:

```sh
poetry sync
poetry run bumpversion minor
poetry publish --build
```
