### :keyboard: Activity: Create the final source code files

💡All of the following steps take place inside of the `.github/actions/issue-maker/src` directory.

1. Create and add the following contents to the `.github/actions/issue-maker/src/index.js` file:

   ```javascript
   const core = require("@actions/core");
   const github = require("@actions/github");

   async function run() {
     const issueTitle = core.getInput("issueTitle");
     const catFact = core.getInput("catFact");

     const token = core.getInput("repoToken");
     try {
       const octokit = new github.GitHub(token);

       const newIssue = await octokit.issues.create({
         repo: github.context.repo.repo,
         owner: github.context.repo.owner,
         title: issueTitle,
         body: catFact
       });
     } catch (error) {
       core.setFailed(error.message);
     }
   }

   run();
   ```

1. Commit the changes to the `action-three` branch.
1. Click the green `Commit new file` button

---

I will respond once you have finished.
