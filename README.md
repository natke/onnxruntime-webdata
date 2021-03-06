# ONNX Runtime website data

Pull issue and pull request data from GitHub using the GitHub API, and export based on time to close.

## Setup

Create a Personal Access Token in GitHub. Set the starting page for issues and PRs. GitHub rate-limits API calls to about 50 calls of pages containing 100 items, so historical data is preserved in this repo. If old PRs or issues have been updated, then the query may need to be run over the old data anyway.

```bash
export GITHUB_TOKEN=<value of personal access token>
export GITHUB_ISSUE_START_PAGE=109
export GITHUB_PR_START_PAGE=3
```

## Pull issue data

```bash
python get_issues.py
```

Gets all issues from the onnxruntime GitHub repo.

## Export all issue data to CSV

```bash
python convert_issues_to_csv.py
```

Filters issues that have the component:documentation label, and calculates the time to close, in days, and exports as CSV.

## Pull PR data

```bash
python get_prs.py
```

Gets all of the pull requests against the gh-pages branch from the onnxruntime GitHun repo

## Export all PR data to CSV

```bash
python convert_prs_to_csv.py
```

Calculates the time to close, in days, and exports as CSV.
