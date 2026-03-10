# AWS Nuke Pipeline

This repository contains a standalone pipeline to "nuke" (delete) every resource in a specific AWS account. It uses the `aws-nuke` tool for comprehensive cleanup.

## Features
- **Comprehensive Deletion**: Targets all resource types across specified regions.
- **Safety Blocklist**: Prevents accidental deletion of production accounts.
- **Resource Filtering**: Excludes critical resources like IAM roles needed for the pipeline itself.
- **Dry-Run by Default**: Built-in safety to preview changes.

## Usage

1.  **Configure `nuke-config.yml`**: Update the account ID and filters (e.g., to protect your Terraform state bucket).
2.  **Run GitHub Action**: Trigger the "Nuke AWS Account" workflow manually.
3.  **Confirm Destruction**: Type `NUKE` to confirm actual deletion.

## Required Secrets/Permissions
- **AWS OIDC**: The pipeline uses OIDC to authenticate with AWS. Ensure the IAM role has sufficient permissions to delete resources.
