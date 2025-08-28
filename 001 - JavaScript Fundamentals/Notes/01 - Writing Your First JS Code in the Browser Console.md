# Writing Your First JavaScript Code in the Browser Console

## Writing Your First JavaScript Code
We will now write our very first line of JavaScript code. For now, we will do this in the browser developer tools to get started as quickly as possible. Later, we will switch to the code editor that was installed previously.

Make sure to open up Google Chrome. There are three ways to open the Chrome developer tools:

- **Mac:** `command + option + J`
- **Windows:** `ctrl + alt + J`
- Right-click → **Inspect** → go to the **Elements** tab → then to the **Console**
- Or use the Chrome menu: **View > Developer > JavaScript Console**

All of these tabs are part of the developer tools, but we are interested in the **console**.  
The JavaScript developer console allows us to write and test JavaScript code. It is very useful during development, for example, to fix errors. However, we do not write real applications using this console. For now, let us use the console because it is an easy way to write some JavaScript.

---

## Using the Alert Function
Let us write `alert`, which is a JavaScript function. Open parenthesis, and without a space between `alert` and the parenthesis, write a string (basically text).

Example:

```javascript
alert("Hello world.");
````

This will give a popup window with `"Hello world"`.
This is your very first line of JavaScript code. Any code written here and executed will immediately be evaluated.

---

## Writing Variables and Conditionals

We can do much more. Let us write some more JavaScript code. You do not need to understand everything yet; this is just to show what can be done.

### Define a variable:

```javascript
let JS = "amazing";
```

Now, we have defined `JS` as being `"amazing"`.

### Conditional statement:

```javascript
if (JS === "amazing") {
  alert("JavaScript is fun.");
}
```

If you hit return, you will get a window that says **"JavaScript is fun."**

This demonstrates the logic:

* We defined `JS` as `"amazing"`.
* Then checked if it is equal to `"amazing"`.
* If true, JavaScript shows the alert window with the specified text.

---

### Changing the variable:

```javascript
JS = "boring";
```

```javascript
if (JS === "amazing") {
  alert("JavaScript is fun.");
}
```

This time, nothing happens because `JS` is no longer `"amazing"`.
The condition is not true, so the alert window is not shown.

---

## Navigating Previous Commands

You can access previous commands by hitting the **up arrow** on the keyboard.
This allows you to see all the previous commands that were used.

---

## Simple Math Operations in the Console

Another feature is performing simple math operations.
For example:

```javascript
40 + 8 + 23 - 10
```

This displays the result immediately.
The console can be used as a **calculator** for quick calculations and experimentation.

---

## Conclusion

This introduction provides a first taste of the JavaScript language and what lies ahead.
You are encouraged to experiment further with the console or proceed to the next lecture to learn more about what JavaScript actually is.

---

## Key Takeaways

* Introduced writing JavaScript code in the browser developer tools console.
* Demonstrated how to use the `alert` function and create variables in JavaScript.
* Showed how to use conditional statements and perform simple math operations in the console.
* Explained how to navigate previous commands and encouraged experimentation.

```
```
