# 2. A Message Queuing service is to be used to subscribe to events and updates via (Amazon Simple Queue Service) SQS 

## Status
Accepted

## Context
![Image of Context](https://github.com/tactlessowls/tactless-architecture/blob/main/ADRs/images/imageSource2.PNG)

## Decision
For those of the API that support subscription based model, we have decided to have queu service that will subscrube to events. These events are fed into data processing where the data is transformed to common model and send down the pipe

Smart fridges push the updates -> in this case events are to be added to a queueing service (SQS in AWS world). Events will trigger lambdas that will transform  data into domain objects and invoke internal lambdas responsible for handling events from fridge.

## Consequence
Event based updates will allow the system to always have live updates as these events occur. The users will have access to the most up to date information about product availablity. 
