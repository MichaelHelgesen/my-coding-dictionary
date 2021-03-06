**Set** The Set object lets you store unique values of any type, whether primitive values or object references.

        const set1 = new Set([1, 2, 3, 4, 5]);

        console.log(set1.has(1));
        // expected output: true

**Concat:** JavaScript offers the concat method for both strings and arrays that work in the same way. For arrays, the method is called on one, then another array is provided as the argument to concat, which is added to the end of the first array. It returns a new array and does not mutate either of the original arrays. Concat offers a way to add new items to the end of an array without any mutating side effects.

**Functional programming:** One of the core principle of functional programming is to not change things. Changes lead to bugs. It's easier to prevent bugs knowing that your functions don't change anything, including the function arguments or any global variable. A function, ideally, should be a pure function, meaning that it does not cause any side effects.

Another principle of functional programming is to always declare your dependencies explicitly. This means if a function depends on a variable or object being present, then pass that variable or object directly into the function as an argument.

There are several good consequences from this principle. The function is easier to test, you know exactly what input it takes, and it won't depend on anything else in your program.

This can give you more confidence when you alter, remove, or add new code. You would know what you can or cannot change and you can see where the potential traps are.

Finally, the function would always produce the same output for the same set of inputs, no matter what part of the code executes it.

**Mutation:**  In functional programming, changing or altering things is called mutation, and the outcome is called a side effect. A function, ideally, should be a pure function, meaning that it does not cause any side effects.

**Lambda:** When the functions are passed in to another function or returned from another function, then those functions which gets passed in or returned can be called a lambda.

**Higher order functions:** The functions that take a function as an argument, or return a function as a return value are called higher order functions. (fCC)

**first class functions:** Functions that can be assigned to a variable, passed into another function, or returned from another function just like any other normal value, are called first class functions. In JavaScript, all functions are first class functions. (fCC)

**Immediately Invoked Function Expression (IIFE):** A common pattern in JavaScript is to execute a function as soon as it is declared:

        (function () {
        console.log("Chirp, chirp!");
        })(); // this is an anonymous function expression that executes right away
        // Outputs "Chirp, chirp!" immediately

Note that the function has no name and is not stored in a variable. The two parentheses () at the end of the function expression cause it to be immediately executed or invoked. This pattern is known as an immediately invoked function expression or IIFE.

An immediately invoked function expression (IIFE) is often used to group related functionality into a single object or module.

**Mixin** A mixin allows other objects to use a collection of functions.

        let flyMixin = function(obj) {
        obj.fly = function() {
            console.log("Flying, wooosh!");
        }
        };

        let bird = {
        name: "Donald",
        numLegs: 2
        };

        let plane = {
        model: "777",
        numPassengers: 524
        };

        flyMixin(bird);
        flyMixin(plane);

**.filter()** The filter() method creates a new array with all elements that pass the test implemented by the provided function.
arr.filter(callback[, thisArg])
Required | arr | Array being filtered
Required | callback | Function with 3 arguments (element, index, array)
Optional | thisArg | Value of this while executing callback

**charAt(number)** Returns a new string consisting of the charatcter located at the number given.

**Return** Breaks a chain.

**arr.reverse() (array)**
A method to reverse the objects in a string.

**arr.join() (array)**
A method to join objects in an array back to a string.

**Object.keys()**
We can generate an array of all the keys in an object by using Object.keys(object). We pass inn the object as argument. It will be no specific order to the array with keys.

**for...in / for in**
Used to iterate through all keys in an object.

    for (let user in object) {
    console.log(user);
    };

We define a variable which resets in each iteration. Example above prints each user in the object "object".

**Deugging**
- console.clear() to clear the console.

- typeof to check the data structure, type or variable.

        console.log(typeof "")

**Regular Expression** Regular Expressions are used in programming to match parts of a string. There are multiple ways to use regexes. 

- .test(): Takes a regex, applies it to a string and returnes true/false. It must be a litteral match. 

        let testStr = "freeCodeCamp";
        let testRegex = /Code/;
        testRegex.test(testStr);
        // Returns true

- Match literal string with different possibilities with the alternation or OR operator (|): /fish|dog|cat/

- Ignore case while matching: We use whats called a flag, in this case, the i flag. /ignorecase/i

- Extract matches: Extract the actual matches with .match() method. Apply the method on a string and pass in the regex inside the parantheses.

        "Hello, World!".match(/Hello/);
        // Returns ["Hello"]
        let ourStr = "Regular expressions";
        let ourRegex = /expressions/;
        ourStr.match(ourRegex);
        // Returns ["expressions"]

- Find more than one match: To search for or extract a pattern more than once, we use the g flag. For big and smal letters we use the i flag.

        let twinkleStar = "Twinkle, twinkle, little star";
        let starRegex = /Twinkle/gi; // Change this line
        let result = twinkleStar.match(starRegex); // Change this line

- Match anything with wildcard period (.): It will match any one character. /hu./ to find hug or hum. 

- Match single character with multiple possibiliies: Using character classes ([]). 

        let bigStr = "big";
        let bgRegex = /b[aiu]g/;
        bigStr.match(bgRegex); // Returns ["big"]

- Match a range of characters from the alphabet: Inside a character set we can define a range of characters to match. We use a hyphen for this purpose: [a-e].

- Match numers and letters of the alphabet: [a-z0-9].

- Matching single characters not specified: Called negated character sets. We place a caret charater (^) after the opening bracket and before the characters we do not want to match. [^aeiou].

- Match characters that occur one or more times: It occures at least once and may be repeated in a row. We then use the pluss sign (+). /a+/g would find one match in "abc" and return [a]. It would find two matches in "aabc" and return [aa]. "abab" would return [a, a] because they are not in a row. 

- Match characters that occur zero or more times: How we do this is by using the asterisk (*). /go*/

- Find characters with lazy matching: A greedy match finds the longest possible part of a string that fits the regex pattern and returns it as a match /t[a-z]*i/ finds "titani".
The alternative is called a lazy match, which finds the smallest possible part of the string that satisfies the regex pattern. /t[a-z]*?i/ By inserting a questionmark we turn it to a lazy match and it returns "ti".

- Match beginning string patterns: A caret (^) outside of brackets are used to search for patterns at the beginning of strings. /^Ricky/

- Match ending sting patterns: To search the end of a string, we use ($). /story$/

- Match all letters and numbers: Searching for all letters in the alphabet and all numbers is so common that it has a shortcut: \w this is equal to [A-Za-z0-9_] It includes Upper and lowercase plus numbers and (_) as well. /\w+/ Also known as shorthand character classes.

- Match everything BUT numbers and letters: To find the opposite \w, we use \W! This is the same as [^A-Za-z0-9_].

- Match all numbers: This shortcut is \d. This is equal to the character class [0-9].

- Match all non numbers: \D is a shortut for [^0-9].

