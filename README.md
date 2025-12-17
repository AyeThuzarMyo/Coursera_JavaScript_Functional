# Coursera_JavaScript
# JavaScript Functional Styling Lab
A hands-on exploration of Functional Programming in JavaScript, focusing on variable scoping (let vs var), template literals, and the Browser Console API.

---
**Project Logic & Variable Scoping**
This project demonstrates the differences between block-scoped and function-scoped variables while building a console UI.

---
1. **Dynamic Styling with let**
In the consoleStyler function, we use let to declare variables. This is the modern standard for variables that will be reassigned or updated within a specific block.

```js
function consoleStyler(color, background, fontSize, txt) {
    // 'let' allows us to declare and then update the 'style' variable
    let message = "%c" + txt;
    let style = `color: ${color};`;

    // Using the += operator to append more CSS rules
    style += `background: ${background};`;
    style += `font-size: ${fontSize};`;

    console.log(message, style);
}
` ``` `
---

2. **Conditional Logic with var**
In the celebrateStyler function, var is used. Unlike let, var is function-scoped. While let is generally preferred in modern JS, using var here demonstrates the legacy approach to variable declaration.

```js
function celebrateStyler(reason) {
    // 'var' is function-scoped
    var fontStyle = "color: tomato; font-size: 50px";
    
    if (reason === "birthday") {
        console.log(`%cHappy birthday`, fontStyle);
    }
    else if (reason === "champions") {
        console.log(`%cCongrats on the title!`, fontStyle);
    }
    else {
        console.log(reason);
    }
}
` ``` `
---

3. **Function Composition**
The styleAndCelebrate function acts as a "higher-level" function. It accepts five parameters and distributes them to the specific helper functions, showcasing how modular code can be combined.

```js
function styleAndCelebrate(color, background, fontSize, txt, reason) {
    consoleStyler(color, background, fontSize, txt);
    celebrateStyler(reason);
}
---

Comparison: let vs var
Understanding the variables used in this project:

| Feature | let (Used in Task 1) | var (Used in Task 2) |
| **Scope** | Block Scoped (within { }) | Function Scoped |
| **Re-declaration** | Cannot be re-declared in the same scope | Can be re-declared |
| **Hoisting** | Hoisted, but not initialized | Hoisted and initialized as undefined |
| **Modern Usage** | Preferred for modern development | Generally avoided in modern JS |

---

**How to Run the Code**
1. Copy the entire script from functionalprogramming.js.
2. Open your browser's Developer Tools (F12 or Ctrl+Shift+I).
3. Navigate to the Console tab.
4. Paste the code and hit Enter.

**Expected Output**
When you run the final invocation: styleAndCelebrate('ef7c8e', 'fae8e0', '30px', 'You made it!', 'champions');

You will see:
"You made it!" styled with a pinkish text color and a cream background.
"Congrats on the title!" in large, tomato-colored text.
