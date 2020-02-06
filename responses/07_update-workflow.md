## Workflow update!

The last piece to this actions puzzle is to edit the workflow file so that we can set custom values for these inputs.

### :keyboard: Activity: Update the workflow file

💡All of the following steps take place inside of the `.github/workflows` directory.

1. Add the following contents to the `.github/workflows/my-workflow.yml` file:

   ```yaml
   name: "Docker Actions"

   on: [push]

   jobs:
   action:
       runs-on: "ubuntu-latest"
       steps:
       - uses: actions/checkout@v1

       - name: "hello-action"
           uses: ./.github/actions/hello-world
           with:
           first-greeting: "Learning Lab User"
   ```

1. Commit the changes to the `hello-world` branch

---

I'll respond when I notice you have completed this step
