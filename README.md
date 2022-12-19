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
