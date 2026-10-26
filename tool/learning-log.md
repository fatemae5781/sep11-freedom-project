# Tool Learning Log

## Tool: **Math.js**

## Project: **money tracker**

---

### 10/25/26:

* Today I explored **Math.js**, a JavaScript library for doing math. A library is a set of tools someone has made for programmers to use. Unlike JavaScript’s built-in Math object, Math.js must be added to a project before I can use it.

* The video explained that I need to include the Math.js library with a link, then use math. followed by the method I want. The example page you shared loads it with this script tag:

```html
<script src="https://unpkg.com/mathjs/lib/browser/math.js"></script>
```

* After loading the library, I can use Math.js methods. I tried changing the example numbers:

```js
print(math.round(math.e, 3)); // 2.718
print(math.log(1000, 10));    // 3
print(math.sqrt(64));         // 8
```

* `math.round(math.e, 3)` rounds the value of `e` to three decimal places. `math.log(1000, 10)` finds the base-10 logarithm of 1000, which is 3. `math.sqrt(64)` finds the square root of 64, which is 8.

* I also tried Math.js’s expression parser. It lets me write a math expression as text inside `math.evaluate()`:

```js
console.log(math.evaluate("3 * (10 + 2)")); // 36
console.log(math.evaluate("48 / 6"));       // 8
```

* I changed the numbers to see how the answers changed. In the first expression, Math.js adds 10 and 2 first, then multiplies the result by 3. That gives 36. The second expression divides 48 by 6, giving 8.

* Math.js can also work with more than regular numbers. The examples on its website show it can calculate with units, complex numbers, fractions, arrays, and matrices. For example, it can convert centimeters to inches or find the determinant of a matrix.

* I learned that I need to load the Math.js library before using its methods. If the library is not loaded, the browser will not know what math means. I want to keep trying different numbers and expressions to see what Math.js can calculate.

* **Links I used today:**
  * [Math.js](https://mathjs.org/)
  * [Math.js video](https://www.youtube.com/watch?v=PFiXsJKfP_4)


<!-- 
* Links you used today (websites, videos, etc)
* Things you tried, progress you made, etc
* Challenges, a-ha moments, etc
* Questions you still have
* What you're going to try next
-->
