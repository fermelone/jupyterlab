FROM mcr.microsoft.com/vscode/devcontainers/base:ubuntu

# Set environment variables
ENV PYTHONUNBUFFERED 1

# Install Python and pip
RUN apt-get update && export DEBIAN_FRONTEND=noninteractive \
    && apt-get -y install --no-install-recommends python3 python3-pip \
    && apt-get clean -y && rm -rf /var/lib/apt/lists/*

# Set up the working directory
WORKDIR /workspaces

# Install any needed packages specified in requirements.txt
COPY requirements.txt .
RUN pip3 install --no-cache-dir -r requirements.txt

# Set up aliases
RUN echo 'alias python=python3' >> ~/.bashrc && \
    echo 'alias pip=pip3' >> ~/.bashrc