# Lazy Loading Image Component

A simple React project showcasing a **lazy-loading image component** built with **React Hooks** and the **Intersection Observer API**. This component defers loading images until they enter the viewport, improving page performance and user experience.

## Table of Contents

- [Demo](#demo)
- [Features](#features)
- [Getting Started](#getting-started)
  - [Prerequisites](#prerequisites)
  - [Installation](#installation)
  - [Running the App](#running-the-app)
- [Usage](#usage)
  - [LazyImage Props](#lazyimage-props)
- [Project Structure](#project-structure)
- [Available Scripts](#available-scripts)
- [How It Works](#how-it-works)
- [Performance Tips](#performance-tips)
- [Contributing](#contributing)
- [License](#license)

## Demo

> No demo available yet.
> ```
> ```

## Features

- 🚀 **Lazy loading** for images using the Intersection Observer API
- ⚛️ Built with modern **React** and **React Hooks**
- 🧩 Easy-to-reuse `<LazyImage />` component
- 📱 Works great with long lists or image-heavy pages
- ♿ Fallback support for browsers without Intersection Observer

## Getting Started

This project was bootstrapped with [Create React App](https://create-react-app.dev/).

### Prerequisites

Make sure you have the following installed:

- **Node.js** (LTS recommended)
- **npm** (comes with Node.js)

You can check your versions with:

```bash
node -v
npm -v
```

Clone the repository and install dependencies:

```bash
git clone https://github.com/Jkalio52/lazy-loading-image.git
cd lazy-loading-image
npm install
Running the App
Start the development server:

npm start
Then open your browser at:

http://localhost:3000
The page will reload when you make edits. Lint errors will appear in the console.

Usage
Below is an example of how you might use the lazy-loading image component in your app. Adjust the import path to match your actual file structure.

import React from 'react';
import LazyImage from './components/LazyImage';

function App() {
  return (
    <div>
      <h1>Lazy Loading Image Demo</h1>

      <LazyImage
        src="https://via.placeholder.com/800x600"
        alt="Sample Lazy Loaded"
        placeholder="https://via.placeholder.com/10x10"
        className="lazy-image"
      />
    </div>
  );
}

export default App;
LazyImage Props
These are suggested props – update this section to match your actual component implementation.

src (string, required): Final image URL that should be loaded lazily.
alt (string, recommended): Alt text for accessibility.
placeholder (string, optional): Low‑resolution or placeholder image shown before the main image loads.
className (string, optional): Additional CSS class names.
...imgProps: Any extra props are spread onto the underlying <img /> element.
Project Structure
This is a generic overview — update the component paths to match your repo if they differ.

lazy-loading-image/
├─ public/
│  ├─ index.html
│  └─ ...
├─ src/
│  ├─ components/
│  │  └─ LazyImage.js
│  ├─ App.js
│  ├─ index.js
│  ├─ App.css
│  └─ index.css
├─ package.json
├─ README.md
└─ ...
Available Scripts
In the project directory, you can run:

npm start
Runs the app in development mode.

Open http://localhost:3000 to view it in the browser.
The page reloads when you make edits.
You will see any lint errors in the console.
npm test
Launches the test runner in interactive watch mode.

npm test
See the Create React App documentation for more information on testing.

npm run build
Builds the app for production to the build folder.

npm run build
Bundles React in production mode
Minifies the code
Filenames include content hashes
Your app is ready to be deployed. See the CRA docs for deployment examples.

npm run eject
Note: this is a one‑way operation. Once you eject, you can’t go back.


Copy all configuration files and dependencies (Webpack, Babel, ESLint, etc.) into your project so you can fully customize them.

Most users will never need to run this. Stick with the default configuration unless you know you need custom tooling.

How It Works
At a high level, the lazy-loading image component works like this:

Initial render

The component renders a placeholder (blank, blurred, or tiny image) instead of the full image.
Intersection Observer

A IntersectionObserver is attached to the image container.
When the element scrolls into the viewport (i.e., becomes visible), the observer callback fires.
Swap source

When visible, the component swaps the src from the placeholder to the real image URL.
Optionally, it can add a CSS class (e.g. loaded) to trigger a fade‑in effect.
Cleanup

The observer disconnects when no longer needed to avoid memory leaks.
If IntersectionObserver is not supported by the browser, you can fall back to:

Immediately loading the image, or
A simple window.scroll/resize listener (if implemented).
Performance Tips
Use compressed and appropriately sized images.
Use a blurred or tiny placeholder to make loading feel smoother.
Avoid unnecessary re-renders in parent components that contain many lazy images.
Consider combining lazy loading with code splitting and React Suspense for large apps.
Contributing
Contributions, issues, and feature requests are welcome.

Fork the repository
Create your feature branch: git checkout -b feature/my-feature
Commit your changes: git commit -m "Add my feature"
Push to the branch: git push origin feature/my-feature
Open a Pull Request
License
This project is licensed under the MIT License. See the LICENSEOpens a new window file for details.

Author: Jay Kalio

Lazy-loading images is an easy win for performance—feel free to use this component in your own projects and adapt it to your needs.