- Match whitespace: We search for whitespace using \s. It also matches carriage return, tab, form feed and new line character. Think of it as similar to the character class [\r\t\f\n\v]. 

- Match non-whitespace characters: We use \S. It is similar to the character class [^ \r\t\f\n\v].

- Specify upper and lower number of matches: We specify the lower and upper number of patterns with quantity specifiers. Used with curly brackets, with two numbers. {2,4}. /a{3,5}h/.

- Specify only the lower number of matches: To specify the lower number we use the curly brackets with just one number and comma {3,}.

- Specify Exact number of matches: To do this we use curly brackets with one number and no comma {3}.

- Check for all or none: Sometimes what we search for may or may not exist. We can check for the possibility of existence of an element with a question mark (?). This checks for zero or one of the preceding element. Think of it like saying that the previous element is optional. 

        let american = "color";
        let british = "colour";
        let rainbowRegex= /colou?r/;
        rainbowRegex.test(american); // Returns true
        rainbowRegex.test(british); // Returns true

- Positive and negative lookahead: Look-ahead in you string to check for patterns further along. There are positive and negative lookaheads. A positive lookahead will make sure the pattern is there, but wont actually match it. It is used as (?=...) where ... is the required part that is not matched.
A negative lookahead (?!...) will look to make sure the pattern (...) in not there. 

        let quit = "qu";
        let noquit = "qt";
        let quRegex= /q(?=u)/;
        let qRegex = /q(?!u)/;
        quit.match(quRegex); // Returns ["q"]
        noquit.match(qRegex); // Returns ["q"]

        let password = "abc123";
        let checkPass = /(?=\w{3,6})(?=\D*\d)/;
        checkPass.test(password); // Returns true

- Reuse patterns using capture groups: Usefull for searching for patters that occurs multiple times in a string. We can search for repeat substrings using capture groups. We put the regex of the pattern that will repeat between parentheses (regex). To specify where this repeat string will appear, we use backslash (\) and then a number. The number starts at 1 and increases with each additional group we use. Example \1 to match first group. Below we see an example of matching a word occuring twice separated by space (using .match will return an array with the string it matches, along with its capture group): 

        let repeatStr = "regex regex";
        let repeatRegex = /(\w+)\s\1/;
        repeatRegex.test(repeatStr); // Returns true
        repeatStr.match(repeatRegex); // Returns ["regex regex", "regex"]

- Use capture groups for search and replace. We search and replace using .replace() on a string. The inputs for .replace() is first the regex pattern we want to search for. The second parameter is the string we want to replace or a function to do something. 

        let wrongText = "The sky is silver.";
        let silverRegex = /silver/;
        wrongText.replace(silverRegex, "blue");
        // Returns "The sky is blue."

        we can also access capture groups in the replacement string with dollar signs ($)

        "Code Camp".replace(/(\w+)\s(\w+)/, '$2 $1');
        // Returns "Camp Code"

- Replace whitespace from start to end: 

**Export/export default**

**Import/import***

**getters/setters**

**Destructuring assignment** is special syntax for neatly assigning values taken directly from an object to variables.

**The rest operator** Opposite the spread operator. The rest operator collects multiple elemenets and condenses them into a single array element. Since it is an array, we can use array methodes. 

    const sum = (function() {
    "use strict";
    return function sum(...args) {
        return args.reduce((a, b) => a + b, 0);
    };
    })();
    console.log(sum(1, 2, 3)); // 6

Think of the "...args" above as an array. 

**The spread operator** The spread operator (...) spreads or expands an array to its elements. You use it to add the elements of an existing array into a new array, pass elements of an array as arguments to a function, copy arrays and concatenate arrays. We can combine arrays or insert all of the elements of one array into another, at any index.

The spread operator only works in-place, like in an argument to a function or in an array literal. 

**new Time** Lets us retrieve the time. 

    let time = new Date();

By default Javascript will use the browsers time zone and display a date as a full text string. 

It's 4 ways to create a new date object: 

    new Date()
    new Date(year, month, day, hours, minutes, seconds, milliseconds)
    new Date(milliseconds)
    new Date(date string)

* new Date() creates a new object with the current date and time.
* new Date(year, month, ...) creates a new object with a specified date and time.
* new Date(dateString) creates a new date object from a date string.
* new Date(milliseconds) creates a new date object as zero time plus milliseconds.

**HTMLOptionsCollection:** Lets us traverse a list of options in a selector as well as optionally altering its items. Usefull if you need to target one of the options or retrieve some information from one.

    var x = document.getElementById("program-selector").selectedIndex;
    var y = document.getElementById("program-selector").options;
    alert("Index: " + y[x].index + " is " + y[x].className);

**classlist():** With classlist() we can manipulate class on a DOM element. It contains different methods like add, remove, toggle, contains. 

**BEM (Block, element, modifier):** BEM is a naming convention for CSS. 

* Block: house
* Element: house__kitchen
* Modifier: house--condo

A block is a high level construct like header or content. A block of content. 

Element is a piece of a block. So the name is the block name, followed by two underscores and the element name.

Modifier indicates a different version of the an element.

**Async/Await:** Is the combination of two tools, the async function and the await operator. When used together, we get a new way to structure our promises, that makes the code a whole lot easier to work with. The await operator can only be used with async functions.

When creating a new function, we can choose to create a function as an async function:

    const processData = async () => {
        return 12
    }

When calling an async function, we ALWAYS get a Promise. The Promise is resolved with the value that we return from the function:

    Promise { 12 }

We can use .then on the async function:

    processData().then((data) => {
        console.log('Data', data)
    })

With await we can get our Promises to look like synchronous code. It resolves one after the other. We don't have to use .then and it's a cleaner form of chaining.

Await also throws our error for us, if the Promise is rejected.

    const processData = async () => {
        let data = await getDataPromise(2) // 2 * 2
        data = await getDataPromise(data) // 4 * 2 Will only resolve if Promise above was not rejected.
        data = await getDataPromise(data) // 8 * 2 Will only resolve if Promise above was not rejected.
        return data // 16. Will only resolve if no Promise was rejected

        /* getDataPromise(2).then((data) => {
            console.log(data) // 4
        }) */
    }



**Fetch API:** An alternative to XMLHttpRequest with Promises built in when doing HTTP requests. 

It takes two arguments, the first one beeing the URL. What comes back from fetch() is actually a Promise.

In fetch we don't have to worry about ready state, since it returns a Promise. If we get the Promise, we know it's ready.  

**HTTP Request:** Hypertext Transfer Protocol is a request response protocol. It means that we, the developer, issue some sort of request. This goes of to some sort of third party server. That server does some work and gives us back a response: request <-> response.

The request describes what we, the person making the request, hope to do.

The response contains information about what was actually done.

**Callback hell:** Deeply nested callbacks that is difficult to read and to manage. Should be replaced with (Promise)chaining. If we want to do two asynchronous things, using data from the first to start the process for the second, callback fall short. 

