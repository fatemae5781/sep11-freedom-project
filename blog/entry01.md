# Entry 1
##### 11/9/26

## Content

When Mister Mueller told us we would create an app that solves a problem, I did not know what to make at first. I was going to work with my friend Yuxin, so we thought about an app that could help us and other people. Then I remembered something Yuxin had told me was a real struggle for her family, her, and other people: managing money. Our idea is a money-saving and money-tracking app for people who have trouble managing their money and sometimes spend it all. The app will help users track their money and set a minimum balance they do not want to go below. If their balance gets close to that amount, the app will give them a warning to slow down their spending. If they go below the amount, it will give them a bigger warning. We also want users to be able to add bank accounts and write reminders to themselves. We are still thinking of more unique features to make the app special.

## The Tool I Chose and Why

At first, I thought about using **Kaboom.js** because I saw that it had a warning symbol in it. Kaboom.js is a tool for making games, so it is more useful for playful, game-like projects. After I explained our idea to Mr. Mueller, he suggested using **Math.js** and **Firebase** instead. Our app is focused on money and calculations, so Math.js makes more sense than a game tool. Firebase may also help us work with information for the app.

I wanted to understand Math.js first before I started tinkering with Firebase. I have not tinkered with Firebase yet. In my next learning log, I want to explain what Firebase is and what I tried with it. I also want to keep thinking about how we can use both tools in our app.

## What I Learned by Tinkering with Math.js

I used Math.js by loading the library into my code and trying examples with different numbers. A library is a set of tools that someone has made for programmers to use. I learned that Math.js must load before the program can use its methods. One way to load it in an HTML file is with a script tag:

```html
<script src="https://unpkg.com/mathjs/lib/browser/math.js"></script>
```

After the library loads, I can use `math.` before a Math.js method. For example:

```js
print(math.round(math.e, 3)); // Rounds e to three decimal places.
print(math.log(1000, 10));    // Finds the base-10 logarithm of 1000.
print(math.sqrt(64));         // Finds the square root of 64.
```

The first line rounds the value of `e` to three decimal places. The second line finds the base-10 logarithm of 1000, which is 3. The third line finds the square root of 64, which is 8. I also tried `math.pow(2, 6)`, which raises 2 to the power of 6.

I tested finding the smallest and largest numbers in a list:

```js
print(math.min(3, 10, 1, 2, 1, 6, 4, 6, 5, 7, 8, 1));
print(math.max(3, 10, 1, 2, 1, 6, 4, 6, 5, 7, 8, 1));
```

`math.min()` finds the smallest number in the list, and `math.max()` finds the largest. This could be helpful in a money app if we want to compare amounts or check a user’s lowest balance.

I also tried using Math.js to solve expressions written as text:

```js
print(math.evaluate("3 * (10 + 2)"));
print(math.evaluate("2010 / 48"));
print(math.evaluate("48 cm to inch"));
```

`math.evaluate()` reads the math expression and calculates the answer. For the first expression, it adds 10 and 2 first, then multiplies by 3, giving 36. The second expression divides 2010 by 48. The third converts 48 centimeters into inches. I learned that Math.js can understand units as well as regular numbers.

I tried **chaining**, which lets me connect several math actions together:

```js
var answer = math.chain(3)
    .add(10)
    .multiply(2)
    .done();
```

This starts with 3, adds 10, and then multiplies the result by 2. The final answer is 26. The `.done()` part finishes the chain and gives back the answer.

I made a helper function called `print()` to show the answer on the webpage:

```js
function print(value) {
  var precision = 14;
  document.write(math.format(value, precision) + "<br>");
}
```

This function takes a value, formats it, and writes it on the page. `math.format()` controls how the answer looks. In this example, the precision is set to 14, and `"<br>"` moves the next answer to a new line.

## More Math.js Experiments

On November 9, I made more examples instead of only reading about Math.js. I tried expressions, variables, functions, units, matrices, and **BigNumbers**. I changed the values to see how the answers changed.

This code calculates the diagonal of a rectangle:

```js
const diagonal = math.evaluate("sqrt(6^2 + 8^2)");
```

The expression finds the square root of 6 squared plus 8 squared. This uses the Pythagorean theorem. The answer is 10, which is the diagonal of a rectangle that is 6 units wide and 8 units long.

I also tried a parser. A parser can remember variables and use them in later calculations:

```js
const parser = math.parser();
parser.evaluate("price = 12.50");
parser.evaluate("quantity = 4");
console.log("Total cost:", parser.evaluate("price * quantity"));
```

