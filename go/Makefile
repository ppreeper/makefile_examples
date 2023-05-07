BINARY_NAME=hello-world
.DEFAULT_GOAL := run

target: prereq1

build:
	GOARCH=amd64 GOOS=darwin go build -o ./target/${BINARY_NAME}-darwin main.go
	GOARCH=amd64 GOOS=linux go build -o ./target/${BINARY_NAME}-linux main.go
	GOARCH=amd64 GOOS=windows go build -o ./target/${BINARY_NAME}-windows main.go

run: build
	./target/${BINARY_NAME}-linux

clean:
	go clean
	rm ./target/${BINARY_NAME}-darwin
	rm ./target/${BINARY_NAME}-linux
	rm ./target/${BINARY_NAME}-windows

test:
	go test ./...

test_coverage:
	go test ./... -coverprofile=coverage.out

vet:
	go vet

lint:
	golangci-lint run --enable-all