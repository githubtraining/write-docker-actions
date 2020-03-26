## Edit the current workflow

Currently `my-workflow.yml` is not set up correctly for our use-case. It worked great for allowing us to take a high-level look at workflows, but if we want to use our custom actions there are some changes that we have to make to it.

### :keyboard: Activity: Remove boilerplate steps from `my-workflow.yml`

1. [Edit]({{workflowFile}}) the `.github/workflows/my-workflow.yml` so that it has the contents below:

   ```yaml
   name: Docker Actions

   on: [push]

   jobs:
     action:
       runs-on: ubuntu-latest

       steps:
         - uses: actions/checkout@v1
   ```

1. Commit these file changes to this branch

---

I'll respond when you push changes to this pull request.
