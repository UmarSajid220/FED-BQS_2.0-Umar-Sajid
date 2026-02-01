# **First Steps in JavaScript**

### **Introduction: What is JavaScript and Why Learn It?**

Welcome to the world of JavaScript\! If you've ever wondered what makes websites "come alive"—with interactive menus, updating news feeds, or online games—the answer is JavaScript. Think of a website like a house. HTML is the frame and the walls, giving it structure. CSS is the paint, furniture, and decorations, making it look good. JavaScript is the electricity and plumbing; it's what makes everything *work*. It turns a static structure into a dynamic, interactive experience for the user.

This guide is designed to walk you through the absolute essentials of JavaScript, one step at a time. We'll cover the core building blocks: how to store information in variables, the different types of data you'll work with, and how to make your code make decisions. By the end, you'll have a solid foundation to build upon. All the information here is synthesized from top-tier learning resources, giving you everything you need to get started on the right foot.

Let's begin with the very first step: setting up a place where you can write and test your code.

\--------------------------------------------------------------------------------

## **1\. Your Coding Playground: How to Run JavaScript**

Before we dive into writing code, it's crucial to have a simple, accessible place to practice. You don't need to install any complex software to get started. In fact, one of the most powerful tools for learning JavaScript is already on your computer: your web browser. The ability to quickly test snippets of code is the best way to learn and experiment.

### **Using the Browser Console**

Every modern web browser comes with a set of developer tools, including a "console." The console is a fantastic place to run single lines of JavaScript and see the results instantly. It’s perfect for quick tests and experiments.

Here’s how to open it:

1. Open any webpage in your browser (it can even be a blank tab).  
2. Right-click anywhere on the page.  
3. From the menu that appears, click on “Inspect” or “Inspect Element”. This will open the Developer Tools panel.  
4. Find and click on the “Console” tab within that panel.

Now, you can type code directly into the console. Let's try the traditional first program, "Hello, World\!". Type the following line into the console and press Enter:

console.log("Hello, World\!");

You should see the message Hello, World\! printed out right below your command. console.log() is a command you'll use constantly to check the values of variables and see what your code is doing behind the scenes.

### **Setting Up a Simple HTML File**

While the console is great for small tests, you'll eventually want to write longer scripts. The most common way to do this is by linking a JavaScript file to an HTML file. This mimics how JavaScript is used on real websites.

Here is a basic HTML skeleton you can save in a file (e.g., index.html):

\<\!DOCTYPE html\>  
\<html lang="en"\>  
\<head\>  
  \<meta charset="UTF-8"\>  
  \<meta name="viewport" content="width=device-width, initial-scale=1.0"\>  
  \<title\>Document\</title\>  
\</head\>  
\<body\>  
    
  \<\!-- You can write JavaScript directly in a \<script\> tag \--\>  
  \<script\>  
    // Your JavaScript goes here\!  
    console.log("Hello, World\!");  
  \</script\>

  \<\!-- Or, you can link to an external .js file \--\>  
  \<script src="javascript.js"\>\</script\>

\</body\>  
\</html\>

You have two options:

1. **Internal Script:** Write your code directly inside the \<script\> tags as shown above.  
2. **External Script:** Create a separate file with a .js extension (e.g., javascript.js), write your code there, and link it using the src attribute.

For the rest of this guide, you can practice using either the browser console for quick tests or an HTML file. While both internal and external scripts work, using an external .js file is strongly recommended for anything more than a few lines of code. It keeps your HTML and JavaScript separate, which is much cleaner and easier to manage as your projects grow.

\--------------------------------------------------------------------------------

## **2\. The Core Building Blocks: Variables and Data Types**

Now that you have a place to write code, let's learn about the fundamental concepts. At the heart of any program is data—numbers, text, and other pieces of information. To work with this data, we need a way to store and label it. This is where variables come in. Think of variables as "storage containers" for your data. Just as important is understanding the *type* of data you're storing, as this determines what you can do with it.

### **Declaring Variables: let and const**

In JavaScript, a variable is like a labeled box where you can put information. To create a variable, you "declare" it using a keyword. The two modern keywords you should use are let and const.

The let keyword is used for variables whose values might change later.

// Declare a variable named 'age' and assign it the value 11  
let age \= 11;  
console.log(age); // Outputs: 11