First, I made a parser. Then I gave it a price of 12.50 and a quantity of 4. It remembers those values, so it can multiply them to find the total cost. This seems useful for a money app because an app might need to remember amounts and calculate totals.

I made and tested a function using the parser:

```js
parser.evaluate("area(width, height) = width * height");
console.log("Area of a 5-by-3 rectangle:", parser.evaluate("area(5, 3)"));
console.log("Area of a 10-by-2 rectangle:", parser.evaluate("area(10, 2)"));
```

This creates an `area` function. It multiplies the width by the height. I tested it with two different rectangles to make sure the answer changed when I used different measurements.

I also tested converting units:

```js
console.log("3 feet in centimeters:", math.evaluate("3 ft to cm").toString());
```

This changes 3 feet into centimeters. I learned that Math.js can work with measurements, not only plain numbers.

Another example compared regular JavaScript decimal math with Math.js:

```js
console.log("JavaScript 0.1 + 0.2:", 0.1 + 0.2);
console.log("Math.js 0.1 + 0.2:", math.evaluate("0.1 + 0.2"));
```

Sometimes regular JavaScript numbers have a tiny rounding error when adding decimals. Math.js can use BigNumbers to give a more exact result. In my test, Math.js gave 0.3, while regular JavaScript showed a tiny difference from 0.3.

I also tried adding two matrices:

```js
const matrixA = [[1, 2], [3, 4]];
const matrixB = [[5, 6], [7, 8]];
console.log("Matrix sum:", math.add(matrixA, matrixB).toString());
```

A matrix is a group of numbers organized in rows and columns. Math.js can add the matching numbers in the two matrices. Matrices may not be needed for the first version of our money app, but trying them helped me see that Math.js can do many different kinds of math.

## How I Might Use Math.js in the App

Math.js could help us calculate how much money users have after spending. It could also help compare a current balance with the minimum amount the user chose. For example, if the balance gets close to the minimum, the app could calculate the difference and show a warning. If the balance goes below the minimum, it could show a bigger warning. We still need to plan exactly how these features will work and which parts need Math.js.

The app will also have bank accounts and reminders, but I still need to learn more about Firebase before I can explain how we might use it. Our next steps are to keep exploring Math.js, learn Firebase, and decide what extra features will make the app more unique and helpful.

## Sources and Files

I used the [Math.js website](https://mathjs.org/) to learn about the library and look at examples. I also watched a [YouTube video about JavaScript’s Math object](https://www.youtube.com/watch?v=93Nd8f9HU8Q). That video was helpful for understanding the difference between the Math object and Math.js, even though it was not the exact tool I meant to learn about. I watched a Youtube video called [Math.js simple demo](https://www.youtube.com/watch?v=PFiXsJKfP_4) teaching me how to use math.js in a code way which was actually very helpful for me.

I also tried code examples in my files: [Math.js tinkering code one](../tool/mathjs1.html) and [my Math.js tinkering code](../tool/math.js2.html). 

## Engineering Design Process

Our project is in the **engineering design process** stage of thinking about the problem and exploring possible tools. We have identified a problem: some people have trouble keeping track of their money and may spend too much. We have started exploring Math.js to see how it could help with calculations. Our next steps are to explore Firebase, decide on the app’s important features. We are still thinking about what extra feature could make our app more unique.

## Skills

I developed **how to learn** and **how to search for information**. I tried to find YouTube videos that could teach me how to use the code. I clicked on a video about the JavaScript Math object, but I was trying to learn about Math.js. The video was still useful because I learned the difference between them.A **JavaScript Math object** and **Math.js** are related, but they are not the same. The Math object is already built into JavaScript, so I can use it without adding a library. It has basic math tools, such as finding a square root or rounding a number. Math.js is an extra library that I have to load into my project. It has more math features, such as working with units, matrices, and math expressions written as text. While trying to find help, I accidentally watched a video about the JavaScript Math object instead of the Math.js library. The video was still useful because it helped me understand the difference, but it was not exactly what I was looking for. I also learned that I should read the title carefully and search for the exact tool I need. Otherwise, I might spend time learning something different from what I planned.

I also developed **collaboration** and **asking for help**. I was writing my code in JSBin and changed some of the code, but when I clicked Run, I did not see any output. I thought my code was right, so I tried changing things in the HTML and the console, but nothing worked. I asked my friend for help, and she told me to click the Output button. I did not notice that button before. This taught me that asking someone for help and looking carefully at the program can help me find a problem faster. I should not be afraid to ask for help when I am stuck.


[Next](entry02.md)

[Home](../README.md)