# Linking a JavaScript File

## Introduction
In this lecture, we will learn how to write JavaScript code in a separate file and run it in the browser by linking it to an HTML file.

---

## Downloading the Starter Code
1. Download the starter code from the GitHub repository (link provided in the course).
2. Click the green **Download ZIP** button.  
   - If not visible (on smaller screens), scroll to the **FAQ section** and use the provided link.
3. Extract the ZIP file after download.

**Folder structure:**
- **final** → Contains the final version of the code for reference.
- **starter** → Starting point for each section/project (use this in VS Code).

---

## Opening the Project in VS Code
- Move the **starter folder** to your desktop.
- Open it in **VS Code** as your project folder.
- Inside, you will find `index.html`.

---

## Writing JavaScript in HTML
JavaScript is usually attached to web pages. Start with an **HTML document**.  
Add a `<script>` tag (place it beneath the `<style>` tag if present).

**Example:**
```html
<script>
  let js = 'amazing';
  if (js === 'amazing') alert('JavaScript is fun!');
</script>
````

* Use `;` at the end of each line (not mandatory, but good practice).
* Open `index.html` in the browser → The alert should appear.

---

## Using the Browser Console

Try a math operation inside your script:

```javascript
40 + 8 + 23 - 10;
```

Reload → Nothing shows, because JavaScript doesn’t print to the console by default.
To see results, use `console.log`:

```javascript
console.log(40 + 8 + 23 - 10);
```

Reload the page → The result shows in the **developer console**, along with the line number in `index.html`.

---

## Recap: Console vs Script Tag

* **Console (previous lecture):** No need for `console.log` or a script tag.
* **Script file:** Must use `console.log` to output values.

---

## Moving JavaScript to an External File

Inline scripts are not ideal. Instead:

1. Create a new file → `script.js`
2. Copy JavaScript code from the `<script>` tag → Paste into `script.js`
3. Remove the inline `<script>` tag from HTML.

---

## Linking the JavaScript File to HTML

Add a script tag **at the end of the `<body>`**, but use the `src` attribute:

```html
<script src="script.js"></script>
```

* If `script.js` is in the same folder as `index.html`, only the filename is needed.
* Reload the page → Code runs as before.

**Troubleshooting:**

* Ensure `script.js` is in the same folder as `index.html`.
* Double-check spelling of `src` and filenames.
* Fix any JavaScript errors.

---

## Conclusion

You now have a clean separation between **logic** (JavaScript file) and **presentation** (HTML file).
Your JavaScript runs in the browser via a linked external file.

---

## Key Takeaways

* Download and extract the starter code from the GitHub repository.
* Use the **starter folder** in VS Code; keep **final folder** for reference.
* Use `<script>` in HTML to run JavaScript; use `console.log` for outputs.
* Prefer external `.js` files linked with `<script src="..."></script>` for better organization.

```
```
