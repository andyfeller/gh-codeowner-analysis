# gh-codeowner-analysis

A `gh` extension to analyze GitHub repository codeowners and branch protection rules.

## Quickstart

1. `gh extension install andyfeller/gh-codeowner-analysis`
1. `gh codeowner-analysis <owner>`
1. Profit! :moneybag: :money_with_wings: :money_mouth_face: :money_with_wings: :moneybag:

## Usage

```shell
$ gh codeowner-analysis --help

Analyze GitHub repository codeowners and branch protection rules.

USAGE
  gh-codeowner-analysis [options] <owner>
  gh-codeowner-analysis [options] <owner>/<repo>

FLAGS
  -c, --cache-dir <cache-dir>         Name of directory containing preserved data to reuse
  -d, --debug                         Enable debugging
  -f, --force                         Whether to overwrite output file if it exists
  -h, --help                          Displays help usage
  -o, --output-file <output-file>     Name of GitHub report file to generate, without '.csv' extension
  -p, --preserve                      Preserve temporary directory containing data
```

This extension generates a report around the codeowners and branch protection rules usage for the target repository owner or repository including:

| Column | Purpose
| --- | ---
| CODEOWNERS_GITHUB_EXISTS | Whether /.github/CODEOWNERS file exists in repository's default branch
| CODEOWNERS_ROOT_EXISTS | Whether /CODEOWNERS file exists in repository's default branch
| CODEOWNER_ERRORS | Whether errors exist in CODEOWNERS file(s)
| BPR_EXISTS | Whether branch protection rule exists on repository's default branch
| BPR_CODEOWNERS_REQUIRED | Whether branch protection rule requires codeowners to review pull requests being merged into default branch
| BPR_CODEOWNERS_REVIEWS | How many reviews the branch protection rule requires to merge pull requests into default branch

The generated report is based on the name of the target repository owner or repository.  For example, `gh codeowner-analysis andyfeller` will result in `andyfeller.csv` while `gh codeowner-analysis andyfeller/gh-codeowner-analysis` will result in `andyfeller-gh-codeowner-analysis.csv`.  By default, the extension will not overwrite this file unless the `-f, --force` flag is provided.

By default, data is pulled and cached temporarily from the GitHub API, but it can be preserved for development or restarting purposes using `-p, --preserve` and `-c, --cache-dir` flags.

## Setup

Like any other `gh` CLI extension, `gh-montage` is trivial to install or upgrade and works on most operating systems:

- **Installation**

  ```shell
  gh extension install andyfeller/gh-codeowner-analysis
  ```
  
  _For more information: [`gh extension install`](https://cli.github.com/manual/gh_extension_install)_

- **Upgrade**

  ```shell
  gh extension upgrade gh-codeowner-analysis
  ```

  _For more information: [`gh extension upgrade`](https://cli.github.com/manual/gh_extension_upgrade)_
