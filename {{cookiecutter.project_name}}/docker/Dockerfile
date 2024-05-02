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

# Install PDM
RUN pip install -U pdm
ENV PDM_CHECK_UPDATE=false

# Copy project sources into image
COPY pdm.lock pyproject.toml README.md  ./
COPY my_python_project ./my_python_project/

# Install dependencies and project into the local packages directory
RUN pdm install --check --prod --no-editable

# Retrieve packages
CMD ["pdm", "run", "python", "my_python_project", "--name", "{{cookiecutter.username}}"]