// Re-assign the variable with a new value  
age \= 54;  
console.log(age); // Outputs: 54

The const keyword is used for variables that are *constant*—meaning their value will not be reassigned after they are created. If you try to change a const variable, JavaScript will helpfully throw an error to let you know you're trying to do something you shouldn't.

const pi \= 3.14;  
pi \= 10; // This will cause an error\!  
console.log(pi); // The code won't even get this far.

**A Note on var**: You might see an older keyword, var, in some code examples online. While it also declares variables, it has some quirky behaviors that have been improved upon with let and const. As a best practice, you should avoid using var and stick to let and const.

### **JavaScript's Eight Data Types**

Every piece of data in JavaScript has a type. The language is **dynamically typed**, which means a single variable can hold different data types over time (though this is often not a good practice\!). There are eight basic data types in total.

* **Seven Primitive Types:**  
  * number: Represents both integers (like 10) and floating-point numbers (like 3.14).  
  * bigint: For integer numbers that are too large to be represented by the number type.  
  * string: For text. A string is a sequence of characters, like "Hello" or 'JavaScript'.  
  * boolean: Represents one of two values: true or false.  
  * null: Represents a special value of "nothing," "empty," or "value unknown."  
  * undefined: Represents a value that "is not assigned."  
  * symbol: Used to create unique identifiers, a more advanced feature.  
* **One Non-Primitive Type:**  
  * object: Used for more complex data structures and collections of data.

Let's explore the most common ones you'll use every day.

#### **Numbers**

The number type in JavaScript handles both whole numbers and decimals. It also includes three special values:

* Infinity and \-Infinity: Represent the mathematical concept of infinity. You might get this if you divide by zero (1 / 0).  
* NaN: Stands for "Not-a-Number." It represents a computational error, like trying to divide a string by a number ("text" / 2).

One great thing about JavaScript is that mathematical operations are "safe." Your script won't crash if you try to do something impossible like divide by zero; at worst, you'll just get NaN as the result.

#### **Strings**

A string is simply a piece of text. In JavaScript, you can create strings using three different types of quotes:

