## Create the third actions `action.yml` file

Like our "hello world" action, this action will require at least one `input:` parameter. We need this parameter so that our JavaScript for this action has access to the `output:` from the joke action.

If you recall, in the `my-workflow.yml` file, we stated this action would take a specific input named `catFact:` and we set it's value to the output of the previous action.

```yaml
- name: create-issue
  uses: ./.github/actions/issue-maker
  with:
    catFact: {% raw %}${{steps.cat.outputs.fact}}{% endraw %}
```

Because of this, we need to define `catFact:` as one of our `inputs:` for this action. Remember when we did this with the first action? It looked a little like this:

```yaml
inputs:
  catFact:
    description: "the cat fact retreived from a previous action"
    required: true
    default: "Mona is an Octocat"
```

We also will also need to authenticate to GitHub with the action so that we can interact with the GitHub API. For that we will use a special token that gets created for us when we use actions called [GITHUB_TOKEN](https://help.github.com/en/actions/configuring-and-managing-workflows/authenticating-with-the-github_token)

Our action will also need to accept an input so that we can let the user specify a name for the issue that will be created when this action runs.

---

### :keyboard: Activity: Create the final metadata file

💡All of the following steps take place inside of the `.github/actions/issue-maker` directory.

1. Create and add the following contents to the `.github/actions/issue-maker/action.yml` file:
   You can use [this link]({{quicklink}}) to easily create this file.

   ```yml
   name: "issue maker"

   description: "create and issue with a cat fact as the body"

   inputs:
     issueTitle:
       description: "A name for the cat-fact issue"
       required: true
       default: "A cat fact for you"

     catFact:
       description: "the cat fact retreived from a previous action"
       required: true
       default: "Mona is an Octocat"

     repoToken:
       description: "Authentication token, use secrets.GITHUB_TOKEN"
       required: true

   runs:
     using: "docker"
     image: "Dockerfile"
   ```

1. Commit the changes to the `action-three` branch.
1. Click the green `Commit new file` button