**Promise chaining:** Very useful when we want to do two things in a row, both beeing Promise calls. We do this by returning the result of the Promise.

Best technique:

        getDataPromise(10).then((data) => {
            return getDataPromise(data)
        }).then((data) => { // Second chain
            return getDataPromise(data)
        }).then((data) => { // Third chain
            console.log(data)
        }).catch((err) => {
        console.log(err)
    })

Not good technique:

        getDataPromise(2).then((data) => {
            getDataPromise(data).then((data) => {
                console.log(`Promise data: ${data}`)
            }, (err) => {
                console.log(err)
            })
        }, (err) => {

        })




**Then:** A method that returns a Promise. It takes two arguments that are callback functions for the success and failure cases of the Promise.

**Promises:** Alternative to callback.

* Easier to read
* It's impossible to run more than one of the functions, and it's only going to run once.
* When using the .then method more than once, we don't call the Promise multiple time. We just use the data from the first time it was called.

Example:



    // Callback
    const getDataCallback = (callback) => {
        setTimeout(() => {
            callback('Time is error', undefined)
        }, 2000)
    }

    getDataCallback((err, data) => {
        if (err) {
            console.log(err)
        } else {
            console.log(data)
        }
    })
    
    // Promise

    const myPromise = new Promise((resolve, reject) => {
        setTimeout(() => {
            //resolve('This is the promise data')
            reject('Error method')
        }, 2000)
    }) 

    myPromise.then((data) => {
        console.log(data)
    }, (err) => {
        console.log(err)
    })

**Currying:** Currying refers to the process of transforming a single function that takes a lot of arguments to multiple functions that take a subset of those arguments. In other words, it restructures a function so it takes one argument, then returns another function that takes the next argument, and so on.

    // Uncurried version
    const createAdder = (a, b) => a + b

    // Curried version
    const createAdder = (a) => {
        return (b) => {
            return a + b
        }
    }

This is useful in your program if you can't supply all the arguments to a function at one time. You can save each function call into a variable, which will hold the returned function reference that takes the next argument when it's available. 

    const add10 = createAdder(10) // Define "a" in createAdder
    console.log(add10(20)) // Define "b" in createAdder

    const add100 = createAdder(100) // Define "a" in createAdder
    console.log(add100(-90)) Define "b" in createAdder

**Impartial:** partial application can be described as applying a few arguments to a function at a time and returning another function that is applied to more arguments.

        //Impartial function
        function impartial(x, y, z) {
        return x + y + z;
        }
        var partialFn = impartial.bind(this, 1, 2);
        partialFn(10); // Returns 13
 
**Closures:** In JavaScript, a function always has access to the context in which it was created. This is called closure. 

A closure is the combination of a function with the lexical scope in which it was defined

So for example in a HTTP request: even though a request takes longer, the inner functions has access to the lexical scope in which they were defined. 

    const myFunction = () => {
        const message = 'This is my message'
        const printMessage = () => { // Has access to message variable even after myFunction runs.
            console.log(message)
        }
        return printMessage
    }

    const myPrintMessage = myFunction()
    myPrintMessage()

* In Objects: The simplest way to make properties private is by creating a variable within the constructor function. This changes the scope of that variable to be within the constructor function versus available globally. This way, the property can only be accessed and changed by methods also within the constructor function.

        function Bird() {
        let hatchedEgg = 10; // private property

        this.getHatchedEggCount = function() { // publicly available method that a bird object can use
            return hatchedEgg;
        };
        }
        let ducky = new Bird();
        ducky.getHatchedEggCount(); // returns 10

**Asynchronous vs Synchronous execution (blocking/ non blocking):** When we execute something synchronously, we start some sort of task and then we have to wait for it to finish, before we move on. This can cause the entire browser to lock up it for example a http request takes to long.

When we execute something asynchronously, we start some sort of task, then we can actually get other work done before that task is complete. This makes the code faster and does not freeze the user interface. 

**Getters and setters:** 

**super:**

**Creating subclasses (class syntax):** Makes it possible to create a subclass that inherits all the methods from an already created class.

**Class syntax:** A different way to define things with object constructors. More organized and easier to read.

**fromCharCode:** A string method to get the actual letter from a key press. 

**keypressed / charCode:** Short for character code, and allows us to detect which character was pressed.

**Literal syntax:** The syntax of the language allows us to define a value of a specific type, using a series of characters.

    {
        name: 'Michael'
    }

The language sees the opening and closing braces and the key value pair inside and defines it as an object.

**Object.prototype:** This is where methods like filter, split and hasOwnProperty lives. At the top of the prototype chain. 

When we create objects, they are all instances of the object protoype, and as such, gets access to all the object prototypes methods. 

We can override the methods (not recommended).

We can define own methods on object.prototype.

**hasOwnProperty:** We can check if an object has a property by providing that property name as an argument. If the property exists it returns true, if not it returns false.

    const product = {
        name: 'Influence'
    }

    console.log(product.hasOwnProperty('name'))

But what happens if we put in .hasOwnProperty as an argument? It returns "false". How? We know it is a property. Lets see what the documentation says: 

    Object.prototype.hasOwnProperty()

We see "object.prototype..." that means that these are shared methods, like filter, split, and hasOwnProperty. When using these methods we go up the property chain till we find them on the object prototype.

But hasOwnProperty doesn't go up the chain. So when we run this: 

    console.log(product.hasOwnProperty('hasOwnProperty'))

It only checkes to se if something exists on that specific thing (product). Since hasOwnProperty is on the Object.prototype, the result is "false".

**Primitive values:** A value that does not have properties. A non object. There is five types:

* String
* Boolean
* Number
* Null
* Undefined

Everything not in this list is an object.

**Split (string):** A method avaliable on strings. Returns an array. Takes one argument, that is a string. 

**Prototypal inheritance (object oriented programming / prototype property / prototype chain):** Protoypal inheritance is a form of inheritance. 

    // Object: myObject --> Object.prototype --> null
    // Array: myArray --> Array.prototype --> Object.prototype --> null
    // Function: myFunc --> Function.prototype --> Object.prototype --> null
    // String: myString --> String.prototype --> Object.prototype --> null
    // Number: myNumber --> Number.prototype --> Object.prototype --> null
    // Boolean: myBoolean --> Boolean.prototype --> Object.prototype --> null


    Person.prototype.getBio = function () {
        return `${this.firstName} is ${this.age}`
    }

By setting up methods on the constructor functions prototype property, all instances of that object get access to it.

How does it work? Say that we have this code: 

    const me = new Person('Mikke', 'Helgesen', '38')
    // me.[[Prototype]] = Person.prototype

The me.prototype gets equal to the constructor functions prototype. If we try to access first name, it finds it in the instance, because we as the developer defined it here:

    console.log(me.firstName)

