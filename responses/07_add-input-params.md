## Using input parameters

A "Hello World" message is great, but let's personalize it a little bit. We will do this by adding an **input** parameter to the `action.yml`, `workflow.yml` and `main.go` files.

Although this example may seem a little lightweight input parameters have a very flexible use case. Consider a scenario where you need to access secret API key with your action, or when you need to specify the path to a given file. Inputs allows for these problems to be easily solved.

#### A quick example

To add inputs we need to add the `inputs:` parameter to the `action.yml` file. The `inputs:` parameter has a few parameters of its own.

| Parameter      | Description                                                        | Required                      |
| -------------- | ------------------------------------------------------------------ | ----------------------------- |
| `description:` | String describing the purpose of the input                         | True                          |
| `required:`    | Boolean value indicating if the input parameter is required or not | False (Default value is True) |
| `default:`     | String representing a default value for the input parameter        | False                         |

---

Let's take a look at how this fits into an `action.yml` file.

**action.yml**

```yaml
name: "my hello action"

description: "say hello with actions"

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
```

_The placement of your `inputs:` is not strictly enforced, however it has become commonplace to ensure the `runs:` statement is defined after your `inputs:` and `outputs:` in your `action.yml` file._

---

## So what is actually happening here?

Well, in the `my-workflow.yml` file we could specify values for inputs we just created:

- first-greeting
- second-greeting
- third-greeting

Or we could leave them out and rely on their default values.

The example below demonstrates a mix of both:

**my-workflow.yml**

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
          firstGreeting: "Learning Lab User"
```

Now that there are inputs in the action's metadata the **user** can interface with them by supplying values. In this case **Learning Lab User** was passed as the value for the `firstGreeting` input which overrides the **default** value, specified in the `action.yml`, of **Hubot**

---

**main.go**

```golang
package main

import (
	"fmt"
	"os"
)

func main() {

  // Access Inputs as environment vars
  firstGreeting := os.Getenv("INPUT_FIRSTGREETING")
  secondGreeting := os.Getenv("INPUT_SECONDGREETING")
  thirdGreeting := os.Getenv("INPUT_THIRDGREETING")

  // Use those inputs in the actions logic
  fmt.Println("Hello " + firstGreeting)
  fmt.Println("Hello " + secondGreeting)

  // Someimes inputs are not "required" and we can build around that
  if thirdGreeting != "" {
    fmt.Println("Hello " + thirdGreeting)
    }

}
```

In our actions source code we can access the inputs as if they are environment variables. GitHub Actions takes every `inputs:` value and converts it by adding `INPUT_` and making the value uppercase.

For example:

- `firstGreeting` = `INPUT_FIRSTGREETING`
- `secondGreeting` = `INPUT_SECONDGREETING`
- `someInput` = `INPUT_SOMEINPUT`

_How you access environment variables will vary by language_

---

📖Read more about the [input parameter](https://help.github.com/en/actions/automating-your-workflow-with-github-actions/metadata-syntax-for-github-actions#inputs)
