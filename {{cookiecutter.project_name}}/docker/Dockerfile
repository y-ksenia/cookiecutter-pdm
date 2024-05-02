# syntax=docker/dockerfile:1

FROM  python:{{cookiecutter.minimal_python_version}}-slim-buster

# Prepare system environment
ENV LANG=C.UTF-8 \
  LC_ALL=C.UTF-8

# Prepare system packages
RUN apt-get update && \
  apt-get install -y --no-install-recommends \
  curl make \
  && rm -rf /var/lib/apt/lists/*

# Setup directory to work inside image
RUN mkdir -p /workspace
WORKDIR /workspace

# Copy only requirements to cache them in docker layer
COPY pdm.lock pyproject.toml ./

# Install PDM
RUN url -sSL https://pdm-project.org/install-pdm.py | python3 -

# Project initialization:
RUN pdm install --no-self

# Copy project sources into image
COPY README.md ./
COPY {{cookiecutter.project_slug}} ./{{cookiecutter.project_slug }}/

CMD [ "python", "{{cookiecutter.project_slug}}//foo.py"]