But if we try to access a prototype that is not in in the instance:

    const bio = me.getBio()
    console.log (bio)

What happens is that it finds a prototype property that links to the shared set of methods on the constructor function. So we move up the prototype chain to get the method. If it's not there either, it's undefined. So it first looks in the instance, then moves up the chain untill it finds it or gets undefined.

But how come we can access methods on primitives like string, number and booleans? Thats because when we attach a method to them, they get converted to an object! They have an object wrapper.

**Object wrapper:** We can access methods on primitives like string, number and booleans. Thats because when we attach a method to them, they get converted to an object! They have an object wrapper.

**Object oriented programming:** Objects, as we know, is used to model real life things, like a car, a person, a todo list, a note taking list and so on. Object oriented programming is based on these objects and is focused on code reusability.

We can make a object template, and than use that to create as many instances of that object as we need. These instances share the object properties, but use them with their unique data. Methods are shared via prototypal inheritance (object prototypes).

With the "new" keyword, we create a new custom object type, based on the object defined after the "new" keyword. This is called a constructor function:

    const me = new Person() //constructor function

What happens is that JavaScript generates a new empty object for the new instance, then it gives us access to this object in the constructor function via the "this" value. By doing this, we are able to customize each instance.

    const Person = function (firstName) {
        this.firstName = firstName
    }

    const me = new Person('Mikke')

    console.log(me)

A constructor function ususally gets defined with a capital letter. It makes it easier to separate and to know that it needs to be called with a "new" keyword in front. 

**Strict mode:** A mode in JavaScript where the quirks are tweaked and it's not so easy to fall into weird language traps. This is a better mode making it harder to mess up. 

To set up:

    'use strict'

Strict helps us code better today, and also makes it future proof.

**Try / catch:** Can be used to prevent the whole program to stop when there is an error. A way to cover from errors gracefully: Doing something as opposed to just letting it explode.

Boilerplate: 

    try {

    } catch (e) {
        
    }

**Throwing an error (throw):** When we throw an error, it crashes our program. We can add a message and some context as to what the problem was. Nice for type checking.

    if (typeof amount === 'number') {
            return amount * .25
        } else {
            throw 'Argument must be a number'
        }

If we want more info, we can add the message into "Error()"

        if (typeof amount === 'number') {
            return amount * .25
        } else {
            throw Error('Argument must be a number')
        }


**Equality:** 

* Strict (===): Type in effect. Must be the same and same type.
* Loose (==): Takes type out, so 5 becomes the same as '5'. No need to use. 


**Type coercion:** JavaScript tries to convert data types if values are of different type. This is best avoided with strings and numbers.

    console.log('5' + 5) // 55
    console.log('5' - 5) // 0

Three types of coercions:
* String (avoid).
* Number (avoid).
* Boolean (OK: truthy / falsy).

True gets converted to 1, and false gets converted to 0:

    const value = true + 12
    const type = typeof value
    console.log(type)
    console.log(value)

**Truthy and falsy (not true and false):** All valuables in JavaScript is either truthy or falsy. So when evaluated in a boolean context, it ends up beein true or false. 

So if we take this: 

    const products = []
    const product = products[0]

    if (product !== undefined) {
        console.log('Product found')
    } else {
        console.log('Product not found')
    }

And replace the boolean in "if" with this: 

    if ('testing') {
        console.log('Product found')
    } else {
        console.log('Product not found')
    }

What happens? JavaScript will try it's best to convert the string (or anything else not boolean) into a boolean. This is where the truthy and falsy definitions come into play. In the example above, JS sees the string as true.

But it's actually easier to define whats falsy, and then know that everything else is truthy. 

Falsy values:
* null
* false
* '' (empty string)
* 0
* undefined
* NaN

Knowing this, it can be used to clean up code and refactor it. We can use them in our if conditions and ternary operators. 


**Conditional operator (ternary operator):** Allows us to use a bit of conditional logic without having to use the if statement. It's not a complete replacement though. But it is a nice little short hand for specific cases. 

    const myAge = 27
    let message

    message = myAge >= 18 ? 'You can vote' : 'You can not vote'

    // Same as above
    /* if(myAge >= 18) {
        message = 'You can vote'
    } else {
        message = 'You can not vote'
    } */

    console.log(message)

The code above can be shortened even more, by setting the conditional operator directly on the message variable

    const myAge = 27
    const message = myAge >= 18 ? 'You can vote' : 'You can not vote'

We start of by the condition. Then comes a questionmark, followed by the value if the condition passes. Next comes the colon, followed by the value if the condition is false.

We can also use functions in the ternery operator: 

    myAge >= 21 ? showPage() : showErrorPage()

**Arrow function:** They don't bind arguments, they don't bind "this" and they come with an advanced short hand syntax. 

An alternative way to create a function in JavaScript. It comes with a special syntax, making it great to use if we have simple one line functions. 

In arrow function, we start with the arguments list "()". Then comes the arrow "=>" followed by the function body wrapped in curly braces "{}".

    const squareLong = (num) => {
    return num * num;
    }

One of the differences between arrow functions and a regular functions is the short hand syntax. It's a different way to define the function body and can only be done with arrow functions. 

To use it, we first have to check if the function qualifies for it. If it's a simple function body with one line that just returns something, it's a great canditate. In this case, we can remove the curly braces and the return statement and just enter the expression.

    const square = (num) => num * num

Arguments only exist in regular functions. There is no "bound", no local variable, in arrow functions. So this code will fail: 

    const add = () => {
        return arguments[0] + arguments[1]
    } 

    console.log(add(11, 22, 33, 4))

Arguments also don't bind their "this" value, making them less usable as methods.

 

**Unix Epoch:** A specific point in time that is in the past:

* January 1st 1970 00:00:00
* We use a positive number to indicate time after unix epoch, and a negative number to indicate a time before 1970.
* Unix Epoch is represented by "0"
* One second from 0 = 1000 ms
* One minute in the past: -60000
* We use .getTime() to get the number.


**toString():** Returns a string representing the object.

**Date():** Gives us the current date. It includes a lot of methods. 

If not given an argument, it gives us the current point in time. But if we add some arguments, we can define when this "now" represents. 

    const date = new Date() // Current time.
    const date new Date('January 21 2001 6:25:01') // Set "now".
    const timeStamp = now.getTime() // Get timestamp. Ref. Unix Epoch. 

**new operator:** Create a new instance of a variable.

**Storage (event):** A special event that fires when any of the data in local storage changes.

You don't see the changes in the current tab (window) where you actually do the changes to local storage, only in the other ones we have open.

**Global event:**

**Window:** A global variable provided by the browser. It provides a lot of interesting things related to the browser window. It's a representation of it. It also contains all of the other browser globals. It contains a lot of properties like

* .innerWidth = width of browser window.
* .innerHeight = height of browser window.

"document" is a shorthand for "window.document".

