# Reusable Workflows for Java & C#

This repository contains a collection of reusable GitHub Actions workflows designed to streamline CI/CD processes for Java and C# projects. By using these workflows, you can easily integrate standardized build, test, and deployment steps across multiple repositories and projects.

---

## Features

- **Java Workflows**  
  - Build and test using Maven or Gradle  
  - Code quality checks (e.g., Checkstyle, SpotBugs)  
  - Packaging and artifact publishing  

- **C# Workflows**  
  - Build and test using .NET CLI  
  - Code analysis and formatting  
  - Packaging and deployment to NuGet or other targets  

- **Reusable & Modular**  
  - Easy to include and customize in your own workflows  
  - Parameterized inputs for flexibility  
  - Centralized updates for best practices  

---

## How to Use

### Import a reusable workflow

In your project repository, add a workflow that calls one of the reusable workflows from this repo. For example, to run the Java build workflow:

```yaml
name: Java CI

on:
  push:
    branches: [main]
  pull_request:
    branches: [main]

jobs:
  build:
    uses: your-org/reusable-workflows/.github/workflows/name-build.yml@main
    with:
      java-version: '17' / dotnet-version: "7.0"
      build-tool: 'maven' # or 'gradle'
    secrets:
      # add secrets if required
