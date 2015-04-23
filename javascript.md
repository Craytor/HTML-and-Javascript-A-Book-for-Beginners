## Scripting
So we now know the basics of HTML and CSS, but these will only create basic results. It’s time to learn how to make project become dynamic and extraordinary! In this chapter, we will learn the differences between client-side and server-side scripting, learn Javascript, and also take a brief look at jQuery, a Javascript library. Each type of scripting, client-side or server-side scripting, has its own use case. For example, if you are wanting to make the user's browsing experience interactive, you would want to use client-side scripting - if you want to do tasks such as sending emails, server side scripting would be needed. If you want to make something interactive, you should go with client-side scripting, but if you need to access results and display them on a webpage, you should use server-side scripting. 

#### Client-side Scripting
Client-side scripting is just what the name implies, scripting on the client side. This type of scripting will occur directly on the web page, and you can incorporate it right into your HTML file. It is run from your local machine. You don’t have to own, have access to, or install a webserver. Instead, it’s just like you testing your HTML and CSS; and you can open it right in the browser. This is really good news for beginners as you will not have to worry about trying to install a web server on your computer, which can be a tricky task at times! Client-side scripting doesn’t have a way to directly store data in a database or fetch data, but you can achieve a way of doing this by writing an API (but this is beyond the scope of this book).

####Server-side Scripting
Unlike client-side scripting, server-side scripting is code that is executed and run on the server and not on the client. By using server-side scripting, you can open many more doors. You can do things you couldn’t do with client-side scripting such as accessing a database, making purchases, and much more. It is important to point out that all of this is done secrely. Server-side scripting does a lot of the processes a website may need to do in order to display content such as calculating certain things and retrieving results from a database. When you call the website, it's code will be executed and then will return a response. The code that is displaying these results cannot be edited by the vister, unlike Javascript.

## Getting Started
Alright, so now that we know what the differences are between client and server-side scripting, we can now begin to utilize the elements of client-side scripting. Again, we are choosing this route because we do not have access to a server where we could execute these scripts, and client-side scripting is all executed within the browser.

So with that being said, these are the main points we will cover with JavaScript:

* Logging Data
* Defining Variables
* Accessing Variables
* Displaying Variables (their content)
* Numerical Operations
	* Addition
    * Subtraction
    * Multiplication
    * Division
* Functions
* Objects
	* Properties
    * Methods
* Events

As you begin working through the JavaScript sections, please use a new document with just the following:
```
<html>
    <head>
    </head>
    <body> 
    </body>
</html>
```

#### Logging Data
When starting to develop in JavaScript, you need to be able to debug (find your errors) in your code. A good way to do this is to log data a JavaScript console. This is also a good way to tell how far your code is executing before you get an error (so that you can easily find out where it's going bad). 

All right, *now* we can get started... First within your `<head></head>` tags, add script tags which should look something like this:
```
<script>

</script>
```
Alright, sweet! We can now start putting content within these tags, and it will be executed! Luckily, it's not as hard as it may sound. In order to log data, we must untilize JavaScript's console object.

* If you are using Google Chrome, press the menu button on the top right of your browser, select more tools, and then select Javascript Console. (`Menu > More Tools > Javascript Console`)
* If you are using Mozilla Firefox, press the menu button on the top right of your browser, select Developer, and then select Browser Console. (`Menu > Developer > Browser Console`)
* If you are using Internet Explorer... There is no solution for you (kidding, but IE is a horrible browser), use either of the two browsers listed above.

By utilizing this object, we have access to four different logging methods, and they are `info, error, warn, log`. There are many more, but they will not be covered in the scope of this tutorial. So, now that we know these different methods, let's *actually* log `This page has been loaded...` in the console when the page is loaded. We can do this by calling the `console.log` method. It should look something like this:
> Note, this information should go within the `<script></script>` tags.
```
console.log('This page has been loaded...');
```

Alright, now let's go ahead and view this page in the browser and open up the console in your brower.
{<1>}![Console Log](/content/images/2015/04/console.PNG)

If you see a log that looks similar to this one, you're golden. Also, it is important to note that you can see the file and the line on which where the the code was executed, in this case the code executed on `line 12`, for you this may be different.

#### Defining Variables
Alright, now that we know how to log data in the console, we can now take a look at variables. Varibles are like barcodes at stores, you scan them at the register, magic happens in the backend, and then, whoohla, you know the name and the price of the product. Variables are like barcodes, you can set them equal to data such as strings or arrays. So how can we go about this you may be asking, and the answer is quite simple. First we need to declare a variable and set it equal to something, in this case we will set it equal to `Hello World!`. So let's take a look at what this may look like...
```
var hello = "Hello World!";
```
So what's going on? First `var` is declaring that what ever follows between it and the equals sign is going to be the variable. Also note the the name of your variable (`hello`) **may not contain spaces**! The equals sign `=` is what is binding your data to your variable, and finally `"Hello World!"` is what the data is.
> Note that the data has quotes around it, this is important if you are including words and or phrases. For numbers you don't need quotes.

Let's try setting a variable equal to a number as well...
```
var myNumber = 1;
```

Okay, now that we know how to declare the variables, how do we view the data? It's pretty simple, we can either log it in the console or insert into our web page. We are not at the point where we can insert the data in the web page (it's coming up later), so let's stick with logging via the console. So this is what it should look like:
```
console.log(hello);
console.log(myNumber);
```

