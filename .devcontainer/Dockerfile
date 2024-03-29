# Use a lightweight base image
FROM python:3.10-slim

# Set the working directory
WORKDIR /workspace

# Install pipenv
RUN pip install --no-cache-dir pipenv

# Copy the Pipfile
COPY Pipfile ./

# Install dependencies from Pipfile
# Ensure that pipenv uses the correct version of Python
RUN pipenv install --python 3.10

# Copy the project code
COPY . .
