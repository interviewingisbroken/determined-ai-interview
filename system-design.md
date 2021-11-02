# Log Viewer Implementation

1. 5 min to discuss the interview goals and agenda
2. 10 min to review this document independently. The interviewer will briefly walk through the document.
3. Discussion about this project.

## Goal

We are building a log viewer for a given experiment. You are a frontend engineer. In this interview, you are expected to: 

1. Drive the conversation to discuss this project with a product manager and a backend engineer. The product manager is the stakeholder and to provide support for product requirements. The backend engineer is to provide knowledge on the APIs and the backend system.
2. Ask questions to clarify the product requirements.
3. Propose APIs to the backend engineer (fill out the API Proposal section).
4. Break down the whole project into small executable tasks (fill out the Task Breakdown section).

## Concepts 

 - Experiment: An experiment is a model training procedure. Logs are generated through this procedure.
 - Agent: Experiment run on multiple agents. Each agent might generate different logs at any moment. Users want to filter the logs by the selected agents. 

## Visual Aid

![design](/logviewer.png)

## Requirements

- Experiment Header:
  - Experiment ID
  - Experiment status (queued, running, paused, canceled, errored, completed)
- Filter:
  - Log level (multiple selectable)
  - Agent ID (multiple selectable)
  - Start and end datetime of the log timestamp.
- Log Table
  - The log table displays a limited number of the latest logs. New logs appear if there are new log events happen. You need to guarantee the freshness of the logs. You need to ensure the frontend is performant with a large amount of logs.
  - Logs are sorted from the latest to the oldest. 
  - The log table support scrolling down. As you scroll down, older logs will be displayed. If you scroll down to the bottom, you will see the oldest logs.
  - The log table contains columns for: log level (error, warning, info), timestamp of each entry, agent ID that the log was generated from, and log message. 
 
 ## API Proposal
 
 TASK: Propose restful APIs to the backend engineer. Please provide as much detail as possible.
 
 Consider the following: 
 - What kind of parameters might we need? 
 - What protocols should be used, e.g. GET, PUT, WebSocket, long-polling, etc.? Why? 
 - How do these endpoints get consumed by the frontend? 

Fill this out: 

GET /api/v1/experiments/[experiment-id>]/logs 

Parameters:

Response: 
```
[
  { 
    level: ‘info’, 
    message: ‘Running batch 5893 of 262144...’, 
    timestamp: 1627837871.204, 
  }, 
  { 
    level: ‘error’, 
    message: ‘Unable to write to disk during checkpointing!’, 
    timestamp: 1627837871.553, 
  }, 
] 
```
  
## Task Breakdown
  
TASK: Break down the whole project into tasks and create tickets for all of the tasks.  
  
Consider the following: 
 - What are the different implementation tasks?
 - What kind of components do we need to build out and how do they work together? 
  
For the estimate column, you can use the following standard to measure the work:
 - Small: work that is relatively easy and often a very small amount of time. 
 - Medium: work equivalent to roughly 2-3 times a Small ticket in level of effort.
 - Large: work that is difficult and/or quite time consuming to do but do not break down into smaller tickets. 
 
| Ticket Title| Description | Estimate | Dependencies |
| ----------- | ----------- | -------- | ------------ |
| fill out    | fill out    | fill out | fill out     |


