# git-hooks

Git hooks for GO pre-commit format by gofmt.

This script will run `goimports` and `go vet` to format and validate the files.

## Install

1. Clone this repo
2. Set executable `sudo chmod +x $PATH_TO_REPO/git-hooks/pre-commit`
3. Change to target project folder `cd $PATH_TO_PROJECT`
4. Config project git `git config core.hooksPath $PATH_TO_REPO/git-hooks/`
5. Install **goimports** if not exist:
   1. Check with `which goimports`
   2. GO version < 1.17 `go get golang.org/x/tools/cmd/goimports`
   3. GO version >= 1.17 `go install golang.org/x/tools/cmd/goimports`
   4. Set PATH env
      1. Edit `~/.bashrc` (or `~/.zshrc` based on your shell)
      2. Add following lines

            ```shell
            export GOPATH=$HOME/go
            export PATH=$PATH:$GOROOT/bin:$GOPATH/bin
            ```

## Test

1. Copy `$PATH_TO_REPO/git-hooks/pre-commit` into `$PATH_TO_PROJECT/.git/hooks/`
2. Execute the file `pre-commit`

## Example

Wrong format:

```go
package test

import "stringsx"

import "fmt"

import "os"

func Title(s string)  {
    fmt.Println(strings.Title(s))
}

func test() 
{
    Title("hello world")
}
```

Formatted:

```go
package test

import (
	"fmt"
	"strings"
)

func Title(s string) {
	fmt.Println(strings.Title(s))
}

func test() {
	Title("hello world")
}
```

## Note

- `git config core.hooksPath` only available for git version > 2.9
