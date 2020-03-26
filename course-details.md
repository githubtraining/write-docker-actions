[GitHub Actions](https://github.com/features/actions) is a powerful platform that empowers your team to go from code to cloud all from the comfort of your own repositories.

This course will teach you the skills needed to begin using and customizing Docker container based actions to fit your unique workflow scenarios.

## What you'll learn

After completing this course, you will be able to:

- Consume actions within a workflow file
- Create custom Docker container based actions
- Create actions in your programming language of choice
- Leverage an external API within an action
- Set and use input parameters for actions
- Publish your newly created action to the marketplace

You'll know the answers to questions like:

- What is a workflow?
- What are actions?
- What is action metadata?
- What is a `Dockerfile`?
- What are GitHub Actions capable of?
- What programming languages can I write GitHub Actions in?
- How do I publish an action?
- How do I customize my action's behavior based on inputs?

## What you'll build

![screenshot of three actions: issue-maker, hello-world, and cat-facts](https://user-images.githubusercontent.com/16547949/77695797-b87f3f00-6f82-11ea-8131-9d362cfc1e4b.png)

In this course you will build three actions that each accomplish different tasks designed to demonstrate the flexibility of creating and consuming Docker Based Actions.

1. **Hello, world!** You will start with the traditional "Hello, world!" program which will teach you where to find the output of a workflow run. You will then modify this "Hello World!" action to accept `input` parameters which allow the action to be more dynamic. This action will be written using the Go programming language.

2. **Cat facts** You will write an action that call upon an external API to retrieve a fact about cats and prints it to the workflows output. You will then modify this cat fact action to set the retrieved data as `output` for another action in the workflow to consume. This action will be written using the Python programming language.

3. **Issue maker** You will open an issue in your repository making the cat fact available to everyone. You will learn how to use the `output` of previous actions as `input` for current actions in this step. This action will be written using the JavaScript programming language.

## Prerequisites

We recommend you first take the following courses on Learning Lab:
- [GitHub Actions: Hello World](https://lab.github.com/githubtraining/github-actions:-hello-world)

Since this is a course on [Docker](https://docs.docker.com/get-started/) based actions, having a basic understanding of Docker is recommended.

## Projects used

- [GitHub Actions Toolkit](https://github.com/actions/toolkit), a multipurpose JavaScript library for writing actions
- [Docker](https://www.docker.com/), a container engine
- [Python](https://www.python.org/doc/essays/blurb/), an interpreted, object-oriented, high-level programming language
- [Go](https://golang.org/), Go is an open source programming language that makes it easy to build simple, reliable, and efficient software
- [Requests](https://requests.readthedocs.io/en/master/), an elegant and simple HTTP library for Python

## Audience

Developers, DevOps Engineers, students, teams