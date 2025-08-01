# Genesis of Wisdom

# Deployment Pipeline Overview

This repository contains a GitHub Actions workflow for deploying the sample web application to Azure App Service.

## Environments

- **Development**: `devopswebapp2-dev` Azure App Service
- **Testing**: `devopswebapp2-test` Azure App Service
- **Production**: `devopswebapp2-prod` Azure App Service (manual approval required)

## Deployment Process

1. Code pushed to `main` triggers deployment pipeline.
2. App deploys automatically to Development.
3. On success, app deploys to Testing.
4. Deployment to Production requires manual approval in GitHub UI.
5. After approval, the app is deployed to Production.

## Approvals

Production deployment is gated by GitHub environment protection rules with required reviewers.

## Secrets

Azure publish profiles are stored as GitHub secrets:
- `AZURE_WEBAPP_PUBLISH_PROFILE`