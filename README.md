# Init Service Tool

A CLI tool to quickly scaffold new Go services with modern project structure and best practices.

## Features

- Create new Go service projects with Uber Fx
- Pre-configured project structure following Clean Architecture
- Built-in templates for common patterns and use cases
- Modern Go project layout with clear separation of concerns
- Integrated logging, configuration, and database support
- Ready-to-use HTTP server with middleware
- Swagger documentation setup

## Installation

```bash
go install github.com/chinhtran-dev/init-service-tool@latest
```

## Project Structure

The generated service follows this structure:

```
myservice/
├── cmd/
│   ├── app/
│   |   └── main.go      # Application entry point
|   ├── config/          # Configuration files
├── external/        # External service integrations
├── internal/
│   ├── app/            # Application bootstrapping
│   ├── http/           # HTTP layer
|   |    ├── handler/   # HTTP handlers
|   |    └── router/    # Route definitions
|   ├── middleware/     # HTTP middleware
│   ├── model/         # Domain models
│   ├── repository/    # Data access layer
│   └── service/       # Business logic layer
├── pkg/
│   ├── constant/      # Shared constants
│   ├── database/      # Database utilities
│   ├── errors/        # Custom error types
|   ├── graceful/      # Graceful shutdown
|   ├── logger/        # Logging utilities
|   ├── swagger/       # Swagger handler
|   ├── util/          # Common utilities
│   └── wrapper/       # Common wrappers
├── test/
│   └── integration/   # Integration tests
├── go.mod            # Go module file
├── .env              # Environment variables
├── Makefile          # Build automation
└── README.md
```

## Requirements

- Go 1.21 or higher
- Git

## Usage

1. Create a new service:
```bash
init-service-tool new --name yourservice
```

2. Navigate to your service directory:
```bash
cd yourservice
```

3. Install required tools:
```bash
make install-tools
```

4. Initialize the project:
```bash
make init
```

5. Format code:
```bash
make fmt
```

6. Configure your environment:
- Copy `.env.example` to `.env`
- Update values in `.env` file

7. Build the service:
```bash
make build
```

8. Run the service:
```bash
make run
```

## Available Make Commands

- `make init` - Initialize project and install dependencies
- `make install-tools` - Install required development tools
- `make build` - Build the service
- `make run` - Run the service
- `make test` - Run tests
- `make fmt` - Format code
- `make lint` - Run linters
- `make swagger-init` - Generate Swagger documentation
- `make swagger-build` - Update Swagger documentation