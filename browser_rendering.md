# Life Skills - Session 01: Browser Rendering

## Browser Rendering: How HTML, CSS, and JS Are Processed

When you open a website in a browser, the browser starts a complex process to display the content correctly on your screen. This process is known as **browser rendering**. It involves converting the code written in HTML, CSS, and JavaScript into a visual representation that users can interact with. Think of it like a chef (the browser) preparing a dish (the webpage) from raw ingredients (HTML, CSS, JS) to a fully plated meal (the rendered site).

### Rendering Pipeline Explained:

1. **HTML Parsing**: The browser downloads the HTML file and parses it to build the **DOM Tree** (Document Object Model), a structure representing all HTML elements on the page.

2. **CSS Parsing**: Simultaneously, the browser fetches and parses CSS files to create the **CSSOM Tree** (CSS Object Model), which defines styles for elements.

3. **Render Tree Construction**: The DOM and CSSOM are combined into a **Render Tree**, containing only the visible elements on the screen along with their styles.

4. **JavaScript Execution**: The browser's **JavaScript engine** (e.g., V8 in Chrome) executes any JS code. If the script manipulates the DOM or CSSOM (e.g., `document.write()`, or modifying class names), it may delay rendering.

5. **Layout (Reflow)**: Once the Render Tree is complete, the browser calculates the **exact position and size** of each element — this stage is called layout or reflow.

6. **Painting**: Each node from the Render Tree is converted into **actual pixels** on the screen, defining colors, borders, shadows, etc.

7. **Compositing**: Finally, if the page includes complex layers (like CSS transforms or animations), the browser **composites** them in the correct order to produce the final display.

### JavaScript and Render Blocking

- If a `<script>` tag appears before HTML is fully parsed, it can **block the creation of the DOM**, delaying the page load.
- External CSS files can **block rendering** until they are downloaded and parsed, which is why optimizing the **Critical Rendering Path** is important for performance.

### Key Concepts:

* **DOM (Document Object Model)** – structure of HTML elements
* **CSSOM (CSS Object Model)** – structure of CSS styles
* **Render Tree** – visual elements with styles
* **Reflow/Layout** – computes layout information
* **Painting** – fills in pixels
* **Compositing** – final step to display layered content
* **Render Blocking** – scripts or styles that delay rendering
* **JavaScript Engine** – runs code that may modify DOM/CSS

---

### References

* [MDN Web Docs - How Browsers Work](https://developer.mozilla.org/en-US/docs/Web/Performance/How_browsers_work)
* [Google Developers - Critical Rendering Path](https://developers.google.com/web/fundamentals/performance/critical-rendering-path)
* [YouTube - How Browsers Render HTML](https://www.youtube.com/watch?v=SmE4OwHztCc)
* [What is the DOM? - MDN](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model/Introduction)
* [Inside Look at Modern Web Browsers (Google)](https://web.dev/inside-browser-part1/)

