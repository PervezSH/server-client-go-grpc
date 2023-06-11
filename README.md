# Go gRPC Server and Client

This project provides a basic implementation of a gRPC server and client in Go. It demonstrates the following functionality:

- Simple RPC
- Server-side streaming RPC
- Client-side streaming RPC
- Bidirectional streaming RPC

## Project Structure
The project directory structure is as follows:

- `client`: Contains the client implementation and the `main.go` file.
- `server`: Contains the server implementation and the `main.go` file.
- `proto`: Stores the `.proto` file defining the gRPC services and messages.

## Prerequisites
Before running the gRPC server and client, make sure you have the following prerequisites installed:

- Go (1.16 or later): [Installation Guide](https://golang.org/doc/install)
- Protocol Buffers Compiler (protoc): [Installation Guide](https://grpc.io/docs/protoc-installation/)
- gRPC Go plugin: Run the following commands to install the plugin:
```bash
go install google.golang.org/protobuf/cmd/protoc-gen-go@v1.28
go install google.golang.org/grpc/cmd/protoc-gen-go-grpc@v1.2
export PATH="$PATH:$(go env GOPATH)/bin"
```

## Installation
1. Create a new directory for your project and navigate into it:

```bash
mkdir server-client-go-grpc
cd server-client-go-grpc
```

2. Initialize a Go module for the project:

```bash
go mod init github.com/your_username/server-client-go-grpc
```

3. Install the necessary dependencies:
```bash
go mod tidy
```

4. To generate the `.pb.go` files from the `.proto` file, use the following command:

```bash
protoc --go_out=. --go-grpc_out=. proto/greet.proto
```

Note: Depending on the path mentioned in your greet.proto file, you may need to adjust the command accordingly.

## Server Implementation

The server implementation can be found in the `server/main.go` file. This file defines the controllers and services used by the server.

## Client Implementaion

The client implementation can be found in the `client/main.go` file. This file demonstrates how the client interacts with the server.
## Running the application

1. Start the gRPC server:


```bash
go run server/main.go
```

2. Run the gRPC client in a separate terminal session:

```bash
go run client/main.go
```

## License

This project is licensed under the MIT License. 