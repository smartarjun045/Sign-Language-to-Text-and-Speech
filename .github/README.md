# GitHub Actions & Dependabot Configuration

This directory contains GitHub Actions workflows and Dependabot configuration for automated dependency management.

## Files Overview

### Workflows (`.github/workflows/`)

1. **`test.yml`** - Continuous Integration
   - Runs on every push and pull request to main branch
   - Tests Python code across multiple Python versions (3.8, 3.9, 3.10, 3.11)
   - Validates imports and basic functionality
   - Includes linting with flake8

2. **`dependabot-automerge.yml`** - Automated Dependency Updates
   - Automatically merges Dependabot pull requests when tests pass
   - Smart merge logic:
     - ✅ Auto-merges patch and minor version updates
     - ✅ Auto-merges major updates for safe dependencies (numpy, pillow)
     - ⚠️ Requires manual review for major updates of critical dependencies
   - Provides detailed comments on PR actions

### Configuration

3. **`dependabot.yml`** - Dependabot Settings
   - Monitors Python dependencies in `requirements.txt`
   - Weekly updates on Mondays at 9:00 AM
   - Groups related dependencies together
   - Assigns PRs to repository owner

## How It Works

1. **Dependabot** creates pull requests for dependency updates weekly
2. **Test workflow** runs automatically on each PR
3. **Auto-merge workflow** waits for tests to pass, then:
   - Approves safe updates automatically
   - Merges approved updates
   - Comments with detailed information
   - Skips risky updates for manual review

## Security & Safety

- Only merges when all tests pass
- Conservative approach for major version updates
- Detailed logging and comments for transparency
- Requires manual review for potentially breaking changes

## Customization

To modify auto-merge behavior, edit the eligibility logic in `dependabot-automerge.yml`. To change update frequency or grouping, modify `dependabot.yml`.