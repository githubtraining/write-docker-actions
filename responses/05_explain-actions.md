## Anatomy of an action

Earlier you learned how the different pieces of GitHub Actions work together. Now you will learn about the components that make up an individual action.

Remember, an action is the unit of work that a workflow file executes when it reaches that task. They are called by referencing them as the value to the `uses:` key in a workflow step.

### What makes up an action?

Docker actions consist of three key components:

| Component                | Description                                                                                                                                                                                                                 |
| ------------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Action source code files | These files contain the logic of your action. This includes any dependencies or custom modules that your main logic may need.                                                                                               |
| Action metadata file     | This file contains information that the actions source code can use. An example of this is allowing a developer to specify an API key as an input variable for your action to consume. This file MUST be named `action.yml` |
| Dockerfile               | This file defines the environment and dependencies for the action. It is best practice that this file be named `Dockerfile`                                                                                                 |

### Let's take a look at how those components fit together.

- **The workflow, usually `workflow.yml`**, is the **user** facing component. It must be housed in `.github/workflows/` and doesn't need to be called `workflow.yml`, but its essence is a workflow. This is what we interact with directly when we want to supply input, or consume the output of a given action. You can think of `workflow.yml` as a user-interface for the `action.yml` file.
- **The action's metadata, called `action.yml`**, is the **interface** between the **user** and the **source code** of the action. It is housed in a directory just for the action. This file may contain default values for inputs and outputs that the source code relies on. Those values can be overwritten by the `workflow.yml` file, but their default values live here and allow the action to execute properly if no values are supplied. This file also defines a high-level environment for the source code, such as whether to use Docker or Node.js and the execution entry point.
- **The action's source code** files define the logic of an action. It is housed in a directory just for the action. The **user** doesn't interact with these files directly. There could be as little as one source code file, but there is no hard rule on how modular an action can be!
- **`Dockerfile`** is only needed when creating Docker based actions and it is responsible for packaging up the environment as well as the source code for the given action. It is housed in a directory just for the action. This file is read and a Docker image is created from it. Once the image is created a container is created from the image and the action is executed.

_Although the **workflow** file is used to allow us to set the `inputs` and `outputs` using the `with:` keyword it is **not** a required component of an individual action._

---

**The failing workflow**

You may be following along on the [Actions tab]({{store.actionsUrl}}) of this repository. If you are, you'll notice that the workflow we set up previously is failing. That is the currently expected behavior: we referenced an action in the `hello-world` directory, which doesn't yet exist. We will be fixing that as we move forward with the lesson.
