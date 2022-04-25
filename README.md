# git-hooks

Git hooks for GO pre-commit format by gofmt

## Install

1. Clone this repo
2. Set executable `sudo chmod +x $PATH_TO_REPO/git-hooks/pre-commit`
3. Change to target project folder `cd $PATH_TO_PROJECT`
4. Config project git `git config core.hooksPath $PATH_TO_REPO/git-hooks/`

## Test

1. Copy `$PATH_TO_REPO/git-hooks/pre-commit` into `$PATH_TO_PROJECT/.git/hooks/`
2. Execute the file `pre-commit`

## Note

- `git config core.hooksPath` only available for git version > 2.9
