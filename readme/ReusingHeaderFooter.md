# Reusing Header and Footer (JavaScript)

### 1. Create Separate Header and Footer Files

Create two separate files:

- **`header.html`**
- **`footer.html`**

### `header.html`

```html
html
CopyEdit
<header class="bg-primary text-white p-3">
    <h1>My Website</h1>
    <nav>
        <a href="index.html">Home</a> |
        <a href="about.html">About</a> |
        <a href="contact.html">Contact</a>
    </nav>
</header>

```

### `footer.html`

```html
html
CopyEdit
<footer class="bg-dark text-white text-center p-3">
    <p>&copy; 2025 My Website. All rights reserved.</p>
</footer>

```

---

### 2. Load Header and Footer in Each Page Using JavaScript

Add this script to each page where you want the header and footer to appear.

### Example: `index.html`

```html
html
CopyEdit
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My Website</title>
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css">
    <script>
        function loadComponent(id, file) {
            fetch(file)
                .then(response => response.text())
                .then(data => document.getElementById(id).innerHTML = data);
        }
    </script>
</head>
<body onload="loadComponent('header', 'header.html'); loadComponent('footer', 'footer.html');">

    <div id="header"></div>

    <main class="container my-4">
        <h2>Welcome to My Website</h2>
        <p>This is the homepage.</p>
    </main>

    <div id="footer"></div>

</body>
</html>

```

---

### 3. Repeat on Other Pages

Just copy the `<div id="header"></div>` and `<div id="footer"></div>` along with the script on each page.

This method makes updating the header and footer easy since changes in `header.html` or `footer.html` automatically reflect on all pages.

# Exemple:

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <!-- Fetch Header and Footer -->
    <script>
        function loadComponent(id, file, callback) {
            fetch(file)
                .then(response => response.text())
                .then(data => {
                    document.getElementById(id).innerHTML = data;
                    if (callback) callback(); // Ensure callback (like setActiveLink) runs after loading
                })
                .catch(error => console.error(`Error loading ${file}:`, error));
        }

        function setActiveLink() {
            let currentPage = window.location.pathname.split("/").pop();
            let links = document.querySelectorAll("nav a");

            links.forEach(link => {
                if (link.getAttribute("href") === currentPage) {
                    link.classList.add("active", "fw-bold", "text-dark");
                } else {
                    link.classList.remove("active", "fw-bold", "text-dark");
                }
            });
        }

        window.onload = function () {
            loadComponent('header', 'components/header.html', setActiveLink);
            loadComponent('footer', 'components/footer.html');
        };
    </script>

</head>

<body>
    <!-- Header -->
    <div id="header"></div>

    <div class="wrapper">
        <main class="content">

            <section>
                <div>
                </div>
            </section

        </main>
        <!-- Footer -->
        <div id="footer"></div>
    </div>

</body>

</html>
```

### **Store in a Separate Folder (More Organized)**

For better organisation, you can create a `components` folder:

```
/public_html
│── index.html
│── about.html
│── contact.html
│── components/
│   │── header.html
│   │── footer.html

```

👉 **If you use this setup, update the script to:**

```
js
CopyEdit
loadComponent('header', 'components/header.html', setActiveLink);
loadComponent('footer', 'components/footer.html');

```