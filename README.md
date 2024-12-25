# resume_website

### Detailed Explanation of the HTML Code

The provided HTML code creates an interactive resume webpage with sections such as experience, education, projects, skills, and interests. Let's break down each part of the code and explain its relationships and functionality in detail:

---

### 1. **HTML Structure**

- `<!DOCTYPE html>`: Declares the document type as HTML5.
- `<html lang="en">`: Starts the HTML document and specifies the language as English.
- `<head>`: Contains metadata and links/styles for the document.
- `<body>`: Contains the visible content of the webpage.

---

### 2. **Head Section**

```html
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Rupesh Kumar Thakur - Resume</title>
  <style>
    ...
  </style>
</head>
```
- `<meta charset="UTF-8">`: Ensures proper encoding of characters.
- `<meta name="viewport" content="width=device-width, initial-scale=1.0">`: Makes the website responsive.
- `<title>`: Sets the title of the webpage.
- `<style>`: Includes CSS for styling the page.

### Relationships
- The `<meta>` tags ensure the document is accessible and functional on various devices.
- The `<style>` tag directly affects how elements in the `<body>` are displayed.

---

### 3. **CSS Styles**

The CSS defines the visual appearance of the webpage.

#### General Styles
```css
body {
  margin: 0;
  padding: 0;
  font-family: 'Arial', sans-serif;
  background: linear-gradient(to bottom, #87CEEB, #FFD700);
  overflow-x: hidden;
}
```
- Sets the font, background gradient, and removes default margins and padding.

#### Header Styling
```css
header {
  text-align: center;
  color: white;
  padding: 2em 0;
}
```
- Centers text and adds padding around the header.

#### Main Content Styling
```css
main {
  display: flex;
  flex-direction: column;
  align-items: center;
  padding: 2em;
  background: white;
  margin: 2em;
  border-radius: 15px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
}
```
- The `main` element contains all sections, styled with a shadow and rounded corners for aesthetics.

#### Section Styles
```css
section {
  width: 100%;
  margin-bottom: 1em;
  cursor: pointer;
  transition: opacity 0.3s;
}

section:hover h2 {
  color: #2ecc71;
}

.content {
  display: none;
  padding: 1em;
  background-color: #ecf0f1;
  border-radius: 5px;
}
```
- Sections are collapsible.
- The `.content` class is initially hidden and displayed on interaction.

---

### 4. **Body Section**

The `<body>` contains structured elements:

#### Header
```html
<header>
  <img src="your_photo.jpg" alt="Your Photo" style="border-radius: 50%;" height="100" width="100">
  <h1>Rupesh Kumar Thakur</h1>
  <p>
    <img src="phone_icon.png" alt="Phone Icon" height="16" width="16"> +91 9835271246
    <img src="email_icon.png" alt="Email Icon" height="16" width="16"> rupeshkumarthakur135@gmail.com
    <img src="linkedin_icon.png" alt="LinkedIn Icon" height="16" width="16"> <a href="https://www.linkedin.com/in/rupesh-kumar-thakur-12a469212/" target="_blank">LinkedIn</a>
  </p>
</header>
```
- Displays the name, contact information, and a circular profile picture.
- Icons improve visual representation of phone, email, and LinkedIn links.

#### Main Sections
Each section (“Experience”, “Education”, etc.) is structured as follows:

```html
<section onclick="toggleContent('experience')">
  <h2>EXPERIENCE</h2>
  <div class="content experience">
    <ul>
      <li><strong>Fidelity International</strong> (August 2022 – Present)
        <ul>
          <li>Contributed to a test-bed framework project for automated integration testing...</li>
        </ul>
      </li>
    </ul>
  </div>
</section>
```

- **`<section>`**: Encapsulates each category.
- **`<h2>`**: Section headings.
- **`.content`**: Hidden divs that are displayed upon interaction.
- **`onclick="toggleContent('experience')"`**: Calls a JavaScript function to toggle visibility.

---

### 5. **JavaScript Functionality**

```javascript
function toggleContent(section) {
  const content = document.querySelector(`.${section}`);
  const sectionElement = content.parentElement;

  if (sectionElement.classList.contains('expanded')) {
    content.style.display = 'none';
    sectionElement.classList.remove('expanded');
  } else {
    content.style.display = 'block';
    sectionElement.classList.add('expanded');
  }
}
```

- **Purpose**: Toggles visibility of the `.content` block within a section.
- **Workflow**:
  1. Identifies the section to toggle using its class.
  2. Checks if the section is currently expanded.
  3. If expanded, it hides the content and removes the class.
  4. Otherwise, it shows the content and adds the class.

---

### Relationships Between Blocks

1. **HTML and CSS**:
   - The CSS styles defined in the `<style>` block are applied to corresponding HTML tags and classes.
   - For example, `.content` is styled to initially hide its content, and `.expanded` modifies its behavior.

2. **HTML and JavaScript**:
   - JavaScript functions modify the behavior of HTML elements, like toggling `.content` visibility.

3. **CSS and JavaScript**:
   - JavaScript dynamically applies or removes CSS classes (e.g., `.expanded`), altering the appearance defined in CSS.

---

### Example Use Case
1. **Viewing Experience Details**:
   - Click on the "Experience" section.
   - JavaScript toggles the `.content` div visibility, showing details about roles and responsibilities.

2. **Responsive Design**:
   - On smaller screens, CSS media queries adjust padding and margins for better readability.

---

