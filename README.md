# cachito-gomod-twenty

This repository is used for a cachito/cachi2 integration test that verifies proper processing of Go projects. Starting in Go version 1.21, the `go` directive in go.mod specifies the required minimum version of go for the module, **which also must be greater than or equal to the `go` line of all dependencies.**

If a module requiring minimum go version 1.20 has a dependency on a module requiring minimum go version 1.20, Go 1.21 will update the `go` directive in go.mod file to use 1.21. This is new behavior introduced in Go 1.21 and may be unexpected from the perspective of the caller.

The top-level module in this repository requires minimum go 1.20 but depends on a module with minimum 1.21. Cachito/cachi2 should process the top-level module with Go 1.20 in order to avoid unexpected changes to go.mod.
