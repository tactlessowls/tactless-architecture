# 4. API Gateway will be utilized to handle request handling and communication to different entities

## Status
Accepted

## Context
![Image of Context](https://github.com/tactlessowls/tactless-architecture/blob/main/ADRs/images/imageSource4.PNG)

There are 3 different entry points communicating with data in the system:
- Centarl Kitchen accessing/managing item data
- Customers accessing item data
- Updates that are received from external systems/APIs

## Decision

We decided to have separete API Gateways for each of these points of access, ensuring that authentication/authorization is separated by default.

## Consequence

System will have different concerns regarding access and security for the aforemention access points.
Care must be made in implementation of these endpoints as not to duplicate logic and concerns.
