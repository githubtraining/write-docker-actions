### :keyboard: Activity: Create the metadata file

💡All of the following steps take place inside of the `.github/actions/cat-facts` directory.

Our action does not require much metadata for it to run correctly. We will not be accepting any inputs, we will however be setting a single output this time.

We will not use the `fact` in in this portion of the course. There will be a later step that will rely on this actions output.

1. Create and add the following contents to the `.github/actions/cat-facts/action.yml` file:

   ```yaml
   name: "my cat fact action"

   description: "Get external data with GitHub Actions"

   outputs:
     fact:
       description: Resulting cat fact from the https://cat-fact.herokuapp.com/facts api

   runs:
     using: "docker"
     image: "Dockerfile"
   ```

1. Commit the changes to the branch named `action-two`

---

I'll respond in this pull request when I notice you have completed these steps
