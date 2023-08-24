# Don’t repeat yourself (DRY) Principle

“_Every piece of knowledge must have a single, unambiguous, authoritative representation within a system._” - Andy Hunt and Dave Thomas formally defined this principle in 1999 in their book The Pragmatic Programmer

Writing a function that contains a specific logic and then calling it multiple times in our code is a form of applying the DRY principle.

Here is a pseudocode that receives two temperatures in Fahrenheit and converts them into Celsius before applying DRY:

![Untitled](docs/assets/dry/image-1.png)

Now here is the same program after applying DRY:

![Untitled](docs/assets/dry/image-2.png)

We can see that, after applying DRY, the logic that converts Fahrenheit to Celsius appears only once in our code.

We can use a loop to execute repeated code

```jsx
let chips = ["corn", "pita", "potato", "tortilla"];

// non DRY code
console.log(chips[0]);
console.log(chips[1]);
console.log(chips[2]);

// DRY code
for (let i = 0; i < chips.length; i++) {
  console.log(chips[i]);
}
```

Another example is by taking repetitive bits of code and extracting them into a function.

```jsx
let drinks = ["lemonade", "soda", "tea", "water"];
let food = ["beans", "chicken", "rice"];
//non DRY code
console.log(drinks[0]);
console.log(drinks[1]);
console.log(drinks[2]);
console.log(drinks[3]);

console.log(food[0]);
console.log(food[1]);
console.log(food[2]);

// DRY code
function logItems(array) {
  for (let i = 0; i < array.length; i++) {
    console.log(array[i]);
  }
}

logItems(drinks);
logItems(food);
```

“Easy to change” doesn’t just mean clean code, if you can’t figure out what a variable is for or what a function does based on its name, then it’s harder to change it later, when you might not remember exactly how your code works (or when somebody else is trying to change your code).

**Advantages of DRY**

The advantages of the DRY principle include the following:

- It makes the codebase easier to maintain since if we wanted to change the logic or add to it, we’d only need to change it in one place instead of multiple locations where the logic appears
- It makes the code easier to read because there’ll be less redundancy in the code

**It’s important to mention that misusing DRY (creating functions where we don’t need to, making unnecessary abstractions, and so on) can lead to more complexity in our code rather than simplicity.**

```jsx
// non DRY code
let f = ["bananas", "dates", "dried figs", "oranges"];

function hi(banana) {
  for (let i = 0; i < banana.length; i++) {
    console.log(banana[i]);
  }
}

hi(f);

// DRY code
let fruits = ["bananas", "dates", "dried figs", "oranges"];

function logItems(array) {
  for (let i = 0; i < array.length; i++) {
    console.log(array[i]);
  }
}

logItems(fruits);
```

Using descriptive variable names make it easier to understand what the variable contains and in turn make it easier to use or change later on.

A good starting naming convention for your variables and functions would be:

- singluar words for variables containing values. i.e: fruit, firstName, favoriteColor
- plural words for variables containing objects or arrays. i.e: fruits, names, myColors
- a description for variables containing functions. ie: logFruits, findPerson, getFavoriteColor

**The Opposite of DRY**

WET (which can stand for We Enjoy Typing, Write Every Time, and Waste Everyone’s Time) is when we write the same logic more than once in our code, violating the DRY principle. As a result, the code becomes more difficult to read. Furthermore, if we wanted to change the logic, we’d have to make changes to all of its appearances in our codebase, making the code harder to maintain.

**Conclusion**

Whenever you finish writing some code, you should always look back to see if there is any way you can DRY it up, including: using descriptive variable names, taking repetitive bits of code and extracting them into a function or loop.
