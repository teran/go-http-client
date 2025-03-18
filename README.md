# go-http-client

## Migration notice

This library is moved to [go-collection](https://github.com/teran/go-collection)
repository for unified experience and simplifying maintenance process.
This repository will **not** be deleted for backward compatibility.

[![Go](https://github.com/teran/go-http-client/actions/workflows/go.yml/badge.svg)](https://github.com/teran/go-http-client/actions/workflows/go.yml)
[![Go Report Card](https://goreportcard.com/badge/github.com/teran/go-http-client)](https://goreportcard.com/report/github.com/teran/go-http-client)
[![PkgGoDev](https://pkg.go.dev/badge/github.com/teran/go-http-client)](https://pkg.go.dev/github.com/teran/go-http-client)

HTTP Client for Go to ease interaction with web services, especially APIs

## Usage example

<!-- markdownlint-disable MD010 -->
```go
package main

import (
	"fmt"

	"github.com/pkg/errors"
	ghc "github.com/teran/go-http-client"
)

// FIXME: Change this to your test JSON URL
const testURL = "http://........."

func main() {
	resp := map[string]string{}
	errResp := map[string]string{}
	statusCode, err := ghc.New().
		Base(testURL).
		Get("/json").
		DoJSON(s.ctx, nil, &resp, &errResp)
	if err != nil {
		panic(errors.Wrap(err, fmt.Sprintf("%#v", errResp)))
	}

	fmt.Printf("%#v", resp)
}

```
<!-- markdownlint-enable MD010 -->