Here is what the console should look like:
{<2>}![](/content/images/2015/04/2-1.PNG)
>Note that you should insert this into your `<script></script>` tags along with your variables (`var myNumber = 1;` and `var hello = "Hello World!";`).

#### Accessing Variables
So once you defined your variable, you need to be able to access it. Accessing a variable is pretty easy, and actually we just done this when we logged the contents of a variable to the console. So in order to log, or use the contents of the variable, you just use the variable name, it's just that simple!

#### Displaying Variables (their content)
Now, this is most likely the moment you have been waiting for! So just how do you display that variable on your webpage? Well let's take a look!

>This will require **both** HTML and JavaScript for your results to work as planned.

So by using JavaScript, we could select the whole page and replace it's content with what we specify, but that isn't fesable in a real-world application. Instead we will go ahead and get the content of a div, and replace the contents of it with what ever our variable is. Ready?

So, let's take a look at the body section of our site. Notice how we have an onload event attribute. All this means is once the body loads, it will then run the function in JavaScript. Don't know what a function is? That's fine... It's coming up!
```
<body onload="loaded()">
	<div id="content"></div>
</body>
```

Now within JavaScript, we can now select the `content` div and do our fancy stuff! Let's take a look... Notice how we have the loaded() function - all it does is holds content and can be called, and once called, the code is then exectued.We will learn more about functions later on.
```
function loaded() {
    var hello = "Hello world!";
    document.getElementById("content").innerHTML = hello;
}
```
Here's a look at what you may see on your page (i.e. dependign what you set your hello variable to).
{<3>}![](/content/images/2015/04/hello_world-.PNG)

Now, before we go any further, let's try one more thing!
Let's go back up into our loaded() function and take a look at that variable we set. Let's actually change the content of "Hello world" to somthing with **HTML**! Yes, we can even include HTML tags within the variable. Alright, so let's put "Hello world!" in a bold tag within a paragraph tag. This is what our variable should look like now:
```
var hello = "<p><b>Hello world!</b></p>";
```

By utilizing the document object we can use the getElementById function, and therefore can select the contents of the div and replace it all with the variable `hello`. Here's a look:
{<4>}![](/content/images/2015/04/Screenshot-2015-04-22-at-11-09-06-AM.png)

#### Numerical Operations & Variables
You can do many things with variables, the outcome is unlimited! Another thing that may come in handy is to add (numerical) variables together. Let's take a look:

###### Addition
Let's say that you have a $5.00 bill, $10.00 bill, $20.00 bill, and a $50.00 bill - how much money do you have in total? Let's go ahead and solve this:
```
var total = 5 + 10 + 20 + 50;
console.log(total);
```

{<5>}![](/content/images/2015/04/Screenshot-2015-04-22-at-11-12-56-AM.png)

###### Subtraction
So using the total from above, you go and buy yourself a meal at Sheetz. You buy a 3 piece chicken, a bucket of Fryz, and a large fountain soda - the total comes to $8.54. How much money do you have left?

```
var total = 130;  // get this from the problem before

var cost = 8.54;
var amount = total - cost;
console.log(amount);
```
Now, once you run this, you *should* see something similar to this:
{<6>}![](/content/images/2015/04/subtraction.PNG)

###### Multipication
So, what if you wanted to calculate the area of a rectangle - maybe this is the banner on your website. Well - we can do that! Let's say that dimensions of the banner are `900px x 300px`, we can do the following: 

```
var width = 900;
var height = 300;

var area = width * height;
console.log(area + " square pixles");
```

Alright, once you run this, take a look in the console... We should see something like this:
{<7>}![](/content/images/2015/04/multiplication-1.PNG)


###### Division
Multiplication's pretty cool, 'ey? So let's do something even *cooler*! Let's divide, but don't worry, you don't have to be an expert in math to get this one down. So, for this example, let's use another math problem. 
> This problem is a little bit more advanced. A simple way of division is `var1/var2`.
```
Suppose a flagpole's shadow is 25 feet long, and a person is standing next to it. The person is 5 feet high, and casts a 3 foot shadow. How high is the flagpole?
```
Alright, so let's consult this as if it was a math problem. We are going to have to make two porportions. One proportion is `x/25` (for the flagpole) while the other proportion is going to be  `5/3`. Now in math we would cross multiply and set each side equal to one another - so let's do that.

```
// note these are the sides of the equation after cross multiplication...

var flagpole = 125;
var person = 3; // it's suppose to be 3x, let's remove the x, JavaScript isn't that smart

var flagpole_height = flagpole / person;
console.log('x = ' + flagpole_height + ' feet');
```
Again, we should get some groovy response similar to this:
{<8>}![](/content/images/2015/04/division.PNG)

#### Functions
Coming soon...

#### Objects
Coming soon...
###### Properties
Coming soon...
###### Methods
Coming soon...

#### Events
Coming soon...
#### Copyright Notice
This content is subject to change. All content is copyright Tyler Youschak, you may not reuse, redistribute, or recreate, in any way, shape, or form, oral, written, etc.


Last Updated: 04/23/15 9:17 AM