

<p align="center">
  <img width="600" src="https://raw.githubusercontent.com/y_ksenia/cookiecutter-pdm/main/docs/static/cookiecutter.svg">
</p style = "margin-bottom: 2rem;">

---

[![Release](https://img.shields.io/github/v/release/y_ksenia/cookiecutter-pdm)](https://pypi.org/project/cookiecutter-pdm/)
[![Build status](https://img.shields.io/github/actions/workflow/status/y_ksenia/cookiecutter-pdm/main.yml?branch=main)](https://github.com/y_ksenia/cookiecutter-pdm/actions/workflows/main.yml?query=branch%3Amain)
[![Supported Python versions](https://img.shields.io/pypi/pyversions/cookiecutter-pdm)](https://pypi.org/project/cookiecutter-pdm/)
[![Docs](https://img.shields.io/badge/docs-gh--pages-blue)](https://y_ksenia.github.io/cookiecutter-pdm/)
[![License](https://img.shields.io/github/license/y_ksenia/cookiecutter-pdm)](https://img.shields.io/github/license/y_ksenia/cookiecutter-pdm)


This is a modern Cookiecutter template that can be used to initiate a Python project with all the necessary tools for development, testing, and deployment. It supports the following features:

- [PDM](https://pdm.fming.dev/latest/) for dependency management
- CI/CD with [GitHub Actions](https://github.com/features/actions)
- Pre-commit hooks with [pre-commit](https://pre-commit.com/)
- Code quality with [black](https://pypi.org/project/black/), [ruff](https://github.com/charliermarsh/ruff), [mypy](https://mypy.readthedocs.io/en/stable/), and [deptry](https://github.com/y_ksenia/deptry/)
- Publishing to [Pypi](https://pypi.org) or [Artifactory](https://jfrog.com/artifactory) by creating a new release on GitHub
- Testing and coverage with [pytest](https://docs.pytest.org/en/7.1.x/) and [codecov](https://about.codecov.io/)
- Documentation with [MkDocs](https://www.mkdocs.org/)
- Compatibility testing for multiple versions of Python with [Tox](https://tox.wiki/en/latest/)
- Containerization with [Docker](https://www.docker.com/)

---
<p align="center">
  <a href="https://y_ksenia.github.io/cookiecutter-pdm/">Documentation</a> - <a href="https://github.com/y_ksenia/cookiecutter-pdm-example">Example</a> -
  <a href="https://pypi.org/project/cookiecutter-pdm/">PyPi</a>
</p>

---


## Quickstart

On your local machine, navigate to the directory in which you want to
create a project directory, and run the following two commands:

``` bash
pip install cookiecutter-pdm
ccpdm
```

Alternatively, install `cookiecutter` and directly pass the URL to this
Github repository to the `cookiecutter` command:

``` bash
pip install cookiecutter
cookiecutter https://github.com/y_ksenia/cookiecutter-pdm.git
```

Create a repository on GitHub, and then run the following commands, replacing `<project-name>`, with the name that you gave the Github repository and
`<github_author_handle>` with your Github username.

``` bash
cd <project_name>
git init -b main
git add .
git commit -m "Init commit"
git remote add origin git@github.com:<github_author_handle>/<project_name>.git
git push -u origin main
```

Finally, install the environment and the pre-commit hooks with

 ```bash
 make install
 ```

You are now ready to start development on your project! The CI/CD
pipeline will be triggered when you open a pull request, merge to main,
or when you create a new release.

To finalize the set-up for publishing to PyPi or Artifactory, see
[here](https://y_ksenia.github.io/cookiecutter-pdm/features/publishing/#set-up-for-pypi).
For activating the automatic documentation with MkDocs, see
[here](https://y_ksenia.github.io/cookiecutter-pdm/features/mkdocs/#enabling-the-documentation-on-github).
To enable the code coverage reports, see [here](https://y_ksenia.github.io/cookiecutter-pdm/features/codecov/).

## Acknowledgements

This project is partially based on [Florian Maas\'s](https://github.com/fpgmaas)\'s 
[cookiecutter-pdm](https://github.com/fpgmaas/cookiecutter-pdm) and [Alexey Devyatkin\'s](https://github.com/KaiL4eK)\'s 
[pyproject-cookiecutter]https://github.com/KaiL4eK/pyproject-cookiecutter)
repository.
