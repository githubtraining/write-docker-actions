## Fetch a cat fact

**Cat Fact API**

We will be using the [Cat Facts API](https://catfact.ninja/facts) for our action. This API does not require any authentication making it an ideal teaching tool.

When we make our request to this API we will get back a JSON Object in the response. An outline of the Object will looks like this:

```json
{
  "current_page": 1,
  "data": [
    {
      "fact": "The Egyptian Mau is probably the oldest breed of cat. In fact, the breed is so ancient that its name is the Egyptian word for “cat.”",
      "length": 132
    }
  ],
  "first_page_url": "https://catfact.ninja/facts?page=1",
  "from": 1,
  "last_page": 332,
  "last_page_url": "https://catfact.ninja/facts?page=332",
  "next_page_url": "https://catfact.ninja/facts?page=2",
  "path": "https://catfact.ninja/facts",
  "per_page": 1,
  "prev_page_url": null,
  "to": 1,
  "total": 332
}
```

It contains an Object of data that we can use in our own program or service. In our case, we are only interested in the `fact` field.

Our action will extract the `fact` field in a new array, then select a random index to display in the console as our random cat fact.

To further demonstrate the flexibility of Docker actions we will create this one using Python.

If Python is a new programming language to you, like always don't worry. You are here to learn about actions and we will supply all the necessary source code for you.

To get more results from the Cat Fact API we will append the `limit` query parameter to the end of the endpoint.

### :keyboard: Activity: Create the Python source code for the cat-fats action

1. Create and add the following contents to the `.github/actions/cat-facts/src/main.py` file:
   You can use [this link]({{quicklink}}) to easily create this file.

   ```python
   import requests
   import random
   import sys

   # Make an HTTP GET request to the Cat Fact API
   cat_url = "https://catfact.ninja/facts?limit=50"
   r = requests.get(cat_url)
   r_obj_list = r.json()

   # Create an empty list to store individual facts in
   # This will make it easy to select a random one later
   fact_list = []

   # We loop through the "data" key in our r_obj_list list and
   # add the "fact" of every object into the fact_list list
   for fact in r_obj_list["data"]:
       fact_list.append(fact["fact"])

   # Select a random fact from the fact_list and return it
   # into a variable named random_fact so we can use it
   def select_random_fact(fact_arr):
       return fact_arr[random.randint(0, len(fact_list)+1)]

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
