### :keyboard: Activity: Hello World

Great job @{{user.login}}, you now have action metadata for your first action. The next piece we will add will be the logic of our action. In this case, our logic will be written in Go.

If you are not familiar with Go programming that's perfectly okay, you are here to learn about writing actions! All the necessary code for each language will be provided for you!

The first iteration of our action will follow the traditional path of logging "Hello World" 👋to the console. We will expand on this as we move forward, for now it's a good test to make sure all of our files are set up correctly 😄

1. Create and add the following contents to the `.github/actions/hello-world/main.go` file:
   You can use this [link]({{quicklink}}) to easily create this file

   ```go
   package main

   import "fmt"

   func main() {
       fmt.Println("Hello Docker Actions")
   }
   ```

2. Commit the changes to the existing `hello-world` branch
3. Click the green `Commit new file` button

---

I'll respond here once you've completed those steps!

📖 [Learn Go programming](https://tour.golang.org/welcome/1)
