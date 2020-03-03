# Questions

**With a partner**, answer these questions as completely as possible. Feel free to look at past lecture notes, the web, anything. 

Take the time to explain it to each other. 

The power of this exercise is in the act of _formulating_ and _explaining_ the concepts to someone else (your teammate).

## One

Run the app. Write out the steps, the _pseudo code_, required to create this app. It doesn't have to be totally accurate, or in the right order.

Only move on to the next question when you have enough detail that you would be able to start coding it yourself.

```
// Answer here

```

## Two - `server.js`

Take a look at the `server.js` file.

We have a new module in there, `body-parser` that is required on line `4`. What is it for? What is its use-case? What other lines are related to this module?

_The NPM site might be a good place to start. Feel free to provide links as relevant._

```
// Answer here
const bodyParser = require('body-parser'); 

we need to parse it to convert to readable data  so on the top we add app.use(express.json()); were adding json middleware. (WE  are READING THIS FROM REQUEST BODY)

1 - express.json() is calling the middleware
2 - the we are calling it in our request =>  .use(bodyParser.json())





```

## Three - `server.js`

Look at lines `23` and `24`. Explain the methods used. How are they different? What are the usecases for each?

```
// Answer here

they 
.get ==> we use use to get all the data requested and show them.** GET CARRIES the request parameter appended in the URL!!
.post ==> we use this type of requests to create. We post to an existing collection of books for example . req.body for post requests
*****IMPT****
post carries the request parameter in the message body which makes it more secure wat if transferring data (that why we need to parse it after we get !)

```

## Four - `server.js`

Line `6`. That's new. What do you think it's for?

```
// Answer here

its to say these specific functions from handlers.js 

module.exports = {
    handleFormData,
    handleHomePage,
    handle404,
};

..well  we need them here so we  ould call them in the server file. we did NOT in the handler.js assign it to a variable  such as module.export.log = etc

```

## Five - `handlers.js`

Explain line `1`. Where, why and how is `items` being used?

```
// Answer here

Strict mode keeps rules more tight.  In this case the whole file has strict mode to convertng mistake sometimes into real errors: 

-In strict mode you have to declare a variable with const,let or var you cant just do x = 4
- we cant use the  "delete" to delete a variable;
- ** Security advantages-ish In strict mode makes it easier to write secure JS. In browser its no longer possible to reference the window object and impossible to access the most recently called functions and the arguments used to run a function?


-items is an array of objects of what the user inputs in the body (?)
```

## Six - `handlers.js`

Why is there `redirect` on line `11`;

```
// Answer here

it is a response method that once it collected the user input it redirects  the user to the home page?

redirect to another URL (typically write smt to the database and redirect to another page)

``` 

## Seven - `handlers.js`

The `handle404` function is a more complex than we've seen thus far, what is the extra functionality for?

```
// Answer here
http://expressjs.com/en/5x/api.html#req.accepts

checks if the content is in html or json? Return true or false

```

## Eight - `ejs`

Take a look at `homepage.ejs` and `todoInput.ejs`. What is happening in there? Explain line-by-line...

```
// Answer here


todoInput.ejs

1- We inject the partial todoinput.ejs which is a form 
2- The form method specifies the HTTP method (could be post or get(default)) 
while the action says where to send the form data. In this case, werte are
sending it to /form-data which calls the handleFormData function and asigns item to the data (by using body methody on the req object) then we push it to an array.
also name = item.

3- for each object in the array we will loop  using for each and show it using ejs <%= item %>

4- we include as well the header and footer partial



```

## Nine - `styles.scss`

What are lines `2` to `7` for this file? Where are these values being used? Take a look at `_homepage.scss` as well? What do you notice?

```
// Answer here

they are variable that we assign. Its one of the pros in using scss/sass as we could
quickly re-use them throughout the styling process




```

## Ten - `_homepage.scss`

Line `16`. See if by searching the Sass documentation, you can determine what _exactly_ is going on here. That `#{}` notation very specific to this use-case. Why?

```
// Answer here
*** wow!

Native way for CSS to simple math 

https://css-tricks.com/a-couple-of-use-cases-for-calc/
```







