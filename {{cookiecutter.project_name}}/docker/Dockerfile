# syntax=docker/dockerfile:1

FROM python:{{cookiecutter.minimal_python_version}}-slim-buster

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
RUN curl -sSL https://pdm-project.org/install-pdm.py | python3 -
ENV PATH=/root/.local/bin:$PATH

# Project initialization:
RUN pdm install --prod --no-self

# Copy project sources into image
COPY README.md ./
COPY {{cookiecutter.project_slug}} ./{{cookiecutter.project_slug }}/

RUN pdm install --prod
CMD [ "python", "my_python_project/example.py", "-name", "{{cookiecutter.username}}"]
