## Using your new action

At this point we can't expect much from our workflow, if you remember all of its contents are commented out. Let's go ahead and fix that now so that we can see our action fetch us a cat fact.

We are going to add a new trigger to our workflow to make it easier for us to trigger it without the need to push changes to the repository. Remember that every time our workflow runs this action we should see a new cat fact which means we need a good way to make it run a few times. If you recall there are many [events](https://help.github.com/en/actions/automating-your-workflow-with-github-actions/events-that-trigger-workflows#webhook-events) that trigger a workflow run.

We will use the `pull_request` event and specify the activity type to be when an issue get's `labeled`. This will allow us to trigger our workflow by simply placing a label on this pull request.

### :keyboard: Activity: Restore the workflow file

Let's change the tigger and add the cat fact action

1. [Edit]({{workflowFile}}) your current workflow file. It should have the following contents:

   ```yaml
   name: Docker Actions

   on:
     pull_request:
       types: [labeled]

   jobs:
     action:
       runs-on: ubuntu-latest

       steps:
         - uses: actions/checkout@v1

         - name: hello-action
           uses: ./.github/actions/hello-world

         - name: meow
           uses: ./.github/actions/cat-facts
   ```

1. Commit the changes to the `action-two` branch

---

I'll respond once you commit your changes
