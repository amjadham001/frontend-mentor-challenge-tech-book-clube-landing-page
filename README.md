# Frontend Mentor - Tech book club landing page solution

This is a solution to the [Tech book club landing page challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/tech-book-club-landing-page-fZQidjHU73). Frontend Mentor challenges help you improve your coding skills by building realistic projects.

## Table of contents

- [Overview](#overview)
  - [The challenge](#the-challenge)
  - [Screenshot](#screenshot)
  - [Links](#links)
- [My process](#my-process)
  - [Built with](#built-with)
  - [What I learned](#what-i-learned)
  - [Useful resources](#useful-resources)
- [Author](#author)
- [Acknowledgments](#acknowledgments)

## Overview

### The challenge

Users should be able to:

- View the optimal layout for the interface depending on their device's screen size
- See hover and focus states for all interactive elements on the page

### Screenshot

- [Mobile screenshot](./screenshots/mobile.png)
- [Tablet screenshot](./screenshots/tablet.png)
- [Desktop screenshot](./screenshots/desktop.png)
- [Primary button hover state screenshot](./screenshots/primary-btn-hover.png)
- [Primary button focus state screenshot](./screenshots/primary-btn-focus.png)
- [Secondary button hover state screenshot](./screenshots/secondary-btn-hover.png)
- [Secondary button focus state screenshot](./screenshots/secondary-btn-focus.png)

### Links

- Solution URL: [GitHub Repository](https://github.com/amjadham001/frontend-mentor-challenge-tech-book-clube-landing-page.git)
- Live Site URL: [Live Demo](https://amjadham001.github.io/frontend-mentor-challenge-tech-book-clube-landing-page/)

## My process

### Built with

- Semantic HTML5 markup
- CSS custom properties
- Flexbox
- CSS Grid
- [Tailwindcss](https://tailwindcss.com/) - CSS framework
- Mobile-first workflow

### What I learned

#### Path Resolution in Tailwind CSS Arbitrary Values

During development, I encountered an issue with some image loading when using Tailwind's arbitrary value utilities for background images. The problem stemmed from path resolution differences between the HTML file location and the generated CSS file location.

**The Issue:**
When using arbitrary value utilities like `bg-[url(./assets/images/pattern.svg)]`, Tailwind processes these class names and generates CSS rules in a new CSS file at `styles/` folder (according to our configuration). Since the CSS file is located in the `styles/` subdirectory while the HTML file is in the root directory, the relative paths become invalid when referenced from the CSS context.

**Example of the Problem:**

```html
<!-- ❌ Incorrect - Path relative to HTML location -->
<div class="bg-[url(./assets/images/pattern-light-bg.svg)]"></div>

<!-- ✅ Correct - Path relative to CSS file location -->
<div class="bg-[url(../assets/images/pattern-light-bg.svg)]"></div>
```

**Root Cause:**

- HTML file location: `/` (root)
- CSS file location: `/styles/`
- When CSS references `./assets/`, it looks for assets relative to `/styles/` (which doesn't exist)
- The correct path should be `../assets/` to go up one directory from `/styles/` to `/` before accessing the assets folder

**Key Learning:**
When using Tailwind's arbitrary value utilities with file paths, always consider the final location of the generated CSS file, not the HTML file, when determining relative paths. This is a common pitfall that can cause resource loading failures in production builds.

### Useful resources

- [Figma](https://www.figma.com/) - This tool helped me to view and inspect the design in more detail such as `font-size`, `padding` and `margin`, to get a perfect and consistent result.

## Author

- Github - [@amjadham001](https://github.com/amjadham001)
- Frontend Mentor - [@amjadham001](https://www.frontendmentor.io/profile/amjadham001)
- Twitter - [@amjadham001](https://x.com/amjadham001)
- Codepen - [@amjadham001](https://codepen.io/amjadham001)

## Acknowledgments

To everyone who taught me a letter 🌹...
