
Awesome 🎉

This action now has two of the three key files it needs to run:

- Source code
- Metadata

## Create the action's `Dockerfile`

Lastly we will create the `Dockerfile`. Like with Go programming, it is perfectly okay if you are not a Docker guru, we will provide the needed code snippets for your `Dockerfile`.

### :keyboard: Activity: Create a `Dockerfile` containing the Docker instructions

1. Create and add the following contents to the `.github/actions/hello-world/Dockerfile` file:
   You can use [this link]({{quicklink}}) to easily create this file in the proper location.

   ```dockerfile
   FROM golang:1.15
   WORKDIR /go/src/hello
   COPY . .
   RUN go get -d -v ./...
   RUN go install -v ./...
   CMD ["hello"]
   ```

2. Commit the changes to this branch
3. Click the green `Commit new file` button

📖 [Become a `Dockerfile` guru](https://docs.docker.com/engine/reference/builder/)

---

I'll respond when you push changes to this pull request.
