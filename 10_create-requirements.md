### Requirements.txt

Our `main.py` file imports a dependency that we need to go out and get. Some of you may be familiar with the Python package manager `pip`, which is what is going to do this for us.

`pip` allows us to create a special file named `requirements.txt` which contains a list of what our project needs to run.

---

### :keyboard: Activity: Creating the requirements.txt file

1. Create and add the following contents to the `.github/actions/cat-facts/requirements.txt` file:

```txt
 requests
```

1. Commit the changes to the `action-two` branch:

It may seem simple, but we only need to add the word `requests`, the other dependencies of our project do not need to be installed with `pip`

---

I'll respond in this pull request when you have completed these tasks.

📖 [Learn about pip](https://pip.pypa.io/en/stable/user_guide/)
