# NodeJS Microservices guidelines

Microservices Diagram

![API DMM](./assets/dmm/http-request-dmm.svg?sanitize=true)

The microservices will consts of 4 major parts sitting in two different layers which are the HTTP Context / Business Logic.

* [Router](#router)
* [Controller](#controller)
* [Service](#service)
* [Data Access Layer](#data-access-layer)


## Router

The route is in charge of taking http requests and routing them to the correct controllers.

## Controller

The controllers are reponsible for handling information from the request / response. Extract all relevant information to send to services here. 

## Service

The service layer is where the business logic is implemented. Hashing passwords for comparisons, making calls to databases or API's should be done at this level.

## Data Access Layer

Queries to databased should be defined here, and POJO's should be defined to share data between this layer and the service layer.

