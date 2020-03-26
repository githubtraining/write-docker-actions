## {{user.login}} it's time to get ready for the third action: issue-maker 🎉

As with the other actions we wrote, we are going to need to setup a few directories and files.

This time we will start with the dependencies for our action. JavaScript projects can be packaged with a `package.json` file which contains metadata and configuration information about a project. In our case we will use some pieces of the [actions toolkit](https://github.com/actions/toolkit).

### :keyboard: Activity: Add `package.json` to issue-maker

1. Create and add the following contents to the `.github/actions/issue-maker/package.json` file:
   You can use [this link]({{quicklink}}) to easily create this file.

   ```json
   {
     "name": "issue-maker",
     "version": "1.0.0",
     "description": "",
     "main": "index.js",
     "scripts": {
       "test": "echo \"Error: no test specified\" && exit 1"
     },
     "keywords": [],
     "author": "",
     "license": "ISC",
     "dependencies": {
       "@actions/core": "^1.2.2",
       "@actions/github": "^2.1.0"
     }
   }
   ```

1. Commit the changes to this branch.
1. Click the green `Commit new file` button

---

I will respond once you have finished.