We often attach events on window if we want a global event, meaning we can't or don't want to attach the event to any specific element, but the window as a whole.

**Substring:** A method to get part of a string.

* .substring(start, end) 

It takes two number arguments. The first is start, and the second (optional) is where you want it to end. Remember that it return the data between the numbers, so it does not include the ones we specify.

**Location** A global object provided by the browser. It contains different properties and the "assign" method. It functions much like the "href" in the anchor tag. It takes one argument, a string, which is a link.

* location.assign('link')
* .hash = Property that contains the hash portion of the URL.

**Debugger statement:** We put a debugger statement anywhere in the code where we want to pause the code to figure out what variable values equal.

Just type "debugger".

**Debugging:** The art of getting bugs out of your code.

**Global namespace:** Meaning that JavaScript data is avaliable globally, even though it's refactored into several files, and as long as all the files are loaded in and in correct order.

**Refactoring:** The concept of re-structuring your code without changing the external behaviour. The goal is not to create as few lines as possible, as that would only make it so complex it would be difficult to read and change. 

The goal is to make the code more reasonable, easier to comprehend, update, read and change.

**JSON (JavaScript Object Notation):** A global variable. It allows us to convert data into a string and vice versa.

Methods: 
* .stringify() = Takes in your data like object and array and returns a string. We pass the data we want to stringify as the argument.
* .parse() = Takes data converted to string, and converts it back to it's original form.

We use stringify just before we write our object. We use parse just after we read it.

**Local storage (global variable):** The ability to store data locally, so that we can fetch it later or not loose it when refreshing the page. In JavaScript it can perform the CRUD operations that make up data storage mechanism.

The global variable "localStorage" is provided by the browser, like "document". It can only store strings, and it contains several methods we can use, like:

* .setItem(key, value) = C in CRUD (create). Create data with local storage. Two arguments: key value pair.
* .getItem(key) = R in CRUD (read). Get an item stored in local storage. One argument, the key.
* U in CRUD = Updates the local storage, by using .setItem() described above. 
*  .removeItem(key) = D in CRUD (delete). Deletes an item in local storage. Takes one argument, the key.
* .clear() = Delete everything in local storage. Takes no arguments. 

**CRUD:** Stands for "create, read, update and delete". These four operations is what makes up the data storage mechanism.  

**Class (HTML):** An identifier that can be held by multiple elements in the HTML document. 

**Id (HTML):** A unique identifier that lets us target the element in the HTML document.

    <button id="remove-all">Remove all notes</button>

**Event handler / event listener / addEventListener** There are a lot of different events we can listen to on a web page. An event is something a user does, like click something, scroll or hover over something. 

An event listener is a function that runs when the user performes an event. We attach a event listener to an event.

    document.querySelector('button').addEventListener('click', functionName / function)

This method takes to arguments, a string describing the action, followed by the function name or function.

There is also an argument passed to the callback function, often refered to as "e" as in "event". It gives us access to a lot of information. This argument represents the event. It is useful when we want to do something with the element the event gets fired on.

    document.querySelector('button').addEventListener('click', function(e) {
    e.target.textContent = 'The button was clicked'
    })

Some event methods and properties
* .preventDefault() = When combined with 'submit' it stops the default browser behaviour of refreshing the page and clearing the form fields.
* .target = Used so that we can get access to the data in the object that the event fires on. So we can property chain with for example .textContent, .value or .elements if it's a form.
* .elements = Gives us access to all the fields in a form that the event fires on. Chained with name of field.
* .checked = A boolean to check if a checkbox is is checked or not. 

**Document object:** 
* .remove() = remove an element. Takes no argument.
* .textContent = get the text content of an HTML element, or set it.
* createElement('element') = Allows us to create a new element. We define the element in the paretheses.
* appendChild('elementToAppend') = Adds an item last in the defined element. The element is set in the parentheses.
             
      document.querySelector('body').appendChild(newParagraph)

* .setAttribute() = Define an elements attribute. For example change an input from the default "text" to "checkbox". Takes two arguments, type and attribute. 

**QuerySelector / querySelectorAll:** A method to search the document object for a given element. It gets called with a single argument, a string, where we define what we are looking for.

    document.querySelector('p')

What comes back is a representation of the element we defined as the argument.

The query only selects the first match. If you want to target all, we have to use 

    querySelectorAll('string')

This creates a node list of alle the matching elements. 

**Document:** The object provided to us by the browser so that we can manipulate the HTML content with JavaScript. It comes with a lot of information and methods we can use.

**DOM:** Stands for Document Object Model. The "document" in DOM is the HTML-document. The "object" is a javaScript object. So we have a JS object that models our HTML document.

So we use DOM when we want to do something with our HTML with JavaScript.

**Method chaining:** You can add methods on other methods, as long as they are of the correct data type. 

    note.title.toLocaleLowerCase().includes('gr')

**In place:**

**Sort array method .sort() (compare function):** Method that sorts the array in place. Don't need an argument, but can take one. Default sorting is alfabethical when used on strings.  

The argument can take a function, in which we can specify the sort order.

    arr.sort([compareFunction])

The .sorts function compares one item with another, deciding who comes before the other. Where other array methods' (like .forEach() and .indexOf()) functions gets called one time for each item, the .sort(item1, item2) function gets called with two individual items. 

If item1 should come first, we return -1. If item two should come first, we return 1. If they are the same, we return 0, saying we don't need to change the order.

Capitalization is important since capital A comes before a.

**Filtering arrays .filter():** Consept of taking an existing array and creating a new array with some of the items based of the filtering.

    notes.filter(function (note, index) {
    
    })

This is a callback function like .forEach() and .findIndex(). It takes a single argument which is a function. The callback function takes two arument, the individual item and the index. It returns a boolean like .findIndex() and .find(). 

So if the boolen is true, it should be kept in the new array we are generating. 

.filter() gives back a new array, it does not change the original array.

No matches would return an empty array.

**Searching for objects:** When comparing two objects, it doesn't matter if they have the same set of object properties and the same set of object property values. That doesn't make two objects equal. 

What makes two objects equal is if they are the exact same object in memory.

**for statement / for loop:** An alternative looping mechanism for "forEach". But the for loop doesn't require array data.

    for (let count = 0; count <= 2; count++) {
        // code
    }

We provide three things in the for loop parenthesis: the initializer (count), the second is the condition (when true and when false) and the third is the final expression. 

The initializer only runs once, in the first iteration. Then it moves to the condition: as long as the condition is true, the code in the code block runs. After the code has executed, the final expression runs. 

**Callback function:** When we pass a function as an argument into another function. 

We are never calling the callback function directly, instead we pass it into the main function where it ends up getting called. 

**Array methods:** Different ways to manipulate the arrays.

