# Amrutam CI/CD Pipeline

This repository contains the CI/CD pipeline configuration using Drone CI for automated code quality scanning and deployment.

## Pipeline Overview

To view the pipeline digram: https://app.eraser.io/workspace/6i7kdgf4uBB3SFmE7J4e

The project uses two main pipelines:

### 1. SonarQube Code Analysis
- Automatically scans code for quality and security issues
- Runs on push and merge events to the master branch
- Uses SonarQube scanner for code analysis

### 2. DigitalOcean Deployment
- Builds and deploys the application on DigitalOcean infrastructure
- Pipeline triggers on merge events to master branch
- Runs on a DigitalOcean droplet (s-1vcpu-1gb) in NYC1 region

## Prerequisites

- SonarQube instance running at your configured domain
- DigitalOcean account with API token
- Drone CI server configured with your repository

## Environment Setup

The following secrets need to be configured in Drone CI:

- `sonar_token`: Authentication token for SonarQube
- `do_token`: DigitalOcean API token

## Pipeline Steps

### SonarQube Pipeline
1. Code checkout
2. SonarQube scan with configured parameters
   - Project Key: my_project_key
   - Project Name: My Project Name
   - Version: 1.0.0

### DigitalOcean Pipeline
1. Frontend build
2. Image testing
3. Docker image compression
4. Image push to registry

## Contributing

When contributing to this project, ensure your code will pass the SonarQube quality gates before merging to master.
