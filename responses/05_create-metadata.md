## Enough talk, lets do this!

Now that we know what action metadata is, let's create the metadata for our **hello-world** action.

### :keyboard: Activity: Create the metadata file

💡All of the following steps take place inside of the `.github/actions/hello-world` directory.

We will start with using the parameters that are **required** and later implement some optional parameters as our action knowledge grows.

1. Create and add the following contents to the `.github/actions/hello-world/action.yml` file:
   You can use this [link]({{quicklink}}) to easily create this file

   ```yaml
   name: "my hello action"

   description: "say hello with GitHub Actions"

   runs:
     using: "docker"
     image: "Dockerfile"
   ```

1. Commit the changes to a new branch named `hello-world`
1. Create a pull request titled **Create action.yml**.
1. Supply the pull request body content and click `Create pull request`.

---

I'll respond in your new pull request when I notice you have completed these steps
