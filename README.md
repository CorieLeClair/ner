# NER

[![GoDoc](https://godoc.org/github.com/sbl/ner?status.svg)](https://godoc.org/github.com/sbl/ner)
[![Build Status](https://travis-ci.org/sbl/ner.svg?branch=travis)](https://travis-ci.org/sbl/ner)

Named Entity Recognition for golang via the [MITIE (MIT Information
Extraction)](https://github.com/mit-nlp/MITIE) library.

### Installation

- Install the MITIE library and header files. This does vary by platform. On a
  mac the easiest way would be `brew install mitie`. You'd have build from
  source on a linux system.
- The go bindings will fail if the MITIE header files and dynamic library are
  not found.
- `go get github.com/sbl/ner`

### Usage

See `_example/main.go` for a simple usage example. Training files in your
language of choice are required to be able to detect entities in text. See
https://github.com/mit-nlp/MITIE#initial-setup for reference.

```
// In a nutshell
ext, err := ner.NewExtractor(path)
defer ext.Free()
if err != nil {
  return
}

tokens := ner.Tokenize(txt)

es, err := ext.Extract(tokens)
if err != nil {
  return
}
```