* .pop() = remove last item.
* .push() = add item to the rear of the list.
* .shift() = remove first item.
* .unshift() = add item to the front of the list.
* .splice() = add items to an array,  or remove elements from anywhere in the list. _notes.splice(1, 1)_ removes the middle item in a list of three. Splice takes three arguments. But the most commonly used are the first two integers, which represents indexes or positions, of the array that splice() is beeing called upon. The first parameter represents where to start, the second is the number of elements to delete. 

        function colorChange(arr, index, newColor) {
        arr.splice(index, 1, newColor);
        return arr;
        }

        let colorScheme = ['#878787', '#a08794', '#bb7e8c', '#c9b6be', '#d1becf'];

        colorScheme = colorChange(colorScheme, 2, '#332327');
        // we have removed '#bb7e8c' and added '#332327' in its place
        // colorScheme now equals ['#878787', '#a08794', '#332327', '#c9b6be', '#d1becf']

- .slice() copies or extracts a given number of elements to a new array, leaving the array its called upon untouched. Takes two perameters. First is index to start, second is index to stop.

let weatherConditions = ['rain', 'snow', 'sleet', 'hail', 'clear'];

        let todaysWeather = weatherConditions.slice(1, 3);
        // todaysWeather equals ['snow', 'sleet'];
        // weatherConditions still equals ['rain', 'snow', 'sleet', 'hail', 'clear'] 

* .forEach() = Loop over an array and apply the same code to all items. It is a function and takes a single argument that is also a function. This is a callback function that comes with two arguments we can access: item and index.
"item" refers to each individual item in the array. The second argument is the "index", which gives us the index of each individual item.
* .indexOf() = search for an item. In the parentesis we pass in what we are looking for. Returns a number, which is the index. If there are severals of the same, it returns the first one. If it's not there, the number is -1. (Not a callback function)
* .findIndex = A callback. Works much like forEach. Gets called one time for each item, and it takes the arguments item and index. If the match is true, it returns the index. Stops at first match. Returns -1 if nothing is found.
* .find() = A callback function that returns the actual item matching the search query and not just the index like .findIndex().
* .reduce() = An alternative to forEach() if you want to add values together. It applies a function against an accumulator for each item in the array. It takes four arguments: accumulator, currentValue, currentIndex and array

      [0, 1, 2, 3, 4].reduce(function(accumulator, currentValue, currentIndex, array) {
      return accumulator + currentValue;
      });

    In this example the accumulator changes from 0 - 1 - 3 - 6, the currentValue from 1 - 2 - 3 -4, the currentIndex from 1 - 2 - 3 - 4 and the return value from 1 - 3 - 6 - 10

    So it adds up the items in the array: 0 + 1 + 2 + 3 + 4.

Array.prototype.reduce(), or simply reduce(), is the most general of all array operations in JavaScript. You can solve almost any array processing problem using the reduce method.

This is not the case with the filter and map methods since they do not allow interaction between two different elements of the array. For example, if you want to compare elements of the array, or add them together, filter or map could not process that.

* .every() = Returns either true or false. It returns true if every array item matches our comparison function, and false otherwise.

        var numbers = [1, 5, 8, 0, 10, 11];
        numbers.every(function(currentValue) {
        return currentValue < 10;
        });
        // Returns false

* .some() = The some method works with arrays to check if any element passes a particular test. It returns a Boolean value - true if any of the values meet the criteria, false if not.

        var numbers = [10, 50, 8, 220, 110, 11];
        numbers.some(function(currentValue) {
        return currentValue < 10;
        });
        // Returns true

See also _filtering arrays_.

[See MDN for a complete list and documentation.](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array)

**Bracket notation:** A way to reference items in an array. This way we can also change the value.

    console.log(arrayList[3])

**Index (arrays):** The order the item comes in the array. The index starts at 0 in arrays.

**Arrays / array object:** Array is a global object thats used to create lists. Can store several types of data in one place, like a sting, a number, a boolean, another array, and objects. 

We declare a new array with opening and closing brackets ([]). Every unique data is separated with a comma.

    var sandwich = ["peanut butter", "jelly", "bread"]

Arrays, like objects, are passed as reference. That means that if you pass an array into a function and change it's values, it will directly change the original one. 

[See MDN for a complete list and documentation.](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array)

**hoisting:** When declaring a variable using "var", it gets hoisted to the top by the program. So even if we reference a "var" before it is declared, we get no errors. But it's only the declaration that gets hoisted, NOT the value.

**Math object:** This is a built in object that has properties and methods for mathematical constants and functions. Not a function object. 

**Number object:** From MDN: The Number JavaScript object is a wrapper object allowing you to work with numerical values. A Number object is created using the Number() constructor.

There are a lot less usefull methods avaliable for numbers compared to strings, since most calculations is done using the mathematical operators (+, -, *, /). 

[See MDN for a complete list and documentation.](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number)


**String object:** The string global object is a constructor for strings or a sequence of characters. And as such, there is a lot of different methods and properties avaliable from JavaScript itself, like ".length", ".toUpperCase()", ".charAt()". 

[See MDN for a complete list and documentation.](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)

**This (keyword):** A keyword that causes a lot of confusion. 

Inside of our methods, we can use the "this" keyword. "This" references the object the method is defined in.   

See "Methodes (object)".

**Methods (object):** We can also add functions as property values. So a method is   an object property, whos value is a function (Functions defined on objects).

    const car = {
    color: 'Red',
    getSummary: function () {
        return `This car is ${this.color}`
        }
    }

Can be shortened to this: 

    const car = {
    color: 'Red',
    getSummary() {
        return `This car is ${this.color}`
        }
    }  

How is this useful? With a function as a object property value, we get access to all the objects properties inside the function.

To access the objects properties, we use the "this" keyword.

Inside of our methods, we can use the "this" keyword. "This" references the object the method is defined in.   

By using objects and methods we are able to create a self contained unit where we have the functionality (our methods) stored along side the data that they work on.   

**Assignment operator (=):**

**Objects references:** When we pass an object as an argument, the arguments value is not just a clone of the object that gets passed, but a reference to the exact same one that is stored in memory.

So for example when we pass an object into a function, we can manipulate it's properties. If so, we manipulate the properties of the original object that gets passed in. But if we assign a new value to that argument, we break this binding. In that case, the argument does not point to the same thing as the object passed in as the argument does. So we can not use assignment operator (=) to clear the object or set it to something new. 

**Dot notation (objects):** A way to access the property of an object if we know the name of it.

    let myPerson = {
    name: 'Mikke',
    age: 38,
    location: 'Norway'
    }

    console.log(`${myPerson.name} is ${myPerson.age} and lives in ${myPerson.location}`);

**Objects:** Objects are a way to store related information about a single entity (like a book: title, pages, author, publish year) in one place. With object we model things.

Object are created with a variable name and opening and closing curly braces:

    let myBook = {
    
    }

Inside we need to define the various properties (properties describes the pieces of data stored on an object) for the object.

        let myBook = {
            title: 'Ego is the enemy'
        }

