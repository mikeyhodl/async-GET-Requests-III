# async-GET-Requests-III

In the previous exercise, we created the boilerplate code for making a GET request using async and await.

In this exercise, you’re going to build on previously created boilerplate code to get nouns that describe the inputted word from the Datamuse API:

Datamuse API Documentation.
Instructions
1.
Under the comment “AJAX function”, create a new arrow function called getSuggestions() using the async keyword.

You’ll be coding inside the arrow function of const getSuggestions for the remainder of this exercise.


Hint
The syntax would look like:

const getSuggestions = async () => {}
2.
Inside the code block of the async arrow function, create a const variable named wordQuery and assign it inputField.value.

3.
Create another const called endpoint, assign it value of a string that is url, queryParams, and wordQuery concatenated in that order.


Hint
Make sure you’re still in the code block of getSuggestions(). You have a couple of ways to concatenate a string:

const word1 = ‘hello’;
const word2 = ‘world!’;
 
console.log(word1 + ' ' + word2);
// ‘hello world!’
You can also interpolate it using a template literal, but remember to use backticks!

console.log(`${word1} ${word2}`);
// ‘hello world!’
4.
Add a try statement with an empty code block. Outside the code block for try, add a catch(error) statement with a code block that logs error to the console.


Hint
The syntax will look something like:

try {
   // code goes here
} catch (error)  {
    console.log(error)
}
5.
Inside the try code block, using const, create a variable named response and assign it to await the result of calling fetch() with endpoint as the first argument. For this API to work within the provided browser, add {cache: 'no-cache'} as the second argument.


Hint
First create a variable named response using const:

const response
Then assign response to await the resolution of fetch(endpoint, {cache: 'no-cache'})

const response = await fetch(endpoint, {cache: 'no-cache'})
6.
Below the variable response from the previous step, create a conditional statement that the checks if the ok property of the response evaluates to a truthy value.

Inside the code block of the conditional statement, await response.json() and save it to a variable called jsonResponse using the const keyword.


Hint
Use an if statement to check the ok property of response. Then inside the statement, create a const jsonResponse and assign it to await the resolution of response.json().

The general syntax will look like:

if(variable.property){
  const someVariable = await variable.method()
}
7.
Call the function renderRawResponse() and pass in jsonResponse. Then, run the code.

In the response field, type in a word and click the submit button on the web page.

You should now see an array of objects that contain nouns that describe the word you typed in!

You can view the purpose of the renderRawResponse helper function at public/helperFunctions.js.


Hint
Make sure you’re still in the conditional statement, write your code under jsonResponse.

8.
Now that you can see the body of response, you should clean it up to display on the webpage.

Delete renderRawResponse(jsonResponse) and replace it with renderResponse(jsonResponse). Run the code. Then type in another word and click the submit button.

Great, now you have an organized list of words and you finished your GET request!

You can view the purpose of renderResponse function at public/helperFunctions.js.
