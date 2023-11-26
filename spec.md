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
- queries to programs:
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
- web-app that allows the user to make queries.

## plan

## references


