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

**Undefined:** Datatype of a variable which does not yet have a value. 

**Nan:** "Not a number". 

**Null:** Nothing. Also means "non-existent".

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

