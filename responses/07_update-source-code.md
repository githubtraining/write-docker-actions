## Source code update!

Great job 👍 next let's update our source code to consume the inputs that are now defined.

### :keyboard: Activity: Update the action source code

💡All of the following steps take place inside of the `.github/actions/hello-world` directory.

1. Add the following contents to the `.github/actions/hello-world/main.go` file:

   ```go
   package main

   import (
       "fmt"
       "os"
   )

   func main() {

   // Access Inputs as environment vars
   firstGreeting := os.Getenv("INPUT_FIRST-GREETING")
   secondGreeting := os.Getenv("INPUT_SECOND-GREETING")
   thirdGreeting := os.Getenv("INPUT_THIRD-GREETING")

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