1. **Single quotes:** 'Hello'  
2. **Double quotes:** "World"  
3. **Backticks:** \`JavaScript\`

Single and double quotes work in almost the same way. The main difference is convenience: if your string contains a single quote, you can wrap it in double quotes, and vice-versa.

const single \= 'She said "Hello\!"';  
const double \= "I'm learning JavaScript.";

##### **Focus on Backticks (Template Literals)**

Backticks are special because they offer "extended functionality." They create what are called **template literals**, which have two major advantages.

First, they allow you to embed variables and expressions directly into the string using the ${...} syntax. This makes creating dynamic strings much cleaner.

let name \= "John";

// Using a template literal to embed a variable  
console.log(\`Hello, ${name}\!\`); // Outputs: Hello, John\!

// You can also embed expressions  
console.log(\`The result is ${1 \+ 2}\`); // Outputs: The result is 3

Second, template literals respect line breaks in your code, making it easy to create multiline strings.

const multiline \= \`One day you finally knew  
what you had to do, and began,\`;

console.log(multiline);

With regular quotes, you would have to use a special character (\\n) to achieve the same result.

##### **String Concatenation**

Joining strings together is called **concatenation**. While you can use the \+ operator for this, template literals are almost always more readable.

const name \= "Bob";

// Old way using the \+ operator  
console.log("Hello" \+ ", " \+ name); // "Hello, Bob"

// Modern way using template literals  
console.log(\`Hello, ${name}\`); // "Hello, Bob"

#### **Booleans**

The boolean type is very simple: it only has two possible values, true and false. This type is the foundation of decision-making in code. It's used to store yes/no states or the result of a comparison.

let nameFieldChecked \= true; // yes, the field is checked  
let isGreater \= 4 \> 1;       // yes, 4 is greater than 1, so this is true

#### **The "Empty" Values: null and undefined**

These two types can be a bit confusing at first, but the distinction is important:

* **undefined** means "a value has not been assigned." If you declare a variable but don't give it a value, it will be undefined by default.  
* **null** is a value you can intentionally assign to a variable to represent that it is "empty" or "unknown."

In short, undefined is the default state of an uninitialized variable, whereas null is a deliberate assignment of "no value."

### **Checking the Type with typeof**

Sometimes, you'll need to know what type of data is stored in a variable. The typeof operator is a handy tool for this. It returns a string with the name of the data type.

typeof undefined     // "undefined"  
typeof 0             // "number"  
typeof 10n           // "bigint"  
typeof true          // "boolean"  
typeof "foo"         // "string"  
typeof Symbol("id")  // "symbol"  
typeof Math          // "object"  
typeof null          // "object"  \<-- This is a famous quirk\!  
typeof alert         // "function"

**The typeof null Quirk:** Notice that typeof null returns "object". This is a well-known, long-standing error in JavaScript that has been kept for compatibility reasons. Just remember: null is not an object, even though typeof says it is. It's a primitive type of its own.

Now that we understand how to store and identify different types of data, the next logical step is to learn how to compare them.

\--------------------------------------------------------------------------------

## **3\. Evaluating Your Data: Comparison Operators**

A huge part of programming involves asking questions about your data to guide what the program does next. Is this number bigger than that one? Are these two strings the same? These questions are answered using comparison operators. The result of any comparison is always a boolean value: either true or false.

Here are the primary comparison operators you'll use:

| Operator | Description |
| :---- | :---- |
| \> | Greater than |
| \< | Less than |
| \>= | Greater than or equal to |
| \<= | Less than or equal to |
| \== | Equals (Loose Equality) |
| \!= | Not equals (Loose) |
| \=== | Strict Equals (checks value and type) |
| \!== | Strict Not equals (checks value and type) |

### **The Pitfall of Loose Equality (\==) vs. The Safety of Strict Equality (\===)**

This is one of the most important distinctions for a new JavaScript developer to learn. The regular, double-equals operator (\==) can sometimes behave in unexpected ways. This is because **it tries to convert values of different types before comparing them.**

For example, \== considers 0 and false to be the same:

console.log(0 \== false); // true, because \`false\` is converted to 0  
console.log('' \== false); // true, because the empty string \`''\` is also converted to 0

This can lead to subtle bugs. To avoid this, you should almost always use the **strict equality operator (\===)**. This operator checks for equality *without* performing any type conversion. If the types are different, it immediately returns false.

console.log(0 \=== false); // false, because the types are different (number vs. boolean)

There is also a strict non-equality operator (\!==). The rule of thumb is simple: **always prefer \=== and \!== to avoid errors and make your code's intention clear.**

### **Comparing Different Data Types**

When you use comparison operators like \> or \< with values of different types, JavaScript will convert both values to numbers before making the comparison.

console.log('2' \> 1); // true, because the string '2' is converted to the number 2  
console.log('01' \== 1); // true, because the string '01' is converted to the number 1

When comparing two strings, JavaScript uses "lexicographical" or dictionary order. It compares the strings character by character.

console.log('Z' \> 'A');      // true  
console.log('Glow' \> 'Glee'); // true, because 'o' comes after 'e'

### **The Strange Case of null and undefined**

Comparing null and undefined can be tricky because they behave differently depending on the operator.

* **Strict Equality (\===):** null \=== undefined is false. They are not strictly equal because they are of different types.  
* **Loose Equality (\==):** null \== undefined is true. This is a special rule in JavaScript: they are a "sweet couple" that equal each other in a loose comparison, but they don't equal any other value.  
* **Math Comparisons (\>, \<, etc.):** For math comparisons, null is converted to 0, while undefined is converted to NaN (Not-a-Number).

This leads to a very strange result when comparing null with 0:

console.log(null \> 0);  // (1) false, because null becomes 0, and 0 is not \> 0  
console.log(null \== 0); // (2) false, because \`==\` only equates null with undefined  
console.log(null \>= 0); // (3) true, because null becomes 0, and 0 is \>= 0

It's weird that null \>= 0 is true, but null \> 0 and null \== 0 are both false. This happens because the equality operator (\==) has a special rule for null/undefined, while the other mathematical comparison operators (\>, \<, \>=) follow the rule of converting null to 0.

The key takeaway is to be very careful. **Avoid using comparisons like \> or \< with variables that might be null or undefined** unless you are absolutely sure of what you're doing.

Now that we know how to ask questions about our data, let's learn how to combine those questions to build more complex logic.

\--------------------------------------------------------------------------------

## **4\. Building Conditions: Truthy, Falsy, and Logical Operators**

In JavaScript, decisions aren't just based on the pure boolean values true and false. The language has a broader concept of "truthiness." Every value has an inherent boolean quality when used in a condition, allowing us to write more concise and flexible code. This is where the concepts of "truthy" and "falsy" values come into play.

### **Understanding 'Truthy' and 'Falsy' Values**

A value is considered **falsy** if it behaves like false when evaluated in a boolean context, such as an if statement. In JavaScript, there are only six falsy values you need to remember:

* false  
* The number 0  
* An empty string ""  
* null  
* undefined  
* NaN (Not-a-Number)

Any other value is considered **truthy**. This includes non-zero numbers (even negative ones), non-empty strings (even a string containing "0"), objects, and arrays.

This allows us to write simple checks like this:

if (1) { // 1 is truthy  
  console.log("This will run\!");  
}

if ("0") { // The string "0" is also truthy  
  console.log("This will also run\!");  
}

### **Combining Logic with Operators: || (OR), && (AND), \! (NOT)**

Logical operators allow us to test multiple conditions at once, creating more complex decision-making rules.

#### **|| (OR)**

The OR operator (||) evaluates a chain of expressions and returns the **first truthy value** it finds. The value is returned in its original form, not as a boolean. If no truthy value is found, it returns the last operand.

This operator uses "short-circuit evaluation." It stops checking as soon as it finds a truthy value.

// \`null\` is falsy, \`0\` is falsy, so it continues. \`1\` is truthy, so it stops and returns 1\.  
console.log(null || 0 || 1); // Outputs: 1

// All values are falsy, so it returns the last one.  
console.log(undefined || null || 0); // Outputs: 0

#### **&& (AND)**

The AND operator (&&) does the opposite. It evaluates a chain of expressions and returns the **first falsy value** it finds. If all values are truthy, it returns the last operand.

It also uses short-circuit evaluation, stopping as soon as it finds a falsy value.

// \`1\` is truthy, so it continues. \`0\` is falsy, so it stops and returns 0\.  
console.log(1 && 0); // Outputs: 0

// It finds \`null\` (which is falsy) and stops, never even looking at \`3\`.  
console.log(1 && 2 && null && 3); // Outputs: null

#### **\! (NOT)**

The NOT operator (\!) is the simplest. It takes a single value, converts it to its boolean equivalent, and then returns the opposite.

console.log(\!true);  // false  
console.log(\!0);     // true (because 0 is falsy)

A common trick is to use a **double NOT (\!\!)** to convert any value into its pure boolean form (true or false). The first \! converts the value to its opposite boolean, and the second \! flips it back to its actual boolean value.

console.log(\!\!"non-empty string"); // true  
console.log(\!\!null);              // false

**Operator Precedence:** It's important to know the order in which these operators are evaluated. \! (NOT) has the highest precedence, followed by && (AND), and finally || (OR).

With these logical building blocks, we can now construct conditional statements that control which parts of our code get executed.

\--------------------------------------------------------------------------------

## **5\. Controlling the Flow: Conditional Statements**

Conditional statements are the decision-making structures of your code. They use the true or false results from comparisons and logical operations to choose which block of code to execute. This is how you make your program responsive to different inputs and situations.

### **The if...else Statement**

The most common conditional statement is if...else. Its structure is very readable and follows a simple logic.

The basic if statement executes a block of code only if the condition in the parentheses is true (or truthy).

let year \= 2015;  
if (year \== 2015\) {  
  console.log("That's correct\!");  
}

You can add an optional else block that will execute only if the if condition is false (or falsy).

let year \= 2024;  
if (year \== 2015\) {  
  console.log('You guessed it right\!');  
} else {  
  console.log('How can you be so wrong?');  
}

For checking multiple conditions, you can use else if. JavaScript will check each condition in order until one is met. If none are met, the final else block will run.

let year \= 2024;

if (year \< 2015\) {  
  console.log('Too early...');  
} else if (year \> 2015\) {  
  console.log('Too late');  
} else {  
  console.log('Exactly\!');  
}

**Best Practice:** It's highly recommended to always wrap your code blocks in curly braces {}, even if there's only one line. This improves readability and prevents potential errors.

### **The Ternary Operator: ?**

The conditional operator, often called the **ternary operator** because it has three operands, is a compact alternative to a simple if...else statement. It's particularly useful when you want to assign a value to a variable based on a condition.

The syntax looks like this: let result \= condition ? value1 : value2;

If the condition is true, value1 is returned. Otherwise, value2 is returned.

Here's how we can rewrite a simple if...else block using the ternary operator:

let age \= 20;  
let accessAllowed;

// Using if...else  
if (age \> 18\) {  
  accessAllowed \= true;  
} else {  
  accessAllowed \= false;  
}

// Using the ternary operator \- much shorter\!  
let accessAllowedTernary \= (age \> 18\) ? true : false;

While it's shorter, remember that the main purpose of the ternary operator is to *return a value*. If you need to execute different, more complex branches of code, a standard if...else statement is more readable and should be preferred.

### **The switch Statement**

The switch statement is a useful alternative to a long chain of if...else if blocks, especially when you are comparing a single variable against several possible values.

The syntax involves a value to check, followed by case blocks for each potential match, an optional default block for when no cases match, and break statements to exit the block.

let choice \= "sunny";

switch (choice) {  
  case "sunny":  
    console.log("It is nice and sunny outside today.");  
    break; // The break statement prevents "fall-through"  
  case "rainy":  
    console.log("Rain is falling outside; take a rain coat.");  
    break;  
  case "snowing":  
    console.log("The snow is coming down — it is freezing\!");  
    break;  
  default:  
    console.log("Please select a weather type.");  
}

A crucial detail is that switch uses a **strict equality (\===) check**. This means the type of the value matters.

let arg \= "3";  
switch (arg) {  
  case 3: // This is the number 3, not the string "3"  
    console.log('Never executes\!'); // This code is unreachable  
    break;  
  default:  
    console.log('Type matters\!');  
}

If you omit the break statement, the code will "fall through" and execute the next case block as well. This can sometimes be used intentionally to group cases that share the same code.

let a \= 3;  
switch (a) {  
  case 3: // Grouped with case 5  
  case 5:  
    console.log('a is 3 or 5');  
    break;  
  default:  
    console.log('The number is not 3 or 5.');  
}

You now have a powerful toolkit for making decisions in your JavaScript programs. Let's put this new knowledge to the test.

\--------------------------------------------------------------------------------

## **6\. Knowledge Check: Practice Problems**

The best way to solidify your understanding is to apply what you've learned. Try to figure out the answers to these challenges before looking at the solution and explanation.

\--------------------------------------------------------------------------------

**Challenge 1: Comparisons**

What will be the result of the following expressions?

5 \> 4  
"apple" \> "pineapple"  
"2" \> "12"  
undefined \== null  
undefined \=== null  
null \== "\\n0\\n"  
null \=== \+"\\n0\\n"

#### **Solution and Explanation**

**Solution:**

5 \> 4               // true  
"apple" \> "pineapple" // false  
"2" \> "12"          // true  
undefined \== null   // true  
undefined \=== null  // false  
null \== "\\n0\\n"     // false  
null \=== \+"\\n0\\n"   // false

**Explanation:**

1. 5 \> 4 is a simple numerical comparison and is true.  
2. "apple" \> "pineapple" is false. Strings are compared character by character, and 'a' is not greater than 'p'.  
3. "2" \> "12" is true. This is also a string comparison. It compares the first character of each string: '2' is greater than '1'.  
4. undefined \== null is true. This is a special rule in JavaScript where these two values are loosely equal to each other and nothing else.  
5. undefined \=== null is false. They are of different types, so they are not strictly equal.  
6. null \== "\\n0\\n" is false. null is only loosely equal to undefined.  
7. null \=== \+"\\n0\\n" is false. The types are different (null vs. number, since \+"\\n0\\n" becomes 0), so strict equality fails.

\--------------------------------------------------------------------------------

**Challenge 2: if and Falsy Values**

Will the console.log be executed?

if ("0") {  
  console.log('Hello');  
}

#### **Solution and Explanation**

**Solution:** Yes, the message will be logged.

**Explanation:** The string "0" is not an empty string, so it is a **truthy** value. Any non-empty string becomes true in a boolean context. The only falsy string is the empty one: "".

\--------------------------------------------------------------------------------

**Challenge 3: Logical Operators**

What will the result of this code be?

console.log(null || 2 && 3 || 4);

#### **Solution and Explanation**

**Solution:** The code will log 3.

**Explanation:** The && (AND) operator has a higher precedence than || (OR), so it runs first.

1. 2 && 3 is evaluated. Since both 2 and 3 are truthy, && returns the last truthy value, which is 3.  
2. The expression now becomes null || 3 || 4.  
3. The || (OR) operator finds the first truthy value. null is falsy, so it moves on. 3 is truthy, so the evaluation stops and 3 is returned.

\--------------------------------------------------------------------------------

**Challenge 4: Rewriting if..else into switch**

Rewrite the following if statement using a switch statement.

let a \= 2;

if (a \== 0\) {  
  console.log( 0 );  
}  
if (a \== 1\) {  
  console.log( 1 );  
}  
if (a \== 2 || a \== 3\) {  
  console.log( '2,3' );  
}

#### **Solution and Explanation**

**Solution:**

let a \= 2;

switch (a) {  
  case 0:  
    console.log(0);  
    break;

  case 1:  
    console.log(1);  
    break;

  case 2:  
  case 3:  
    console.log('2,3');  
    break;  
}

**Explanation:**

* The conditions a \== 0 and a \== 1 become case 0: and case 1:.  
* The condition a \== 2 || a \== 3 is handled by grouping case 2: and case 3: together. Because case 2: has no break, the code "falls through" and executes the code for case 3:.

\--------------------------------------------------------------------------------

## **7\. Summary and Key Takeaways**

Congratulations on taking your first steps into JavaScript\! We've covered the absolute fundamentals that form the basis of all programming. Here is a quick review of the most critical concepts:

* **Variables:** Use let for variables that will be reassigned and const for variables that should never change. Avoid using the older var keyword.  
* **Falsy Values:** There are only six falsy values in JavaScript: false, 0, "" (empty string), null, undefined, and NaN. Everything else is truthy.  
* **Strict vs. Loose Equality:** Always prefer the strict equality operator (\===) over the loose equality operator (\==) to avoid unexpected behavior from type conversion.  
* **Logical Operators:**  
  * || (OR) finds and returns the *first truthy* value.  
  * && (AND) finds and returns the *first falsy* value.  
* **Conditional Statements:**  
  * Use if / else if / else for handling complex, branching logic.  
  * Use the **ternary operator** (?) as a concise way to assign a value based on a simple condition.  
  * Use a switch statement as a clean alternative to long if...else if chains when checking a single value against multiple possibilities.

## **8\. Further Learning Resources**

Learning to code is a journey, and this guide is just the beginning. The best way to improve is to keep practicing and exploring. The resources used to create this guide are some of the best on the web for learning JavaScript and are excellent next steps.

* **MDN (Mozilla Developer Network) Docs:**  
  * [Handling text — strings in JavaScript](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/First_steps/Strings): A deep dive into creating and manipulating strings, including template literals and concatenation.  
  * [Making decisions in your code — conditionals](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Building_blocks/conditionals): A comprehensive look at if, else, switch, logical operators, and the ternary operator.  
* **JavaScript.info Tutorials:**  
  * [Data types](https://javascript.info/types): A detailed breakdown of all fundamental data types in JavaScript, including the typeof operator and its quirks.  
  * [Comparisons](https://javascript.info/comparison): An essential guide to how JavaScript compares values, including the tricky cases of null and undefined.  
  * [Logical operators](https://javascript.info/logical-operators): An in-depth explanation of how ||, &&, and \! work, including short-circuiting.  
  * [Conditional branching: if, '?'](https://javascript.info/ifelse): A thorough review of if/else and the ternary operator with practical tasks.  
  * [The "switch" statement](https://javascript.info/switch): A focused look at the syntax and behavior of the switch statement.  
* **The Odin Project:**  
  * [Variables and Operators](https://www.theodinproject.com/lessons/foundations-variables-and-operators): A foundational lesson on setting up your environment, declaring variables, and working with numbers.  
  * [Data Types and Conditionals](https://www.theodinproject.com/lessons/foundations-data-types-and-conditionals): An overview that ties together many of the topics covered in this guide, from data types to conditional logic.

