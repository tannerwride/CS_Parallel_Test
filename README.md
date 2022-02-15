# CSM Hands on Activity - Parallelism and Test Splitting

## How to use this README

There are two branches of this activity, the main branch and the answers branch. The main branch will give instructions for viewing config files and questions associated with the file. 

To view answers and possible optimization ideas, switch to the answers branch. 

## Prereqs

- Completion of the CSM training in Circle Up
- Permission to view customer config files and builds

## Parallelism and Test Splitting to ease Developer Pain

**Problem**: The last thing developers want is a long development lifecycle. When developers run a lot of tests, it can bog down their build and increase duration time. The more tests a project runs, the longer it will take a job to complete on a single machine, which extends the development cycle and delays shipping to end users.

**Solution**: Developers can run tests in parallel by splitting them across multiple separate executors to reduce build time. Users can define a parallelism level to specify how many separate executors get spun up for the test job and use either the CircleCI CLI to split test files or environment variables to configure each parallel machine individually. 

## A Key Difference

- Parallelism: is running the same job (any job, it does not have to be a test job) on different nodes at the same time. Customers use parallelism for test jobs (test splitting) 95% of the time. The other 5% is to check that the programming language is used correctly (“linting”). Although test splitting takes up the majority of the use case for parallelism, the term parallelism is a general term that encompasses other use cases for running one job across multiple executors, like linting. 

- Test splitting: is splitting a one test job across multiple executors. This term exclusively refers to using parallelism for test jobs and no other use cases.