Above we have an object with a single property (title), and that propertys value is a string: 'Ego is the enemy'. 
We can add as many properties as we want to an object.

To retrieve information (object properties) we use dot notation

    console.log(myBook.title) // "Ego is the enemy"

We also use dot notation to set / change the value in an object.

    myBook.title = 'The obstacle is the way'

It's also a good idea to use objects with functions. If we pass objects into functions and return objects from functions, we can keep our function arguments a little cleaner by passing in just a single value instead of many, and it will allow us to return multiple values.

Everything that is not a primitive is an object in JavaScript.


**Template strings (ES6):** Introduced in ES6 as an easier way to combine / concatenate strings. 

To create a template string, we need to use back-ticks. In the part where we want to inject another value, we use a dollar sign ($) followed by opening and closing curly braces. Inside we add a JavaScript expression pointing to wanted value.

    let name = 'Mikke'
    console.log(`Hey, my name is ${name}!`)

We can add as many values as we need to into the string.

    console.log(`Hey, my name is ${name}! I am ${age} old`)

**Function scope:** The same scoping rules that applies to the program as a whole also applies to the functions.

The functions define local scopes. That includes everything inside the code block, but also the function arguments.

    // Global scope (convertFarenheitToCelsius, celsius)
    // Local scope (farenheit, celsius)

    let convertFerenheitToCelcius = function (farenheit) {
    let celsius = (farenheit - 32) * 5 / 9;
    return celsius;
    }

    let celsius = convertFerenheitToCelcius(68);

    console.log(celsius)

**Arguments default:** We can set a default value on the parameters when defining a function. If no arguments are set when calling the function, the default will be used. 

    let getScoreText = function (name, score = 0) { // 0 is set as default for score.
        console.log(name);
        console.log(score);
    }
    
    getScoreText('Andrew'); // Function call with just one or two arguments set.

When we don't want to pass an argument, we can set it to undefined when calling the function.

    getScoreText(undefined, 100);

**Expressions:** "An expression is any valid unit of code that resolves to a value" - MDN

**Return statement:** The reserved keyword "return". Can only be used a single time in our functions.

**Return value:** Returns the result of the code in the function.

Function: The output value / result of the function.

**Parameters:** The names listed in the function definition.

**Arguments:** The _real_ values that get passed to and recieved by the function. 

REGULAR FUNCTIONS ONLY:
We can access the arguments list in our local function by also using "arguments". So if we pass more arguments than parameters, they get stored and is accessible through "arguments".

    const add = function (a, b) {
    return arguments[0] + arguments[1]
    } 

    console.log(add(11, 22, 33, 4))

NB: Arguments only exist in regular functions. There is no "bound", no local variable, in arrow functions.

**Function:** Put simply: A program inside the program. This sub program can be executed as many times as we want. It is also the keyword we need to use, followed by a set of parentheses and curly braces.

    let greetUser = function () {
        console.log('Welcome user!');
    };

At this point the function is defined. To run / call it, we have to call it by reference it by name, followed by the function call syntax; An opening and closing parethesis after the name:

    greetUser();

There are three important parts to a function:

1. Input (argument):
The _real_ values that get passed to and recieved by the function. 
2. Code:
Code that does something meaningful.
3. Output (return value): Returns the result of the function. Can only be used once in our function.

        let square = function (num) { // Defined function with parameter.
            let result = num * num; // Code.
            return result; // Return value (output).
        }

        let value = square(3); // Function call with argument (input) "3"

**Leaked global:** If we assign a value to a variable that is not declared anywhere in the local or parent scope, it automatically gets declared in the global scope. But we can't reference it because it has not been explicitly declared with a name. 

To avoid it, just make sure that the variable is declared somewhere.

**Variable shadowing:** When a variable in a local scope uses it's value instead of the value in a parent scope with the same name. The local variable value is shadowing over the parents, hiding it from existens.

**Scope diagram:** A diagram describing / depicting the scope hierarchy in the program.

    // Global scope (varOne)
        // Local Scope (varTwo)
            // Local Scope (varFour)
        // Local Scope (varThree)

**Scope hierarchy:** Pointing to the depth of the scopes used in a program. The context in which the variable is defined and used and how they relate to each other in the hierarchy.

In a scope you can access variables defined in that scope, or in any parent/ancestor scope.

**Local scope:** Variables defined inside code blocks.

If we assign a value to a variable that is not declared anywhere in the local or parent scope, it automatically gets declared in the global scope.

**Global scope:** Global scope contains all variables defined outside all code blocks. 

If we assign a value to a variable that is not declared anywhere in the local or parent scope, it automatically gets declared in the global scope.  

**Lexical Scope (static scope):** The idea that a variable defined in one part of the program, may not be accessible everywhere else. The context in which the variable is defined and used comes in to play. So we need to pay attention to the code blocks in our script when talking about scope.

    let varOne = 'varOne'; // Global scope

    if (true) {
        console.log(varOne); // Avaliable due to parent/ancector
        let varTwo = 'varTwo'; // Local scope
        console.log(varTwo);
    }

    console.log(varTwo); //Reference error: not defined in global scope.   

**Scope:** Determines the accessibility (visibility) of variables. Where in the program are the variables defined.

In a scope you can access variables defined in that scope, or in any parent/ancestor scope.

Scopes are created in functions.

**Operator:** Constructs which behave generally like functions. Commons examples are arithmetic (+, -), comparison (>, <) and logical operations (&&, ||).

**Operand:** An operand is the object that is being worked on by an operation. 

    let x = 3; // x is an operand
    x = x + 3; // An operation of the operand

**Logical or operator:** A statement that returns true if one of the operands (booleans) to the left and right of the logical "or" operator (||) is true. 

    var num = 7;

    if (num > 10 || num < 5) { 
        return "Yes"; // True
    } 

**Logical and operator (&&):** A statement that returns true if the operands (booleans) to the left and right of the logical "and" operator (&&) is true. 

    var num = 7;

    if (num > 5 && num < 10) {
        return "Yes"; // True
    } 

**Else if** An "else if" clause in a "if" statement. Contains code that will run if the boolean in the "else if" parentheses is the first truth in the "if/else" statement.

    if (true) {
        // I run
    } else if (true) {
        // I don't run
    } else {
        // I don't run
    };

**Else:** An "else" clause in a "if" statement. Contains code that will run if the boolean in the "if" statement is false. 

**Flow control:** The ability to control the flow of our program using for example a series of if statements and conditions.

**Nesting:** Indentation or tabbing of nested code to improve readability.

**Code block:** A place where we can put as many lines of code that we want: if statements, functions, loops to name a few.  

**If:** The keyword that initialise the if statement.

