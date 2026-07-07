### Serverless (AWS Lambda)

Now imagine a food delivery app.

You don't own a restaurant.

When someone orders food:

1. A chef appears.
2. Cooks the meal.
3. Delivers it.
4. Leaves.

If nobody orders food, **you pay nothing**.

This is **AWS Lambda**.

AWS handles:

- Servers
- Operating system
- Scaling
- Maintenance

You only upload your code.
## How Lambda Works

Suppose you write this Python function:

```
def greet():    
	print("Hello!")
```

Nothing happens until an **event** occurs.

Examples of events:

- A user uploads a photo.
- Someone clicks a button on a website.
- A file is added to storage.
- An API request is received.

When the event happens:

```
Event   
↓
AWS starts a server automatically   
↓
Runs your code   
↓
Returns the result   
↓
Stops the server
```

You never start or stop the server yourself.

---

## Why is it called "serverless"?

Because **from your perspective**, there are no servers to manage.

Instead of worrying about:

- Which server?
- How much RAM?
- Which operating system?
- How many CPUs?

You simply upload your code.

AWS takes care of everything else.

---

## Automatic Scaling

Suppose:

- 1 user visits your website.

AWS creates **1 Lambda execution**.

```
1 request   
↓
1 Lambda
```

Now imagine:

- 10,000 users visit at the same time.

AWS automatically runs thousands of Lambda executions in parallel.

```
10000 requests      
↓
Thousands of Lambda executions
```

You don't have to create more servers manually.

---

## Why is there a 15-minute limit?

A Lambda function is designed for **short-lived tasks**.

Examples:

- Resize an image (5 seconds)
- Send an email (2 seconds)
- Process a payment (1 second)
- Read data from a database (3 seconds)

If your code runs longer than **15 minutes**, AWS stops it.

For long-running jobs (such as video rendering that takes hours), you would typically use services like EC2 instead.