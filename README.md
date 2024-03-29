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

# Project Folder Structure

For the sake of clarity, we should split files accordingly into the four sections. Notice that config files are held at the project root level and utilities method sit outside of the API folder, which should be restricted to API related logic.

```
├── api
│   ├── controllers
│   │   ├── login-controller.js
│   │   └── signup-controller.js
│   ├── data-access
│   │   └── user-service.js
│   ├── middlewares
│   │   └── user-authorization
│   ├── routes
│   │   ├── login-route.js
│   │   └── signup-route.js
│   └── services
│       ├── login-service.js
│       └── signup-service.js
├── config.json
└── utilities
    └── logger.js

7 directories, 10 files
```
