# Stage 1: Build stage
FROM python:3.10.8-slim AS builder

LABEL NAME="Giveaways-God"
LABEL VERSION="1.0.0"

# Install base utilities
RUN apt-get update && \
  apt-get install -y --no-install-recommends build-essential && \
  apt-get install -y wget && \
  apt-get clean && \
  rm -rf /var/lib/apt/lists/*

# Set up the working directory
WORKDIR /app

# Stop Python from creating __pycache__ folders
ENV PYTHONDONTWRITEBYTECODE 1

# Copy the poetry.lock and pyproject.toml files
COPY pyproject.toml ./

# Install project dependencies
RUN python -m pip install poetry 
# Don't run yet, have to do it manually
#RUN poetry config virtualenvs.create false #error code 1
#RUN poetry install --no-dev --no-interaction --no-ansi #error code 1

COPY src /app/
