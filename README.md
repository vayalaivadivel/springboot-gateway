# Spring boot api gateway with service registry, discovery and hystrix
The main aim of this project to make micro-service architecture with spring-cloud-api-gateway and service registry with simple circuit breaker
- Design and considerations
- Limitations
- Getting started / Usage Guide
# Design and considerations!
  - It has been designed 4 important components. They are,
  -- api-registry - where all the services are registered with service and client can dicovery the require service with unique name
  -- gatway-service - where the end-user can access all the internal services. This is also registered as part of api-registry since its require to find the internal service.
  -- service - which has one singl api rest end point
  -- hystrix - which avoid cascading failure

# Limitations
- No test cases involved in it
- No Kubernetes
- No profiles(Dev,Test etc.,) maintained.
- No actuator api.
- No https involved.

# Getting started / Usage Guide
- Clone the source code from the git repo.
- Navigate to root folder and execute below mvn command to build all the jars
```sh
       $ mvn clean install
```
- Run all three services one by one with different terminal/command prompt
```sh
       ...service-registry > mvn spring-boot:run
	   ...api-gateway > mvn spring-boot:run
	   ...service-one > mvn spring-boot:run
```
- Click [here](http://localhost:9090/) to check the service-one and gatway-service are registered with service-registry.
- Click [here](http://localhost:8080/get) to test the sample internal service
- Click [here](http://localhost:8080/service1/test1) to test the custom internal service-one

      