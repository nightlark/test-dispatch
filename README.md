# test-dispatch

This repository contains test workflows for GitHub Actions `workflow_dispatch` triggers.

## Test: Workflow Dispatch with Dashed Parameters

The workflow `.github/workflows/test-dash-params.yml` tests whether `workflow_dispatch` input parameters can have dashes in their names and which syntax variations work for accessing them.

### Parameters

- **dry-run**: A parameter with a dash in the name
- **dry_run**: A parameter with an underscore in the name

### Test Cases

The workflow includes four conditional steps that test different syntaxes:

1. **Test 1**: `inputs.dry-run` - Dot notation with dash (may not work)
2. **Test 2**: `inputs['dry-run']` - Bracket notation with dash (expected to work)
3. **Test 3**: `inputs.dry_run` - Dot notation with underscore (expected to work)
4. **Test 4**: `inputs['dry_run']` - Bracket notation with underscore (expected to work)

### How to Run

1. Go to the Actions tab in GitHub
2. Select the "Test Workflow Dispatch with Dashed Parameters" workflow
3. Click "Run workflow"
4. Set the parameters to 'true' to enable the corresponding test steps
5. Click "Run workflow" to execute

The steps that execute will show which syntaxes successfully work for accessing the parameters.