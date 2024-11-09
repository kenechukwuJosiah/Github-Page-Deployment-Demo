# GitHub Pages Deployment Workflow

This repository contains a GitHub Actions workflow to automatically deploy the contents of the `public` directory to GitHub Pages upon changes to the `main` branch.

## Workflow Overview

The workflow file `.github/workflows/deploy.yml` defines a CI/CD pipeline that:

1. Runs whenever a push or pull request is made to the `main` branch.
2. Deploys the `public` directory contents to GitHub Pages.

## Workflow Details

- **Name**: `GitHub Page Deployment`
- **Triggers**:
  - `push` events on the `main` branch
  - `pull_request` events on the `main` branch
  - Manual dispatch using `workflow_dispatch`

### Jobs

#### Build and Deployment

The `build` job runs on `ubuntu-latest` and performs the following steps:

1. **Checkout Code**: Uses the `actions/checkout@v3` action to clone the repository.

2. **Setup GitHub Pages**: Configures GitHub Pages with the `actions/configure-pages@v3` action.

3. **Upload Artifact**: Uses `actions/upload-pages-artifact@v1` to upload the contents of the `public/` directory as an artifact for deployment.

4. **Deploy to GitHub Pages**: Deploys the uploaded artifact to GitHub Pages using `actions/deploy-pages@v1`.

### Project Link

https://roadmap.sh/projects/github-actions-deployment-workflow