**If (if/else) statements (conditional statements):** In the "if" statement, boolean conditions defined in the parentheses determine what code will run in the code block (or if it will run at all). Depending on whether the boolean is true or false, JavaScript will execute the code in the curly braces (code block).

    if (isFreezing) {
        console.log("It is freezing outside!"); // Will run if boolean is true.
    } 

You can expand the "if" statement by using "else" and/or "else if". 

    if (isFreezing <= -1) {
        console.log("It is freezing outside!"); // more than -1
    } else if (isFreezing > 0) {
        console.log("It's not freezing"); // If more than 0.
    } else {
        console.log("it's 0 degrees celcius."); // If none above.
    };

Only one codeblock will ever run, so it's important to pay attention to the order. The code is read from top to bottom, and stops at the first true condition:

    if (true) {
        // I run
    } else if (true) {
        // I don't run
    } else {
        // I don't run
    };

    if (false) {
        // I don't run
    } else if (true) {
        // I run
    } else {
        // I don't run
    };

    if (false) {
        // I don't run
    } else if (false) {
        // I don't run
    } else {
        // I run
    };

**Comparison operators (booleans):** There are six main comparison operators in JS:
    
    // 1. Equal: ===
    "Michael" === "Michael" // True
    "Michael" === "Peter" // False

    // 2. Not equal !==
    "Michael" !== 32 // True
    38 !== 38 // False

    // 3. Less than <
    5 < 10 // True
    5 < 5 // False

    // 4. Less than or equal to <=
    5 <= 5 // True
    5 <= 6 // False

    // 5. Greater than >
    5 > 2 // True
    5 > 10 // False

    // 6. Greater than or equal to >=
    10 >= 10 // True
    100 >= 100 // False

**Comments:** Text to insert into the program, that gets ignored by the computer. Used to describe various things about the code to the human reader. 

Line comment is initialised with to forward slashes:

    // This is a comment

Section comment is initialised with forward slash and asterisk, and ends with the opposite:

    /*
    This is a comment
    with multiple lines
    */

**The order of operations (my dear aunt Sally (multiplication, division, addition, subtraction)):** The order of operations in mathematics: multiplication, division, addition and subtraction. We can use parenthesis to controll the order (please excuse my dear aunt Sally (parentheses, exponents, multiplication, division, addition and subtraction)).

**Parenthesis:** Can change the order of operations or make sure that one operation happens before another.

    let age = 38;
    led result = (age + 3) * 7; // 287

**Division (/):** The forward slash (/) sign is used to divide numbers.

    let age = 38;
    led addResult = age / 2; // 17

**Multiplication (*):** The asterisk (*) sign is used to multiply numbers.

    let age = 38;
    led multiplyResult = age * 10; // 390

**Addition (+):** The plus (+) sign is used to add a number to another.

    let age = 38;
    led addResult = age + 1; // 39

**Subtraction (-):** The minus (-) sign is used to subtract one number from another.

    let age = 38;
    led addResult = age - 1; // 38

**String concatenation:** When adding strings together.
    
    "My name is" + " " + "Michael";
    console.log(firstName + " " + lastName);

**Semicolons (;):** Used to terminate our statements.

    var name = "Mikke";
    conosle.log(name);

It's actually optional, and we can rely on automatic semicolon insertion:

    var name = "Mikke"
    conosle.log(name)

**Plus / concatenation operator (+):** Used to combine / add values. 

**Camel casing:** A common convention on how to write variable names when it consists of several words. Every word starts with a capital letter except for the first one. It makes long names a litte easier to read.

    var myAge = "35";
    var thisIsAVeryLongVariableName: true;

**let (ES6):** A variable declaration introduced in ES6 as a replacement for "var" and is used if the value is going to change. Can be read as a sentence. "Let age equal to 38:


    let age = "38";


 The name can be made up of numbers, letters and $ or _ , but may not contain spaces or start with a number. And they can not be reserved keyword like "let" and "const". 
 
 "Undefined" if not given a value.  

 Also tells the reader of the code if this is a variable that can be changed.

**var:** A variable declaration. The name can be made up of numbers, letters and $ or _ , but may not contain spaces or start with a number. And they can not be reserved keyword like "let" and "const".

"Undefined" if not given a value. 

"var", as opposed to "const" and "let", is function scoped, not block scoped. So if we don't make a function, the "var" is avaliable from anywhere. That can cause us to lose control. 

**const (ES6):** A variable declaration introduced in ES6 and is used when a value is going to be constant. So we can't reassign a constant after it has been created. 

The name can be made up of numbers, letters and $ or _ , but may not contain spaces or start with a number. And they can not be reserved keyword like "let" and "const".

"Undefined" if not given a value.

When it comes to const objects, we can still manipulate the properties, but we can not assign a new value to it.  

Also tells the reader of the code if this is a variable that's never going to change.

**Reserved keyword:** A keyword like "let" or "const" that is a part of the JS-language and has a special meaning to it.  

**Undefined:** A language default. 

Variable: Datatype of a variable which does not yet have a value. The absens of a value.

Function: When an argument is not provided, but it's named  in the function definition, "undefined" is assigned as it's value. In this case, the return value will also be "undefined".

**Nan:** "Not a number". 

**Null:** Nothing. Also means "non-existent". Often used by developers when explicitly wanting to set something to "nothing" / clear a value. 

Used as an alternative to the language default "undefined", so that we don't lose the context; Is it the program or we as developers who have set "undefined"?. 

**Boolean:** A logical data type that can only be true or false. 

**String:** A sequence of characters. Used for text. Wrapped in single or double quotes.

    var string = "This is a string";

**Symbol:** 

**Number:** Floating point numbers, for decimals and integers. Not wrapped in quotes.

    var number = 38;

**Dynamic typing:**

**Data:** In computer science, data is anything that is meaningful to the computer.

**JavaScript variables (see also let, var, and const):** The variables sole purpose is to store and label data in memory, which can be referenced and manipulated by a computer program. We can think of variables like a container that hold information. The box can be labeled so that we better understand what it contains. 

Another popular analogy is the squid (Marjin Haverbeke) :octopus:. He points out that "we should think of variables as tentacles rather than boxes. They do not contain values; they grasp them". Meaning that if we want to remember something, we need to grow a tentacle and grab on to it, or reattach one of the exsisting ones. A program can only access the values that is has a hold on. A variable without a value is like thin air. There is nothing to hold on to, and thus it is "undefined". 

Either way, the label of the variable points to the data rather than using the data itself, similar to X and Y in mathematics. They are a simple names to represent the data we want to refer to. But computer variables differ from mathematical variables in that they can store different values at different times.

A variable name can only be defined once, or we get a SyntaxError: "Identifier '[variable name]' has already been declared".

The variable name can be made up of numbers, letters and $ or _ , but may not contain spaces or start with a number. And they can not be reserved keyword like "let" and "const".

**Data types:** JavaScript contains seven different datatypes which are undefined, null, boolean, string, symbol, number and object.

We can check a datas type by using

    typeof 123

