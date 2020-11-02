# 3. API Gateway will be utilized to handle request handling and communication to different entities

## Status
Pending

## Context
There are 3 differententry points communicating with data in the system:
- Usage by Centarl Kitchen to request or update fridge contents;
- Usage by a customer buying a meal;
- Usage by an internet user handling their subscription details.

Therefore, 3 different API Gateways handling authorisation are needed, so that logic responsible for different flows is logically separated.

## Decision

## Consequence
