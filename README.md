# Interactive Resume Webpage

This project is an interactive resume webpage. It demonstrates how to create a simple, responsive, and interactive web page using HTML, CSS, and JavaScript.

## Table of Contents

1. [Overview](#overview)
2. [File Structure](#file-structure)
3. [HTML Structure](#html-structure)
4. [CSS Styling](#css-styling)
5. [JavaScript Functionality](#javascript-functionality)
6. [Responsive Design](#responsive-design)
7. [How to Use](#how-to-use)
8. [Customization](#customization)
9. [Learning Points](#learning-points)
10. [Detailed Code Explanation](#detailed-code-explanation)

## Overview

This webpage serves as an online resume, featuring sections for:
- Personal Information
- Experience
- Education
- College Projects
- Skills
- Interests

The page is designed to be interactive, with expandable sections that reveal more information when clicked.

## File Structure

The entire webpage is contained in a single HTML file, which includes:
- HTML structure
- CSS styling (in the `<style>` tag)
- JavaScript (in the `<script>` tag)

## HTML Structure

The HTML is structured as follows:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <!-- Meta tags and title -->
    <style>
        <!-- CSS styles -->
    </style>
</head>
<body>
    <header>
        <!-- Personal information -->
    </header>
    <main>
        <!-- Sections for experience, education, etc. -->
    </main>
    <script>
        <!-- JavaScript for interactivity -->
    </script>
</body>
</html>
```

Each section of the resume is wrapped in a `<section>` tag with an onclick event that toggles its content visibility.

## CSS Styling

The CSS uses:
- A gradient background for the body
- Flexbox for layout
- Transitions for smooth animations
- Media queries for responsiveness

Key styling features:
- The body has a gradient background
- The main content area has a white background with rounded corners and a shadow
- Sections have hover effects that change the color of headings
- Content areas have a light gray background when expanded

## JavaScript Functionality

The JavaScript function `toggleContent(section)` is responsible for showing/hiding the content of each section when clicked. It works by:
1. Finding the content element of the clicked section
2. Toggling its display property between 'none' and 'block'
3. Adding or removing an 'expanded' class to control opacity

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

## Responsive Design

The webpage is made responsive using:
- Flexbox for layout
- Percentage-based widths
- Media queries to adjust styling for smaller screens

## How to Use

1. Copy the entire HTML code into a file named `index.html`
2. Open the file in a web browser
3. Click on each section header to expand/collapse the content

## Customization

To customize this resume:
1. Replace the personal information in the `<header>` section
2. Modify the content within each `<section>` to reflect your own experiences, education, etc.
3. Update the `<style>` section to change colors, fonts, or layout as desired

## Learning Points

This project demonstrates several key web development concepts:
1. Semantic HTML structure
2. CSS styling techniques including flexbox, gradients, and transitions
3. Basic JavaScript for interactivity
4. Responsive design principles
5. Combining HTML, CSS, and JavaScript in a single file for a complete webpage

## Detailed Code Explanation

### HTML Structure

```html
<!DOCTYPE html>
<html lang="en">
```
- `<!DOCTYPE html>`: Declares that this is an HTML5 document.
- `<html lang="en">`: The root element of the HTML page, specifying English as the language.

```html
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Rupesh Kumar Thakur - Resume</title>
```
- `<head>`: Contains meta-information about the HTML page.
- `<meta charset="UTF-8">`: Specifies the character encoding for the document (UTF-8 includes almost all characters from all human languages).
- `<meta name="viewport" ...>`: Ensures proper rendering on mobile devices, setting the viewport width to the device width and initial zoom level to 1.0.
- `<title>`: Sets the title of the webpage, which appears in the browser's title bar or page's tab.

### CSS Styling

```css
body {
  margin: 0;
  padding: 0;
  font-family: 'Arial', sans-serif;
  background: linear-gradient(to bottom, #87CEEB, #FFD700);
  overflow-x: hidden;
}
```
- Removes default margin and padding
- Sets the font to Arial with sans-serif as a fallback
- Creates a gradient background from sky blue (#87CEEB) to gold (#FFD700)
- Hides horizontal scrollbar

```css
header {
  text-align: center;
  color: white;
  padding: 2em 0;
}
```
- Centers the text in the header
- Sets text color to white
- Adds padding to top and bottom of the header

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
- Uses flexbox for layout
- Sets flex-direction to column for vertical stacking of elements
- Centers items horizontally
- Adds padding, white background, margin
- Rounds corners and adds a subtle shadow

```css
section {
  width: 100%;
  margin-bottom: 1em;
  cursor: pointer;
  transition: opacity 0.3s;
}
```
- Makes sections full width
- Adds bottom margin to separate sections
- Changes cursor to pointer on hover
- Adds a transition effect for opacity changes

```css
.content {
  display: none;
  padding: 1em;
  background-color: #ecf0f1;
  border-radius: 5px;
}
```
- Initially hides the content
- Adds padding
- Sets a light gray background
- Rounds corners of the content area

### **Body Section**
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

### JavaScript Functionality

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
- Selects the content element using the passed section name
- Checks if the section is currently expanded
- If expanded, hides the content and removes the 'expanded' class
- If not expanded, shows the content and adds the 'expanded' class
- This creates the toggle effect for each section

### Responsive Design

```css
@media only screen and (max-width: 600px) {
  main {
    margin: 1em;
    padding: 1em;
  }

  .content {
    padding: 0.5em;
  }
}
```
- This media query targets screens smaller than 600px wide
- Reduces margin and padding of the main content area
- Reduces padding of content divs
- This ensures the layout remains visually appealing on smaller screens

By understanding each part of this code in detail, you can learn how HTML, CSS, and JavaScript work together to create an interactive and responsive web page. This knowledge can be applied to create your own web projects or to customize this resume template further.

