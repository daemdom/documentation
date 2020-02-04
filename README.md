# DaemDom documentation
Documentation for the DaemDom project

## What it is
DaemDom stands for Daemon-based Domotic infrastructure.
It is a collection of background processes that communicate together to form an agile platform for sensors and actions.

## Project goals

- Rely on the linux operating system (deeply)
  - why code yet another
    - process launcher
    - logger
    - cron
    - configuration
    - ...

- Be modular and agile
  - Nodes can be spawned anytime, they announce themself to a few preconfigured static points
  - Nodes advertise a standardized control port
  - Nodes can produce events (e.g. sensor changes) through a publish-subscribe pattern
  - Nodes support introspection and (password protected) actions through their control port
  
- Be resilient
  - Autoconfiguration
  
- Be language agnostic
  - Althoug [Reference implementation](https://github.com/daemdom/corelib-py3) is in Python3, the building blocks were chosen to be independent of the programming language

## Building blocks

The base infrastructure of daemdom is:
  - linux OS (typ. debian) provides system infrastructure
  - [zmq](https://zeromq.org/) provides powerfull sockets
  - [protocol buffer](https://developers.google.com/protocol-buffers) provides language-agnostic reusable data model
