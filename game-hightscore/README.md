#Game APIS

## How to generate APIs using the protobuff compiler

### Installation

1. Install protobuf using `brew` for mac:
```bash
    $ brew install protobuf
```
1. Install `proto` & `protoc-gen-go` from github.com/protobuf:
```bash
    $ go get -u github.com/golang/protobuf/proto
    $ go get -u github.com/golang/protobuf/protoc-gen-go
```
1. Install `grpc` from google.golang.org/grpc:
```bash
    $ go get -u google.golang.org/grpc
```

### Write a `.proto` file

1. Refer [highscore.proto](game-highscore/v1/highscore.proto) for the same

### Generate go code using `protoc`
1. Update your `PATH` so that the `protoc` compiler can find the plugins:
```bash
    $ export PATH="$PATH:$(go env GOPATH)/bin"
```
1. Run the following command to create generated code in the game directory
```bash
    $ protoc --go_out=plugins=grpc:. *.proto
```
1. Refer to [highscore.pb.go](game-highscore/v1/game/highscore.pb.go) for the generated go code