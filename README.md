# Reusable Workflows for Codecov by Sentry

This repository contains reusable workflows for integrating Codecov by Sentry into your CI/CD pipeline.

> These workflows is part of the Codebelt umbrella and ensures a consistent way of: 
> 
> - Defining your CI/CD pipeline 
> - Structuring your repository
> - Keeping your codebase small and feasible
> - Writing clean and maintainable code
> - Deploying your code to different environments
> - Automating as much as possible
>
> A paved path to excel as a DevSecOps Engineer.

## Available Workflows

- [default.yml](.github/workflows/default.yml) - the default workflow that:
  - [fetches the codebase](https://github.com/codebeltnet/git-checkout),
  - [runs the Codecov by Sentry analysis](https://github.com/codebeltnet/codecov-scan).

### Usage

To call this workflow in your GitHub repository, you can follow these steps:

```yaml
sonarcloud-call:
    uses: codebeltnet/jobs-codecov/.github/workflows/default.yml@v1
```

### Inputs

```yaml
with:
  # The fully qualified name of the repository, including owner, e.g. codebeltnet/xunit.
  repository:
  # The maximum time in minutes to allow the job to run. Default is 15 minutes.
  timeout-minutes: 15
```

### Secrets

```yaml
secrets:
  CODECOV_TOKEN: ${{ secrets.CODECOV_TOKEN }}
```

### Outputs

This workflow has no outputs.

### Example

```yaml
jobs:
  codecov:
    needs: [build,test]
    uses: codebeltnet/jobs-codecov/.github/workflows/default@v1
    with:
      repository: codebeltnet/xunit
    secrets: inherit
```

## Contributing to Reusable Workflows for SonarQube Cloud

Contributions are welcome! 
Feel free to submit issues, feature requests, or pull requests to help improve these workflows.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
