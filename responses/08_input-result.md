## Take a 👀 at what you made!

Great Job 👍 making those changes @{{user.login}}. I will take just a moment to walk you through what happened.

If you look at the screenshot below you will see a very similar output to what your results should show. If you'd like you can open your own [Actions tab]({{actionsUrl}}) to follow along.

![results from using input](https://user-images.githubusercontent.com/38021615/73969834-f50eb280-48d0-11ea-8a1e-3704d226a76e.png)

Your action now says hello to **Learning Lab User** which was the specified value for the `firstGreeting` input parameter which was added to the `my-workflow.yml` file.

What's interesting though, is that we also see **Mona the Octocat** and if you recall that is the value of the `secondGreeting` parameter in the `action.yml` file.

Why do we see the value of the `secondGreeting` 🤔

If you remember, we made the `secondGreeting` input parameter **required**. This means that even if it is not specified in `my-workflow.yml` it will be executed by the `main.js` code using whatever value was set as **default**. It cannot be ignored like our `thirdGreeting` was.

Circling back to the `fistGreeting` you may have noticed that you were able to overwrite the **default** value of `Hubot` by being explicit in the `my-workflow.yml` file.

Had you been explicit with `thirdGreeting` in the `my-workflow.yml` file then the `if` statement in the `main.go` file would have executed and you would have three inputs.
