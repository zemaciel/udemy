# Stick Footer

Check the Sandbox project on the GitHub Udemy Repository (3 Feb 2025)

https://github.com/zemaciel/udemy/tree/main/sandbox

### **1. Make the Page Fill the Full Height**

We applied this CSS:

```css
html, body {
    height: 100%;
    margin: 0;
    display: flex;
    flex-direction: column;
}

```

- This ensures that the `body` takes up **at least** the full height of the viewport.
- The `display: flex; flex-direction: column;` makes the elements inside stack vertically.

### **2. Create a Wrapper That Expands**

```css
.wrapper {
    display: flex;
    flex-direction: column;
    min-height: 100vh;
}

```

- The `wrapper` acts as a **flex container** that stretches across the full viewport height.

### **3. Make the Content Expand**

```css
.content {
    flex: 1;
}

```

- `flex: 1;` makes the `content` section grow and take up **all available space**.
- This pushes the footer **down to the bottom** when there's not enough content.

### **4. Ensure the Footer Stays at the Bottom**

```css
.footer {
    margin-top: auto;
}

```

- `margin-top: auto;` tells the browser to **push the footer down** if there's extra space.

### **Why This Works**

By using **CSS Flexbox**, we let the `content` section expand dynamically while ensuring the `footer` only moves when necessary. This method works well across different screen sizes and avoids using absolute positioning (which can cause issues).

Let me know if you need more clarification! 🚀