# Contributing Guidelines

Here you will find information on how to contribute to the project.

## Table of Contents
- [Getting Started](#getting-started)
  - [Running the project with Podman](#running-the-project-with-podman)

## Getting Started

There are 2 individual ways to start the project depending on your preference:
1. You can install Hugo locally and run the project on your machine.
   1. For example, on macOS, you can use Homebrew by running `brew install hugo`, and then start the server in the project directory with `hugo server`.
2. Alternatively, you can use Podman (a free alternative to Docker from Red Hat) or Docker to run the project. In this case, you don't need to install Hugo locally and we're using the same OS, which helps avoid issues like "It works on my machine".

### Running the project with Podman

1. Install Podman on your machine. Refer to the official Podman documentation for [installation](https://podman.io/docs/installation)
   1. For example, on macOS, you can use Homebrew by running `brew install podman`.
2. Build the container image with the following command:
```bash
podman build -t hugo-dev -f ContainerFile.dev .
```
3. Run the container with the following command:
```bash
podman run --rm -it -v $(pwd):/src -p 1313:1313 hugo-dev
```

This command starts the Hugo server at `http://localhost:1313`.
