## Source code update!

Great job 👍 next let's update our source code to consume the inputs that are now defined.

### :keyboard: Activity: Update the action source code

💡All of the following steps take place inside of the `.github/actions/hello-world` directory.

1. Add the following contents to the `.github/actions/hello-world/main.go` file:
   You can use [this link]({{quicklink}}) to easily edit this file.

   ```go
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

1. Commit the changes to the `hello-world` branch

---

I'll respond when I notice you have completed this step
