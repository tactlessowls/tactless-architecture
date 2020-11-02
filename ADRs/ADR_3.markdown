# 3. External events/updates will all be normalized before entering API Gateway

## Status
Accepted

## Context
![Image of Context](https://github.com/sebfault/architecure-kata-sandbox/blob/master/ADRs/images/imageSource3.PNG)

Lambdas that operate beside API Gateways have the same internal object model. 

## Decision

Since there can be multiple sources of events and information for inventory data, we have decided to add a seperate process to normalize all input date.
Having this separate process will ensure consistency throught the other pipelines 
## Consequence

Since we are adding another process in the input flow, care must be used in the implementation of the normalization process as to not introduce bottlenecks. 
Proper use of lambda functions should add address this. 
