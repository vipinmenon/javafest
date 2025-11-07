# Spring Boot GraphQL Demo

This is a Spring Boot application that demonstrates GraphQL API implementation using the graphql-java library.

## Prerequisites

- Java 17 or higher
- Maven 3.6 or higher

## Running the Application

1. Clone the repository
2. Navigate to the project directory
3. Run the application using Gradle:

```bash
./gradlew bootRun
```

4. The GraphQL API will be available at: http://localhost:8080/graphql
5. You can use the GraphiQL interface at: http://localhost:8080/graphiql

## Sample Queries

### Get all organizations
```graphql
query {
  organizations {
    id
    name
    address
    employees {
      id
      firstName
      lastName
    }
  }
}
```

### Get a specific employee with their car
```graphql
query {
  employee(id: "1") {
    id
    firstName
    lastName
    email
    position
    organization {
      name
    }
    car {
      model
      brand
    }
  }
}
```

### Advanced search
```graphql
query {
  advancedSearch(filters: {
    carBrand: "Tesla"
  }) {
    cars {
      id
      model
      brand
    }
    employees {
      firstName
      lastName
    }
    organizations {
      name
    }
  }
}
```

## Sample Mutations

### Create a new car
```graphql
mutation {
  createCar(model: "X5", brand: "BMW", employeeId: "1") {
    id
    model
    brand
    employee {
      firstName
      lastName
    }
  }
}
```
