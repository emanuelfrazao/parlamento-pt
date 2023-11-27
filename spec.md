---
tile: project specification
description: define MVP version of the project
authors: muita gente
version: 0.1
---

# Specification of the project

1. [introduction](#intro)
1. [user specification](#user-specification)
1. [technical specification](#technical-specification)

## intro

the goal of the project is to create a simple web-app that allows the user to analyse and compare the party proposals for the Portuguese Parliament elections of March 2024, namely:
- making questions about each party's position on a given topic;
- having a summary of the proposals of each party on a given topic;
- provide a coverage map of the topics covered by each party;
- comparing between parties on each given utility;
- comparing withing party changes between elections.

### context

now that LLM's (or SLM's) are trivial to use and train, we do!

### limitations

- very reduced budget
- very reduced time

## user specification

...

## technical specification

### overview

the main components of the project are:
- documents corresponding to party programs – from different elections;
- queries to these programs:
    - on a single program:
        - given a **program** and a **topic**, 
            - summarize the position of the party on that topic;
            - identify the parts of the program that are relevant to that topic;
        - given a **program** and a **question**,
            - answer the question;
            - identify the parts of the program that are relevant to that question;
        - given a **program**,
            - identify the topics covered by the program;
    - on multiple programs – comparing multiple single program queries across:
        - multiple parties;
        - multiple elections;
- web-app that allows the user to make the queries and get the results.

we start by analyzing the needs of **querying the documents**, which is the core of the product, and then analyze how to **store the documents** given the constraints.

### querying the documents

- [document sources](document_sources.md)

the queries envisioned may be described as machine learning tasks:
- **question answering** - given a document and a question, answer the question;
- **topic summarization** - given a document and a topic, summarize the position of the party on that topic.
- **topic identification** - given a document, identify the topics covered by the document, for a predefined set of topics;

furthermore, for all of the queries, we want to be able to:
- identify the parts of the document that are relevant to the query, and
- compare the results of the queries across multiple documents.

all these tasks, under the constraint of providing references along with the answer, can be solved with a combination of:
- a _Vector-Embedding Database_ (VDB), and
- one or many _Language Model(s)_ (LM),

— provided that:
- the VDB contains a vector embedding of each sub-chapter of the document;
- the LM(s) models Portuguese, and can leverage the VDB to answer the queries.

**NOTE**: there are trade-offs to consider in using a single LM for all tasks or one per task:
- in using a single LM:
    - the LM needs to be large in order to be generalist;
    - large LM's are 
        - expensive to train (and harder to find pre-trained in portuguese), and
        - expensive use;
    - on the other hand, the vector embeddings of the VDB are not task-specific, hence a single LM could be used for all tasks;
- in using one LM per task:
    - the LM's can be smaller and task-specific (hence cheaper to train and use);
    - we need to investigate the best solution for the VDB, namely:
        - having a single embedding for all models/tasks, or
        - having one embedding per model/task;

we detail the envisioned solution for each task, using both options, below.

#### single LM

#### one LM per task


#### storing the documents


### architecture



## plan

## references


