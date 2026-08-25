# ISARIC Clinical Epidemiology Platform Documentation

This is the repository for the ISARIC Clinical Epidemiology Platform documentation site:

https://docs.isaric.org

It contains all source content and assets required to build and deploy the documentation, via a Read the Docs (RTD) site:

https://isaricplatform.readthedocs.io

Requests for pages with the ISARIC domain URLs are forwarded to RTD (using an appropriate method). The RTD build configuration YML is `.readthedocs.yaml`.

## Project TOML & Dependencies

All dependencies are documentation dependencies, principally [Sphinx](https://www.sphinx-doc.org/). They are defined in the ``dependencies`` variable of the project TOML.

[Astral UV](https://docs.astral.sh/uv/) is the recommended package manager. This can be installed in different ways, but the simplest is via `pip`:
```shell
python -m pip install uv
```
By default UV installs and manages all dependencies in a new `.venv` subfolder in the working directory - if a pre-existing environment is preferred specify its path via the `UV_PROJECT_ENVIRONMENT` environment variable before running UV commands. To install (or sync) all the project dependencies via the project TOML run the following command:
```shell
uv sync --verbose --all-groups --all-extras --no-project-install --no-cache --refresh --inexact
```
This will usually update the `uv.lock` file: if so, the file should be staged and committed in the normal way.

## Building and Viewing the Documentation Site Locally

To build and view the entire site locally run the following command from the repository root:
```shell
make html
```
and open the `_build/html/index.html` page in a browser of your choice.
