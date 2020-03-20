### :keyboard: Activity: Create cat fact `Dockerfile`

Awesome 🎉

This action now has three of the four key files it needs to run:

- Source-code
- Metadata
- Requirements.txt

Lastly we will create the `Dockerfile`, just like we did with our first action.

1. Create and add the following contents to the `.github/actions/cat-facts/Dockerfile` file:
   You can use [this link]({{quicklink}}) to easily create this file.

   ```dockerfile
   FROM python:3

   COPY requirements.txt ./

   RUN pip install --no-cache-dir -r requirements.txt

   COPY . .

   CMD [ "python", "/src/main.py" ]
   ```

2. Commit the changes to the existing `action-two` branch
3. Click the green `Commit new file` button

---

I'll respond here once you've completed those steps!

📖 [Become a `Dockerfile` guru](https://docs.docker.com/engine/reference/builder/)
