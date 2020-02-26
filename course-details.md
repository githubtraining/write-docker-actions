[GitHub Actions](https://github.com/features/actions) is a powerful platform that empowers your team to go from code to cloud all from the comfort of your own repositories.

Over the duration of this course, approximately 1 hour, you will learn the skills needed to begin using and customizing GitHub Actions to fit your unique workflow scenarios.

## What you'll learn

In this course you will learn how to:

- Consume actions within a workflow file
- Create custom Docker based actions
- Publish your newly created action to the marketplace

You'll know the answers to questions like:

- What is a workflow?
- What are actions?
- What is action metadata?
- What is a Dockerfile?
- What are GitHub Actions capable of?
- What programming languages can I write GitHub Actions in?

## What you'll build

In this course you will build three actions that each accomplish different tasks designed to demonstrate the flexibility of creating and consuming Docker Based Actions.

First, you will start with the traditional "Hello World!" program which will teach you where to find the output of a workflow run. You will then modify this "Hello World!" action to accept `input` parameters which allow the action to be more dynamic. This action will be written using the Go programming language.

Second, you will write an action that call upon an external API to retrieve a fact about cats and prints it to the workflows output. You will then modify this cat fact action to set the retrieved data as `output` for another action in the workflow to consume. This action will be written using the Python programming language.

Lastly, you will write a third action that will open an issue in your repository making the cat fact available to everyone. You will learn how to use the `output` of previous actions as `input` for current actions in this step. This action will be written using the JavaScript programming language.

## Prerequisites

We will be using the GitHub UI to build and consume our actions. Since this is a course on [Docker](https://docs.docker.com/get-started/) based actions, having a basic understanding of Docker is recommended.

It is also worth noting that this course is one of many in a GitHub Actions Learning Path. It is recommended that you complete this learning path in order to get the most out of your Learning Lab experience.

## Projects used

- [Docker](https://www.docker.com/), a container engine
- [GitHub Actions Toolkit](https://github.com/actions/toolkit), a multipurpose JavaScript library for writing actions
- [Python](https://www.python.org/doc/essays/blurb/), an interpreted, object-oriented, high-level programming language
- [Go](https://golang.org/), Go is an open source programming language that makes it easy to build simple, reliable, and efficient software
- [Requests](https://requests.readthedocs.io/en/master/), an elegant and simple HTTP library for Python

## Audience

This is a great course for intermediate developers who are looking to learn how to create custom actions to benefit their workflows. The focal point of the content isn't on which language to create your actions in, rather how to put the pieces of source code, metadata, Dockerfile and workflows together to accomplish your goals.
