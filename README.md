# AWS Nuke Config

Config for aws-nuke that retains SSO and Control Tower related resources.

## Prerequisites

- [aws-nuke](https://github.com/rebuy-de/aws-nuke) installed

## Usage

1. Edit config to include account IDs that s blocked. i.e should never be deleted. This is a security meassure taken by the aws-nuke owner
2. Add the account ID **and** AWS account Alias for the account(s) that should be targeted
   - To create an AWS account alias, run
   ```bash
   aws iam create-account-alias --account-alias my-alias
   ```
   with valid AWS credentials
3. For each target account, add the `presets` (filters) that should be applied
4. To execute, run

```bash
aws-nuke --config nuke_config.yaml
```

To run without any security checks and to delete straight away, run

```bash
aws-nuke --config nuke_config.yaml --no-dry-run -q --force --force-sleep 3
```
