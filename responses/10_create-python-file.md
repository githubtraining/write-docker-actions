## Fetch a cat fact

**Cat Fact API**

We will be using the [cat-fact API](https://cat-fact.herokuapp.com/facts) for our action. This API does not require any authentication making it an ideal teaching tool.

When we make our request to this API we will get back an array JSON Objects in the response. An individual Object looks like this:

```json
{
  "_id": "58e008ad0aac31001185ed0c",
  "text": "The frequency of a domestic cat;s purr is the same at which muscles and bones repair themselves.",
  "type": "cat",
  "user": {
    "_id": "58e007480aac31001185ecef",
    "name": {
      "first": "Kasimir",
      "last": "Schulz"
    }
  },
  "upvotes": 6,
  "userUpvoted": "None"
}
```

It contains many **key:value** pairs of data that we can use in our own program or service. In our case, we are only interested in the `text` field.

Our action will extract the `text` field in a new array, then select a random index to display in the console as our random cat fact.

To further demonstrate the flexibility of Docker actions we will create this one using Python.

If Python is a new programming language to you, like always don't worry. You are here to learn about actions and we will supply all the necessary source code for you.

### :keyboard: Activity: Create the Python source code for the cat-fats action

1. Create and add the following contents to the `.github/actions/cat-facts/src/main.py` file:
   You can use [this link]({{quicklink}}) to easily create this file.

   ```python
   import requests
   import random
   import sys

   # Make an HTTP GET request to the cat-fact API
   cat_url = "https://cat-fact.herokuapp.com/facts"
   r = requests.get(cat_url)
   r_obj_list = r.json()

   # Create an empty list to store individual facts in
   # This will make it easy to select a random one later
   fact_list = []

   # Add the "text" of every object into the fact_list list
   for fact in r_obj_list:
       fact_list.append(fact["text"])

   # Select a random fact from the fact_list and return it
   # into a variable named random_fact so we can use it
   def select_random_fact(fact_arr):
       return fact_arr[random.randint(0, len(fact_list)-1)]

   random_fact = select_random_fact(fact_list)

   # Print the individual randomly returned cat-fact
   print(random_fact)

   # Set the fact-output of the action as the value of random_fact
   print(f"::set-output name=fact::{random_fact}")
   ```

1. Commit the changes to this branch:

📖 [Learn Python programming](https://www.learnpython.org/)

---

I'll respond when you push changes to this pull request.
