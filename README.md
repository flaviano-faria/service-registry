echo "# Service Registry

A Spring Boot microservice that implements Netflix Eureka Server for service discovery and registration in a microservices architecture.

## Overview

This project provides a centralized service registry using Netflix Eureka Server, which allows microservices to register themselves and discover other services in the system. It's part of the EAD (Enterprise Application Development) microservices ecosystem.

## Features

- **Service Discovery**: Centralized registry for microservices
- **Service Registration**: Automatic service registration and health monitoring
- **Load Balancing**: Integration with client-side load balancing
- **High Availability**: Support for multiple Eureka server instances
- **Health Checks**: Automatic health monitoring of registered services

## Technology Stack

- **Java 21**: Latest LTS version of Java
- **Spring Boot 3.5.5**: Application framework
- **Spring Cloud 2025.0.0**: Cloud-native development tools
- **Netflix Eureka Server**: Service discovery and registration
- **Maven**: Build and dependency management

## Prerequisites

- Java 21 or higher
- Maven 3.6 or higher
- Git

## Getting Started

### 1. Clone the Repository

\`\`\`bash
git clone <repository-url>
cd service-registry
\`\`\`

### 2. Build the Project

\`\`\`bash
# Using Maven wrapper (recommended)
./mvnw clean install

# Or using Maven directly
mvn clean install
\`\`\`

### 3. Run the Application

\`\`\`bash
# Using Maven wrapper
./mvnw spring-boot:run

# Or using Maven directly
mvn spring-boot:run

# Or run the JAR file
java -jar target/service-registry-0.0.1-SNAPSHOT.jar
\`\`\`

### 4. Access the Eureka Dashboard

Once the application is running, you can access the Eureka dashboard at:

\`\`\`
http://localhost:8761
\`\`\`

## Configuration

The application is configured via \`application.yaml\`:

\`\`\`yaml
server:
  port: 8761

spring:
  application:
    name: ead-service-registry

eureka:
  client:
    register-with-eureka: false
    fetch-registry: false
\`\`\`

### Configuration Details

- **Port**: The service registry runs on port \`8761\`
- **Application Name**: \`ead-service-registry\`
- **Eureka Client Settings**:
  - \`register-with-eureka: false\` - This server doesn't register itself
  - \`fetch-registry: false\` - This server doesn't fetch registry information

## Project Structure

\`\`\`
service-registry/
├── src/
│   ├── main/
│   │   ├── java/
│   │   │   └── com/ead/serviceregistry/
│   │   │       └── ServiceRegistryApplication.java
│   │   └── resources/
│   │       └── application.yaml
│   └── test/
│       └── java/
│           └── com/ead/serviceregistry/
│               └── ServiceRegistryApplicationTests.java
├── pom.xml
├── mvnw
├── mvnw.cmd
└── README.md
\`\`\`

## Dependencies

### Core Dependencies

- **spring-cloud-starter-netflix-eureka-server**: Netflix Eureka Server implementation
- **spring-boot-starter-test**: Testing framework and utilities

### Spring Cloud Version

- Spring Cloud: \`2025.0.0\`
- Spring Boot: \`3.5.5\`

## Development

### Running Tests

\`\`\`bash
./mvnw test
\`\`\`

### Building for Production

\`\`\`bash
./mvnw clean package -Pproduction
\`\`\`

## Microservices Integration

To register a microservice with this registry, add the following dependencies to your microservice's \`pom.xml\`:

\`\`\`xml
<dependency>
    <groupId>org.springframework.cloud</groupId>
    <artifactId>spring-cloud-starter-netflix-eureka-client</artifactId>
</dependency>
\`\`\`

And configure it in your \`application.yaml\`:

\`\`\`yaml
eureka:
  client:
    service-url:
      defaultZone: http://localhost:8761/eureka/
spring:
  application:
    name: your-service-name
\`\`\`

## Monitoring and Health Checks

The Eureka dashboard provides:

- **Instances**: List of all registered services
- **General Info**: Server status and configuration
- **DS Replicas**: Information about Eureka server replicas
- **Health**: Service health status

## Security Considerations

For production environments, consider:

- Enabling authentication
- Using HTTPS
- Network security
- Firewall configuration

## Troubleshooting

### Common Issues

1. **Port Already in Use**: Ensure port 8761 is available
2. **Connection Refused**: Check if the service is running
3. **Services Not Registering**: Verify client configuration

### Logs

Check application logs for detailed error information:

\`\`\`bash
tail -f logs/application.log
\`\`\`

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Add tests if applicable
5. Submit a pull request

## License

This project is part of the EAD microservices ecosystem. Please refer to the project's license file for more information.

## Support

For issues and questions:

1. Check the troubleshooting section
2. Review the Spring Cloud documentation
3. Create an issue in the repository

## Version History

- **0.0.1-SNAPSHOT**: Initial version with basic Eureka server setup

---

**Note**: This is a development snapshot. For production use, ensure proper configuration and security measures are in place." > README.md