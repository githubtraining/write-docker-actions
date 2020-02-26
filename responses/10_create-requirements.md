### :keyboard: Activity: Create the requirements.txt

💡All of the following steps take place inside of the `.github/actions/cat-facts` directory.

A `requirements.txt` file is required so that the Python package manger, PIP, knows which dependancies to install when our Docker image get's built. In our case we will only need to add the `requests` package to our `requirements.txt`

1. Create and add the following contents to the `.github/actions/cat-facts/requirements.txt` file:
   You can use [this link]({{quicklink}}) to easily create this file.

   ```text
   requests
   ```

1. Commit the changes to the branch named `action-two`

---

📖[Master PIP](https://www.pythonforbeginners.com/pip/)
