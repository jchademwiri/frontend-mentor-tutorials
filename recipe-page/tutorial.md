# Creating a Recipe Page with HTML & Tailwind CSS

## Introduction

#### Welcome your viewers and introduce yourself.

- "Hi everyone, welcome back to my channel! My name is Jacob, and today I’ll show you how to create a professional recipe page using HTML, Vite, and Tailwind CSS."

#### Briefly explain the tools:

- **HTML**: The foundation for structuring the page.
- **Vite**: A build tool to speed up development and provide an optimized build for production.
- **Tailwind CSS**: A utility-first CSS framework to style the CV efficiently and consistently.

---

## Step 1: Setting Up the Project Environment

#### Create a new project folder and initialize Vite.

- Open your terminal and run:

```bash
pnpm create vite recipe-page
cd recipe-page
pnpm install
```

- This sets up a basic project structure with Vite as the build tool. Vite provides faster development and better performance.

#### Install Tailwind CSS.

- Run the following commands to set it up:

```bash
pnpm install -D tailwindcss postcss autoprefixer
pnpx tailwindcss init -p
```

- Update the `tailwind.config.js` file:
- In this `tailwind.config.js` we have added our custom colors and font family, `serif: ["Young Serif", "serif"],` and `sans: ["Outfit", "sans-serif"]`

  ```javascript
  /** @type {import('tailwindcss').Config} */
  export default {
    content: ["*.html"],
    theme: {
      extend: {
        colors: {
          stone: {
            100: "hsl(30, 54%, 90%)",
            150: "hsl(30, 18%, 87%)",
            600: "hsl(30, 10%, 34%)",
            900: "hsl(24, 5%, 18%)",
          },
          brown: {
            800: "hsl(14, 45%, 36%)",
          },
          rose: {
            50: "hsl(330, 100%, 98%)",
            800: "hsl(332, 51%, 32%)",
          },
        },
        fontFamily: {
          serif: ["Young Serif", "serif"],
          sans: ["Outfit", "sans-serif"],
        },
      },
    },
    plugins: [],
  };
  ```

- Add the Tailwind directives and import fonts to your `src/styles.css`:


  ```css
  @import url("https://fonts.googleapis.com/css2?family=Young+Serif&display=swap");
  @import url("https://fonts.googleapis.com/css2?family=Outfit:wght@400;600;700&display=swap");

  @tailwind base;
  @tailwind components;
  @tailwind utilities;
  ```

- Mention starting the dev server:

```bash
pnpm run dev
```

- Tailwind CSS provides pre-built utility classes that simplify styling, and configuring the content ensures unused CSS is purged in production

---
