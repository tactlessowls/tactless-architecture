# 1. CloudWatch events to schedule AWS Lambda Functions. To be used for triggering polling to external APIs

## Status
Accepted

## Context
Client has stated that external sources (such as Smart Fridges and Point of Sale) can communicate using their own API. 

![Image of Context](https://github.com/sebfault/architecure-kata-sandbox/blob/master/ADRs/images/imageSource1.PNG)

## Decision
This serverless architecture can use seperate lambda functions to poll and communicate data from external APIs.
Multiple lambdas can be scheduled by CloudWatch to execute on a customized interval (i.e: hit external API endpoint x every y minutes).

If any new system is introduced, we can add another lambda function to support the new API.
In terms of scaling, AWS lambda functions scales automatically if needed.

## Consequence

There exists a possibilty to NOT get the most updated data whenever an event happens in between scheduled polling intervals.
This limitation is addressed in ADR 2. Otherwise, the scheduling interval can be adjusted to minimize this limitation.
