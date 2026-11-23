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


### 11/9/26
* I experimented with Math.js by making my own small examples instead of only reading its documentation. I tried expression evaluation, variables, functions, units, matrices, and BigNumbers. I also changed the values in the examples to see what would happen. I learned that Math.js can do more than regular JavaScript math it can work with math expressions written as text, keep variables in a parser, and calculate with different kinds of numbers.The parser was useful because I could create variables once and use them in later calculations. I also changed the input to my area function to test that it worked with different dimensions. The unit example showed that Math.js understands measurements, not just plain numbers. The BigNumber test was interesting because normal JavaScript numbers gave a tiny rounding error, while Math.js returned 0.3. So overall, I learned that the library can handle many types of math in a short amount of code, and that changing the examples helped me understand how its features work. 
* I have the code on math.js2.md

### november 23 2026
* So I finally started to tinker with my other tool **Firebase**, and it’s a collection of tools from Google that helps people build and run apps. Instead of creating every feature from scratch, developers can use Firebase for things like signing users in, saving app data, protecting requests, and monitoring app performance.

* I read the Firebase developer documentation and watched a video about using Firebase with Android apps and Google AI Studio. The video showed how Firebase can help an Android app use Gemini AI without putting a private API key directly inside the app.

* The video explained **Firebase AI Logic**. It lets an app send requests to Gemini using Firebase’s tools. This is safer than putting a Gemini API key in the app, because people might be able to find a key stored in an app that they download.

* It also explained **Firebase App Check**. App Check helps check that requests are coming from a real, trusted version of the app not from someone pretending to be the app. During development, Google AI Studio can help set up a debug token automatically. For a published app, the video said the setup can use reCAPTCHA Enterprise to help verify the app.

* The example app in the video used **Firebase Authentication** so a user could sign in with Google. It also used Firebase AI Logic to send a photo and request to Gemini, which then generated an image of the person wearing a Halloween costume.

* Here is a small example of Firebase code that initializes Firebase in an Android app:

```kotlin
val app = Firebase.initializeApp(context)
```

`Firebase.initializeApp(context)` starts Firebase and connects the app to its Firebase project. The `context` tells Android which app is being initialized.

* The video also mentioned **Cloud Firestore**, Firebase’s database for saving and syncing app information, and **Firebase Authentication**, which helps apps manage user sign-ins.

* I learned that Firebase is not just one tool. It is a group of services that can help with different parts of an app, such as data, sign in, security, and AI. I want to keep exploring its documentation and try a Firebase feature in a small app.

* **Links I used today:**
  * [Firebase documentation](https://firebase.google.com/)
  * [Firebase Android AI and App Check video](https://www.youtube.com/watch?v=ms3vRyTM8w0)


<!-- 
* Links you used today (websites, videos, etc)
* Things you tried, progress you made, etc
* Challenges, a-ha moments, etc
* Questions you still have
* What you're going to try next
-->
