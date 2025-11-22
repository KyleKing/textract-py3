# Conda Recipe for textract-py3

This directory contains the conda recipe for building and distributing textract-py3 via conda/conda-forge.

## Building the Package Locally

To build the conda package locally, you need to have `conda-build` installed:

```bash
conda install conda-build
```

Then build the package:

```bash
conda build conda-recipe/
```

## Installing the Locally Built Package

After building, you can install the package with:

```bash
conda install --use-local textract-py3
```

## Testing the Package

Test the installation:

```bash
textract --help
python -c "import textract; print(textract.__version__)"
```

## Submitting to conda-forge

To make this package available on conda-forge, follow these steps:

1. **Fork the staged-recipes repository**:
   - Go to https://github.com/conda-forge/staged-recipes
   - Click "Fork" to create your own copy

2. **Add the recipe**:
   - Copy the contents of this `conda-recipe` directory to `recipes/textract-py3/` in your fork
   - Ensure `meta.yaml` is properly formatted

3. **Submit a Pull Request**:
   - Create a new branch in your fork
   - Commit the recipe files
   - Open a pull request to conda-forge/staged-recipes
   - The conda-forge team will review and provide feedback

4. **After merge**:
   - Once merged, a new feedstock repository will be created at `conda-forge/textract-py3-feedstock`
   - Future updates can be submitted via PRs to that feedstock repository
   - The package will be automatically built and uploaded to the conda-forge channel

## Installing from conda-forge (after submission)

Once the package is available on conda-forge, users can install it with:

### Using conda

```bash
conda install -c conda-forge textract-py3
```

Or add conda-forge to your channels:

```bash
conda config --add channels conda-forge
conda install textract-py3
```

### Using pixi

[Pixi](https://pixi.sh) is a modern package manager that uses conda-forge by default:

```bash
# Add to your project dependencies
pixi add textract-py3

# Or install globally as a CLI tool
pixi global install textract-py3
```

Pixi provides fast, reproducible environments and is especially convenient for managing project dependencies with automatic lock file generation.

## Updating the Recipe

When a new version of textract-py3 is released:

1. Update the `version` variable in `meta.yaml`
2. Update the `sha256` hash (download the new tarball from PyPI and calculate its SHA256)
3. Update any dependency version requirements if needed
4. Increment the `build: number` (or reset to 0 if version changed)

To get the SHA256 hash for a new version:

```bash
# Download the tarball from PyPI
curl -O https://pypi.io/packages/source/t/textract-py3/textract_py3-VERSION.tar.gz

# Calculate SHA256
sha256sum textract_py3-VERSION.tar.gz
```

## Additional Resources

- [conda-forge documentation](https://conda-forge.org/docs/)
- [Contributing packages to conda-forge](https://conda-forge.org/docs/maintainer/adding_pkgs/)
- [conda-build documentation](https://docs.conda.io/projects/conda-build/en/stable/)
