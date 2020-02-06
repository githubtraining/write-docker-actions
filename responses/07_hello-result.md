## Congratulations 🎉

Your very first Docker action has been written and executed within a workflow! You may be wondering how I know that and the truth is that GitHub Actions provide real-time logging of the events happening within the runner! Since our action prints to the console we can just expand that step in our workflow and look at the standard output that is on our screen.

You can do this in your own [Actions tab]({{actionsUrl}}) or you can settle for examining the screenshot below to see our **Hello World** statement in place of where our previous errors existed.

![hello world success](https://user-images.githubusercontent.com/38021615/73961700-f71d4500-48c1-11ea-9304-b0d9abe99044.png)

---

Whoa, that's a lot of output for a simple hello world! Don't let this alarm you, the output you see is from the `Docker build` operation that packages up your files into a Docker image.

📖 Learn about [Docker build](https://docs.docker.com/engine/reference/commandline/build/)
