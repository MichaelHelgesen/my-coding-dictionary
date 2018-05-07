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

**var:** A variable declaration. The name can be made up of numbers, letters and $ or _ , but may not contain spaces or start with a number. And they can not be reserved keyword like "let" and "const".

"Undefined" if not given a value. 

**const (ES6):** A variable declaration introduced in ES6 and is used when a value is going to be constant.

The name can be made up of numbers, letters and $ or _ , but may not contain spaces or start with a number. And they can not be reserved keyword like "let" and "const".

"Undefined" if not given a value.

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

**Object:**

**Dynamic typing:**

**Data:** In computer science, data is anything that is meaningful to the computer.

**JavaScript variables (see also let, var, and const):** The variables sole purpose is to store and label data in memory, which can be referenced and manipulated by a computer program. We can think of variables like a container that hold information. The box can be labeled so that we better understand what it contains. 

Another popular analogy is the squid (Marjin Haverbeke) :octopus:. He points out that "we should think of variables as tentacles rather than boxes. They do not contain values; they grasp them". Meaning that if we want to remember something, we need to grow a tentacle and grab on to it, or reattach one of the exsisting ones. A program can only access the values that is has a hold on. A variable without a value is like thin air. There is nothing to hold on to, and thus it is "undefined". 

Either way, the label of the variable points to the data rather than using the data itself, similar to X and Y in mathematics. They are a simple names to represent the data we want to refer to. But computer variables differ from mathematical variables in that they can store different values at different times.

A variable name can only be defined once, or we get a SyntaxError: "Identifier '[variable name]' has already been declared".

The variable name can be made up of numbers, letters and $ or _ , but may not contain spaces or start with a number. And they can not be reserved keyword like "let" and "const".

**Data types:** JavaScript contains seven different datatypes which are undefined, null, boolean, string, symbol, number and object.

