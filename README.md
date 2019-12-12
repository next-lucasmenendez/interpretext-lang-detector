[![GoDoc](https://godoc.org/github.com/next-lucasmenendez/interpretext-lang-detector?status.svg)](https://godoc.org/github.com/next-lucasmenendez/interpretext-lang-detector)
[![Report](https://goreportcard.com/badge/github.com/next-lucasmenendez/interpretext-lang-detector)](https://goreportcard.com/report/github.com/next-lucasmenendez/interpretext-lang-detector)

# Interpretext lang detector
Package interpretext lang detector measures and suggest language according to input text based on languages dictionary occurrences.

The languages dictionaries are based on [bitcoin/bips/bip-0039-wordlists](https://github.com/bitcoin/bips/blob/master/bip-0039/bip-0039-wordlists.md).

## Installation
```bash
go install github.com/next-lucasmenendez/interpretext-lang-detector
```

## Demo
```go
package main

import (
	"fmt"
	langdetector "github.com/next-lucasmenendez/interpretext-lang-detector"
)

func main() {
	i := `Go (often referred to as golang) is a programming language created at Google in 2009 by Robert Griesemer, Rob Pike, and Ken Thompson. It is a compiled, statically typed language in the tradition of Algol and C, with garbage collection, limited structural typing, memory safety features and CSP-style concurrent programming features added. The compiler and other language tools originally developed by Google are all free and open source.`

	p := langdetector.Detect(i)
	fmt.Println(p) // map[en:1]

	r := langdetector.Suggest(i)
	fmt.Println(r) // en
}
```