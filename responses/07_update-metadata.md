## Your turn!

Now that we know what input parameters are, let's edit the metadata for our **hello-world** action.

### :keyboard: Activity: Update the metadata file

💡All of the following steps take place inside of the `.github/actions/hello-world` directory.

1. Add the following contents to the `.github/actions/hello-world/action.yml` file:
   You can use [this link]({{quicklink}}) to easily edit this file.

   ```yaml
   name: "my hello action"

   description: "say hello with GitHub Actions"

   inputs:
     firstGreeting:
       description: "who would you like to greet in the console"
       required: true
       default: "Hubot"

     secondGreeting:
       description: "another person to greet"
       required: true
       default: "Mona the Octocat"

     thirdGreeting:
       description: "a third greeting"
       required: false

   runs:
     using: "docker"
     image: "Dockerfile"
   ```

1. Commit the changes to this branch

---

I'll respond when I notice you have completed this step
