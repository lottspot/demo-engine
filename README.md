# demo-engine

## What is engine?

Engine is a pipeline programming framework which decouples the implementation of
the pipeline from the compute infrastructure on which it runs. This has some
useful implications, including vendor-agnostic integration with CI
infrastructure and streamlined parity between production and local development
environments.

## Basic concepts

Every engine pipeline is composed of three elements:

1. Name
2. Stages
3. Subjects

### name

The pipeline name acts as a container of all its composing elements.

### stages

Every pipeline has one or more stages. Sequences of stages can be organized into
reusable packages known as _patterns_.

### subjects

A subject represents an individual application or build which is produced or
deployed by the pipeline. An individual subject may exist across multiple
stages (e.g., a subject named "my-app" might exist within both the "build" and
the "deploy" stages).

## How it works

Pipelines, stages, and subjects are implemented as a hierarchy of Makefiles. The
subject Makefile is where individual actions may be programmed as bash commands.
These files provide access to two APIs:

1. Context
2. Methods

### context

These are variables which allow the programmer to reference values such as the
filesystem path to a project or the environment name

### methods

These are pieces of abstracted functionality which are provided to pipeline
programmers.
