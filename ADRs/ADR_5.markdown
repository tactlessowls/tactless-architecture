# 5. Lambda handlers will communicate with the DB Cache and share a separated VPC

## Status
Accepted

## Context

Each API request requires some data from the Data Cache and to perform some processing of this data per request.

## Decision

We decided to use lamda functions to process each separate request in order.

## Consequence

This will allow to incrementally add new endpoints while being able to update and test each path independently.
As per lambda's pricing model, we will only need to pay per use of these lambda functions.
This has potential to reduce cost substantially if the correct functions are implemented.
