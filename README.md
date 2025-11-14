# Azure Storage Account ARM Template

This repository contains an ARM template to deploy an Azure Storage Account with GitHub Actions workflow.

## Files

- `azuredeploy.json` - Main ARM template
- `azuredeploy.parameters.json` - Parameters file
- `.github/workflows/deploy.yml` - GitHub Actions workflow

## Setup

1. Create Azure service principal:
```bash
az ad sp create-for-rbac --name "github-actions" --role contributor --scopes /subscriptions/{subscription-id} --sdk-auth
```

2. Add GitHub secrets:
   - `AZURE_CREDENTIALS` - Output from step 1
   - `AZURE_SUBSCRIPTION_ID` - Your Azure subscription ID

3. Update parameters in `azuredeploy.parameters.json`

4. Push to main branch to trigger deployment