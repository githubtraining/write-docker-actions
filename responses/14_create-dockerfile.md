## Add the issue-maker action's `Dockerfile`

### :keyboard: Activity: Create `Dockerfile` for issue-maker

One more piece to add and that is this actions `Dockerfile`. Once you complete this you will have all the pieces in place to use your final action!

1. Create and add the following contents to `.github/actions/issue-maker/Dockerfile`:
   You can use [this link]({{quicklink}}) to easily create this file.

   ```dockerfile
   FROM node:slim

   COPY package*.json ./

   RUN npm install

   COPY . .

   CMD [ "node", "/src/index.js" ]
   ```

2. Commit the changes to this branch
3. Click the green `Commit new file` button

📖 [Become a `Dockerfile` guru](https://docs.docker.com/engine/reference/builder/)

---

I'll respond when you push changes to this pull request.