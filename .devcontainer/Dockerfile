# Use a lightweight base image
FROM python:3.9-slim

# Set the working directory
WORKDIR /workspace

# Install system dependencies
RUN apt-get update && \
    apt-get install -y git && \
    rm -rf /var/lib/apt/lists/*

# Install pipenv
RUN pip install --no-cache-dir pipenv

# Environment variable to ensure pipenv creates the virtual environment inside the project
ENV PIPENV_VENV_IN_PROJECT=1

# Copy the Pipfile (and optionally Pipfile.lock)
COPY Pipfile* ./

# Install dependencies from Pipfile, creating a virtual environment in the .venv directory
RUN pipenv install --python 3.9

# Set up the Python virtual environment as a Jupyter kernel
RUN pipenv run python -m ipykernel install --user --name=my-kernel

# Copy the project code
COPY . .
