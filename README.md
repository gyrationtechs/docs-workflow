# Task Management API Documentation

This repository contains the documentation for the Task Management API, following a "Docs as Code" approach with automated validation and deployment.

## Project Structure

```
├── docs/
│   ├── getting-started.md
│   └── api-guide.md
├── api/
│   └── openapi.yaml
├── .vale.ini
├── .spectral.yaml
├── .github/
│   └── workflows/
│       ├── vale-check.yml
│       └── openapi-check.yml
└── README.md
```

## Documentation Validation

This project uses automated tools to ensure documentation quality:

- **Vale**: Lints Markdown files for style, grammar, and consistency
- **Spectral**: Validates OpenAPI specifications for best practices and standards

## Local Development

### Prerequisites

- Node.js (v16 or higher)
- Vale CLI
- Redocly CLI

### Setup

1. Install Vale:
   ```bash
   # macOS
   brew install vale
   
   # Or download from https://vale.sh/
   ```

2. Install Redocly CLI:
   ```bash
   npm install -g @redocly/cli
   ```

3. Run local validation:
   ```bash
   # Validate Markdown files
   vale docs/
   
   # Validate OpenAPI spec
   spectral lint api/openapi.yaml
   ```

## CI/CD Pipeline

The project includes GitHub Actions workflows that automatically:

1. **Vale Check**: Validates all Markdown documentation on every push and PR
2. **OpenAPI Check**: Validates the OpenAPI specification and generates/deploys API reference documentation

## Contributing

When contributing to the documentation:

1. Follow the established writing style guidelines
2. Ensure your changes pass Vale validation
3. Update the OpenAPI specification if adding new endpoints
4. Test your changes locally before submitting a PR

## API Reference

The live API reference documentation is available at: https://[username].github.io/[repo-name]/ 