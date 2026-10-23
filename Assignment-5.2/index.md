Here is the complete solution for Assignment 5.2 — CSS Selectors Practice.

To complete this assignment, create two files in the same folder on your computer: index.html and style.css.

1. The HTML File (index.html)
Save this code as index.html. It includes at least 5 HTML elements, cards with classes, a unique section with an ID, and a special paragraph to demonstrate rule conflict and specificity.

HTML
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CSS Selectors Practice</title>
    <!-- Link external stylesheet -->
    <link rel="stylesheet" href="style.css">
</head>
<body>

    <header>
        <!-- Grouping selector target -->
        <h1>CSS Selectors Masterclass</h1>
        <p>Exploring universal, element, class, ID, grouping, and specificity rules.</p>
    </header>

    <main>
        <!-- Step 4: ID Selector Section -->
        <section id="featured-section">
            <h2>Featured Topic</h2>
            <p>This section is styled uniquely using an ID selector (`#featured-section`).</p>
        </section>

        <!-- Step 3: Class Selector Cards -->
        <section class="container">
            <h2>Course Modules</h2>
            <div class="card">
                <h3>HTML Fundamentals</h3>
                <p>Learn structure, tags, and semantic markup.</p>
            </div>
            <div class="card">
                <h3>CSS Styling</h3>
                <p>Learn selectors, box model, flexbox, and grids.</p>
            </div>
            <div class="card">
                <h3>JavaScript Basics</h3>
                <p>Learn DOM manipulation and interactivity.</p>
            </div>
        </section>

        <!-- Step 7: Conflict & Specificity Demonstration -->
        <section>
            <h2>Specificity & Cascade Test</h2>
            <p class="special-text" id="conflict-demo">
                This paragraph tests specificity rules between element, class, and ID selectors!
            </p>
        </section>
    </main>

    <footer>
        <p>&copy; 2026 CSS Practice Portal</p>
    </footer>

</body>
</html>
2. The CSS File (style.css)
Save this code as style.css in the exact same folder as your index.html file.

CSS
/* Step 5: Universal Selector (*) */
* {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
}

body {
    font-family: Arial, sans-serif;
    background-color: #f4f7f6;
    color: #333333;
    line-height: 1.6;
    padding: 20px;
}

/* Step 2: Element Selector */
p {
    font-size: 1rem;
    color: #555555;
    margin-bottom: 10px;
}

/* Step 6: Grouping Selector */
h1, h2, h3 {
    color: #1a2a3a;
    font-weight: bold;
}

header {
    text-align: center;
    margin-bottom: 30px;
}

/* Step 4: ID Selector */
#featured-section {
    background-color: #fff8e1;
    border-left: 5px solid #ffc107;
    padding: 20px;
    margin-bottom: 25px;
    border-radius: 4px;
}

/* Step 3: Class Selector */
.container {
    background-color: #ffffff;
    padding: 25px;
    border-radius: 8px;
    margin-bottom: 25px;
    box-shadow: 0 2px 8px rgba(0,0,0,0.05);
}

.card {
    background-color: #f9f9f9;
    border: 1px solid #e0e0e0;
    padding: 15px;
    margin-bottom: 15px;
    border-radius: 6px;
}

/* ========================================================
   Step 7: Conflicting Rules & Specificity Demonstration
   ======================================================== */

/* Rule A: Element Selector */
p {
    color: #333333; /* Specificity: 0,0,1 */
}

/* Rule B: Class Selector */
.special-text {
    color: #0066cc; /* Specificity: 0,1,0 (Overrides element) */
}

/* Rule C: ID Selector */
#conflict-demo {
    color: #d9534f; /* Specificity: 1,0,0 (Overrides class & element) */
    font-weight: bold;
}
3. Explanation of CSS Selectors Used (For Your Submission)
Universal Selector (*):

Targets every element on the page. Used here to set box-sizing: border-box and reset default margin and padding.

Element Selector (p, header, footer):

Targets HTML elements directly by their tag name. Used to style all general paragraph text (p) and ensure consistent base typography.

Class Selector (.card, .container, .special-text):

Targets any element that has a specific class attribute. Classes can be reused across multiple elements. Used here to style individual modular content cards.

ID Selector (#featured-section, #conflict-demo):

Targets a single, unique element on the page identified by a unique id. IDs have high specificity. Used here to highlight a special featured section.

Grouping Selector (h1, h2, h3):

Combines multiple selectors separated by commas to apply the exact same style rules to all of them at once, keeping the code DRY (Don't Repeat Yourself).

Cascade and Specificity (p vs .special-text vs #conflict-demo):

Demonstrated in Step 7. When multiple rules target the same element, CSS resolves conflicts using specificity. An ID selector (#conflict-demo, specificity 1,0,0) beats a class selector (.special-text, specificity 0,1,0), which in turn beats an element selector (p, specificity 0,0,1), regardless of their order in the stylesheet.