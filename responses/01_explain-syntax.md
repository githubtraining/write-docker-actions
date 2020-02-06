## Go on... Tell me more!

I'm glad you asked. Let's take a look at the workflow file that we just committed to this repository.

```yaml
name: CI

on: [push]

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
      - uses: actions/checkout@v1
      - name: Run a one-line script
        run: echo Hello, world!
      - name: Run a multi-line script
        run: |
          echo Add other actions to build,
          echo test, and deploy your project.
```

This file is made up of a series of metadata, as well as behaviors that we wish to happen when the workflow is triggered.

Let's take a second to talk about each of the pieces that we see here:

- `name: CI`
  - This is the user-defined name for the workflow. This shows up on the Actions tab so we can see which workflows, and their statuses, run on this repository.
  - As you can see, our's is currently named `CI`
- `on: [push]`
  - This defines the **event** that will tigger a workflow on this repository. Currently we are listening for any [push event](https://developer.github.com/v3/activity/events/types/#pushevent) that happens within this repository.
  - Also note that this is an array, which means we can trigger this workflow [on more than one event](https://help.github.com/en/actions/automating-your-workflow-with-github-actions/events-that-trigger-workflows#about-workflow-events) if that is our intended behavior.
- `Jobs:`
  - This is our first block of instructions. We are defining our first job for this workflow.
  - In this case, the job has been named `build`
  - We also define the runner for the job as `runs-on: ubuntu-latest`
  - Finally we define the steps for this job which can either rely on specific actions, or run commands directly. As we can see there are three steps which show a mixed usage of actions and commands.
    - `uses: actions/checkout@v1`
    - ```
      name: Run a one-line script
      run: echo Hello, world!
      ```
    - ```
      name: Run a multi-line script
      run: |
        echo Add other actions to build,
        echo test, and deploy your project.
      ```

---

📖Take a deeper dive into [workflow components](https://help.github.com/en/actions/automating-your-workflow-with-github-actions/configuring-workflows)
📖Read more about [configuring workflows](https://help.github.com/en/actions/automating-your-workflow-with-github-actions/configuring-workflows)

<details><summary>Has Learning Lab stopped responding?  Your Actions workflow might be failing. Click here for troubleshooting help.</summary>

When a GitHub Actions workflow is running, you should see some checks in progress, like the screenshot below.

![Checks in progress box](https://i.imgur.com/uO6iqYd.png)

If the checks don't appear or if the checks are stuck in progress, there's a few things you can do to try and trigger them:

- Refresh the page, it's possible the workflow ran and the page just hasn't been updated with that change
- Try making a commit on this branch. Our workflow is triggered with a `push` event, and committing to this branch will result in a new `push`
- Edit the workflow file on GitHub and ensure there are no red lines indicating a syntax problem
  </details>
