# Deploy-a-Serverless-Function-to-the-Cloud
To understand *serverless computing* by creating and deploying a simple *cloud function (FaaS)* that executes code automatically when triggered  without managing any servers.

   ⚙️ Step 1 — Open AWS Lambda

Go to https://aws.amazon.com/console

Sign in

On the top search bar, type Lambda

Click Lambda → then click Create function

Step 2 — Create Your Function

Now fill in these details:

Function name: helloWorldFunction

Runtime: choose Python 3.9 (or Node.js 18 if you prefer JavaScript)

Permissions:

If it asks for an execution role, select Create a new role with basic Lambda permissions
Then click Create function.

Step 3 — Add Your Code

Scroll down to the Code source section.

Option A (Python)

Replace everything in lambda_function.py with:

def lambda_handler(event, context):
    return {
        'statusCode': 200,
        'body': 'Hello from my first AWS Lambda function!'
    }

    Option B (Node.js)

Replace everything in index.mjs with:

exports.handler = async (event) => {
  const response = {
    statusCode: 200,
    body: 'Hello from my first AWS Lambda function!'
  };
  return response;
};


Click Deploy (top-right corner).

Step 4 — Add a Trigger (To Call It via a Link)

We’ll use API Gateway (it gives your function a public URL).

Scroll up → click Add trigger

Choose API Gateway

Under “Create a new API” → select HTTP API

Security → choose Open (so you can test it easily)

Click Add

✅ You’ll now see a URL under “API endpoint.”

Step 5 — Test the Function

Copy the link → open a new browser tab → paste it.

If you see:

Hello from my first AWS Lambda function!

🎉 Congratulations! You’ve just deployed your first serverless function to the cloud.
