# GraphQL Client MCP Server

An MCP (Model Context Protocol) server that provides tools to interact with the Spring GraphQL Demo API.

## Overview

This MCP server exposes GraphQL queries and mutations as tools that can be used by AI assistants to interact with your Spring Boot GraphQL application.

## Features

### Query Tools

- **get_organizations** - Get all organizations with their employees
- **get_organization** - Get a specific organization by ID
- **get_employees** - Get all employees with their organization and car details
- **get_employee** - Get a specific employee by ID
- **get_cars** - Get all cars with their employee details
- **get_car** - Get a specific car by ID
- **get_organizations_by_car_brand** - Get organizations filtered by car brand
- **advanced_search** - Perform advanced search across cars, employees, and organizations with multiple filter options

### Mutation Tools

- **create_car** - Create a new car and assign it to an employee
- **update_car** - Update an existing car's details
- **delete_car** - Delete a car by ID

## Configuration

The server is configured in your MCP settings file at:
```
/Users/vipinmenon/Library/Application Support/Bob-IDE/User/globalStorage/ibm.bob-code/settings/mcp_settings.json
```

### Environment Variables

- `GRAPHQL_ENDPOINT` - The GraphQL API endpoint (default: `http://localhost:8091/graphql`)

## Prerequisites

1. **Start the Spring GraphQL Demo application**:
   ```bash
   cd /Users/vipinmenon/Public/workspace/conference/javafest/demo/spring-graphql-demo
   ./gradlew bootRun
   ```

2. The application should be running on `http://localhost:8091`

## Usage Examples

Once the MCP server is connected, you can use the tools through your AI assistant:

### Query Examples

**Get all organizations:**
```
Use the get_organizations tool to fetch all organizations
```

**Get a specific employee:**
```
Use the get_employee tool with id "1" to get employee details
```

**Search for Tesla cars:**
```
Use the advanced_search tool with carBrand "Tesla" to find all Tesla cars
```

### Mutation Examples

**Create a new car:**
```
Use the create_car tool to create a BMW X5 for employee "1"
```

**Update a car:**
```
Use the update_car tool to change car "1" to a Tesla Model Y
```

**Delete a car:**
```
Use the delete_car tool to remove car "1"
```

## Development

### Building

```bash
npm run build
```

### Watching for changes

```bash
npm run watch
```
