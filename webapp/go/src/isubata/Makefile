.DEFAULT_GOAL := build

.PHONY: lint
lint: fmt
	@go vet ./...
	@staticcheck ./...

.PHONY: fmt
fmt: install
	@goimports -l -w .

.PHONY: build
build:
	@go build -o isubata

.PHONY: test
test:
	@go test -v ./...

.PHONY: coverage
coverage:
	@go test -cover ./... -coverprofile=cover.out
	@go tool cover -html=cover.out -o cover.html

.PHONY: install
install:
	@go install golang.org/x/tools/cmd/goimports@v0.14.0
	@go install honnef.co/go/tools/cmd/staticcheck@v0.4.6
