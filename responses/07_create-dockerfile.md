### :keyboard: Activity: Hello World

Awesome 🎉

This action now has two of the three key files it needs to run:

- Source-code
- Metadata

Lastly we will create the `Dockerfile`. Like Go programming, it is perfectly okay if you are not a docker guru, we will provide the needed code snippets for your `Dockerfile`.

1. Create and add the following contents to the `.github/actions/hello-world/Dockerfile` file:
   You can use [this link]({{quicklink}}) to easily create this file in the proper location.

   ```dockerfile
    FROM golang:latest
    WORKDIR /go/src/hello
    COPY . .
    RUN go get -d -v ./...
    RUN go install -v ./...
    CMD ["hello"]
   ```

2. Commit the changes to the existing `hello-world` branch
3. Click the green `Commit new file` button

---

I'll respond here once you've completed those steps!

📖 [Become a Dockerfile guru](https://docs.docker.com/engine/reference/builder/)
