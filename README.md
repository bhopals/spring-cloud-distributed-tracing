# Introduction
Spring Cloud Sleuth introduces tracing information into your service calls. The tracing information can be used in conjuction with a log aggregation tool (Papertrail) to query log messages by one piece of their tracing information (the correlation id).  Also, we will be exploring how to do distributed tracing using Spring Cloud Sleuth and Zipkin.     

## Project Details

- 1.  A Spring Cloud Config server that is deployed as Docker container and can manage a services configuration information using a file system or GitHub-based repository.

- 2.  A Eureka server running as a Spring-Cloud based service.  This service will allow multiple service instances to register with it.  Clients that need to call a service will use Eureka to lookup the physical location of the target service.

- 3.  A Zuul API Gateway.  All of our microservices can be routed through the gateway and have pre, response and post policies enforced on the calls.

- 4.  A organization service that will manage organization data used within EagleEye.

- 5.  A new version of the organization service.  This service is used to demonstrate how to use the Zuul API gateway to route to different versions of a service.

- 6.  A special routes services that the the API gateway will call to determine whether or not it should route a user's service call to a different service then the one they were originally calling.  This service is used in conjunction with the orgservice-new service to determine whether a call to the organization service gets routed to an old version of the organization service vs. a new version of the service.

- 7.  A licensing service that will manage licensing data used within EagleEye.

- 8.  A Postgres SQL database used to hold the data for these two services.

- 9.  A Kafka message bus to transport messages between services.

- 10. A Redis service to act as a distributed cache.

## Software needed
1.	[Apache Maven] (http://maven.apache.org)
2.	[Docker] (http://docker.com)
3.	[Git Client] (http://git-scm.com)


## Building Docker Image


   **mvn clean package docker:build**


## Running services 

   **docker-compose -f docker/common/docker-compose.yml up**

## Related Topics

- Single Searchable Source
- Log Aggregating
- Distributed Tracing
  - Spring Cloud Sleuth and the OpenZipkin (Zipkin)
- Correlation ID

- Spring Cloud Sleuth
  - Add correlation IDs
- Papertrail
  - Aggregate logging data from multiple sources into single searchable database.
- Zipkin

  - A data-visualization tool

- A transcation flows across multiple services
- A Distributed Transaction
- Funnel Data to common data store

- Trace Id
- Span Id

- Unified Logging Architecture
- Unified Logging Platform
- Zipkin

  - Zipkin is a distributed tracing platform that allows you to trace transactions across multiple service invocations.

- Correlation IDs can be used to link log entries across multiple services
- A Log Aggregation platform
- Zipkin allows you to graphically see the flow of your transactions and understand the performance characteristics

- Options for Log Aggregation Solutions for Use with Spring Boot
  - ELK (Elasticsearch, Logstash, Kibana)
  - Graylog
  - Splunk
  - Papertrail
  - Sumo Logic