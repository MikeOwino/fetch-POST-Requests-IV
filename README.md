# fetch-POST-Requests-IV

In the previous exercise you’ve positioned yourself to make the POST request by providing the endpoint and the object containing all the necessary information. In this exercise you’ll handle the response.

The request returns a Promise which will either be resolved or rejected. If the promise resolves, you can use that information and the ok status. Let’s implement that knowledge into your code!

If you reset the exercise at any point, you will have to paste in your API key again at the top!

Instructions
1.
Chain a .then() method to the end of the fetch() function you wrote in the previous exercise. As its first argument, pass it an arrow function as a callback that takes response as its single parameter.

Checkpoint 2 Passed

Hint
The syntax for chaining a .then() will look something like:

fetch(url, {
  property: value, 
  property: value
}).then(parameter => {});
2.
Inside the block of the function you made in Step 1, use a conditional statement to check the value of the ok property of response. If it evaluates to a truthy value, call renderJsonResponse() and pass in response.

Run the code.

Now, if you post a URL, you should see the object that was sent back!

renderJsonResponse() is a helper function found in public/helperFunctions.js.

Checkpoint 3 Passed
3.
Great, now that you see the raw object, you will need to pass the JSON to the next .then(). Delete renderJsonResponse(response) and replace it with return response.json()

Checkpoint 4 Passed
4.
Below the curly braces of the conditional statement, throw a new Error in case response.ok is falsy.

The message the error should raise is ‘Request failed!’.

Checkpoint 5 Passed

Hint
The syntax to raise throw a new Error and include ‘Request failed!’ as a message is below:

throw new Error('Request failed!');
5.
Outside of the code block from the first callback function you wrote, add another arrow callback function that takes networkError as a single parameter.

console.log() the networkError.message inside of the callback function you just wrote.

By adding this second callback, you’re safeguarding yourself in the rare event that the network returns an error!

Checkpoint 6 Passed

Hint
The syntax will look like:

fetch(/* previous code*/).then((response) => {
  // Previous code
},(networkError) => {
  // code goes here
});
