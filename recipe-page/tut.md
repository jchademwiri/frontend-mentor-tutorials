# Creating a Single-Page CV with HTML

## Introduction

#### Welcome your viewers and introduce yourself.

- "Hi everyone, welcome back to my channel! My name is [Your Name], and today I’ll show you how to create a professional single-page CV using HTML, Vite, and Tailwind CSS."

#### Briefly explain the tools:

- **HTML**: The foundation for structuring the page.
- **Vite**: A build tool to speed up development and provide an optimized build for production.
- **Tailwind CSS**: A utility-first CSS framework to style the CV efficiently and consistently.

---

## Step 1: Setting Up the Project Environment

#### Create a new project folder and initialize Vite.

- Open your terminal and run:

```bash
pnpm create vite single-page-cv
cd single-page-cv
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
  ```javascript
  module.exports = {
    content: ["./*.html"],
    theme: {
      extend: {},
    },
    plugins: [],
  };
  ```
- Add the Tailwind directives to your `src/styles.css`:
  ```css
  @tailwind base;
  @tailwind components;
  @tailwind utilities;
  ```
- Mention starting the dev server:

```bash
pnpm run dev
```

- ailwind CSS provides pre-built utility classes that simplify styling, and configuring the content ensures unused CSS is purged in production

---

## Step 2: Structuring the HTML

#### Open `index.html` and start building the structure:

- Add meta tags for SEO and social sharing.
  ```html
  <head>
    <meta charset="UTF-8" />
    <link rel="icon" type="image/svg+xml" href="/vite.svg" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <meta
      name="description"
      content="A single-page CV built with semantic HTML."
    />
    <meta name="keywords" content="HTML, CV, Resume, Tutorial" />
    <meta name="author" content="Your Name" />
    <meta property="og:title" content="Single-Page CV Tutorial" />
    <meta
      property="og:description"
      content="Learn how to create a professional CV using semantic HTML."
    />
    <meta property="og:image" content="link-to-preview-image" />
    <meta property="og:url" content="your-tutorial-url" />
    <link rel="icon" href="favicon.ico" type="image/x-icon" />
    <title>My Single-Page CV</title>
  </head>
  ```
- Use semantic HTML to organize sections like Header, Main, and Footer.
- HTML web page skeleton:
  ```html
  <!DOCTYPE html>
  <html lang="en">
    <!-- SEO Metatags -->
    <head> </head>
    <body>
      <div class="max-w-4xl mx-auto my-4">
        <!-- HEADER -->
        <header></header>
        <!-- MAIN -->
        <main></main>
        <!-- FOOTER -->
        <footer></footer>
      </div>
    </body>
  </html>
  ```

---

## Step 3: Adding Content to the CV

- We will be using Tailwind classes for styling.

#### Header Section:

- Add your name, title, and contact details.

  ```html
  <!-- HEADER  -->
  <header class="py-4">
    <hr class="border-b-2 border-black my-8 w-full" />
    <h1 class="text-3xl">Jacob C</h1>
    <h2 class="text-green-600 font-bold">Junior Frontend Developer</h2>
    <p>
      123 Your Street<br />Your City, ST 12345<br />(123) 456-7890<br /><a
        href="mailto:no_reply@example.com"
        >no_reply@example.com</a
      >
    </p>
  </header>
  ```

#### Skills Section:

- Showcase your technical and soft skills..
  ```html
  <main>
    <!-- SKILLS  -->
    <section class="py-4">
      <h3 class="text-green-600 font-bold">Skills</h3>
      <span>
        HTML, CSS, JavaScript, Accessibility, Figma to Design, Responsive Web
        Design, Technical Writing, Presentation,
      </span>
    </section>
  </main>
  ```

#### Education Section:

- Highlight your educational background and achievements, degrees or certifications.
  ```html
  <!-- EDUCATION  -->
  <section class="py-4">
    <h3 class="text-green-600 font-bold">Education</h3>
    <article>
      <p class="text-blue-500 font-bold">School Name, Location - Degree</p>
      <p>Month 20xx to Month 20xx</p>
      <p>List of exciting things you did at university.</p>
    </article>
    <article>
      <p class="text-blue-500 font-bold">
        Certification Name, Provider - Certification
      </p>
      <p>Month 20xx to Month 20xx</p>
      <p>List certification details.</p>
    </article>
  </section>
  ```

#### Experience Section:

- Mention roles, achievements, and skills gained.
  ```html
  <!-- EXPERIENCE  -->
  <section class="py-4">
    <h3 class="text-green-600 font-bold">Experience</h3>
    <article>
      <h4 class="text-blue-500 font-bold">
        Company Name, Location - Job Title
      </h4>
      <p>Month 20xx to Month 20xx</p>
      <ul>
        <li>List of achievements</li>
        <li>List of achievements</li>
        <li>List of achievements</li>
      </ul>
      <p>Skills: List of skills used or gained at this company.</p>
    </article>
    <article>
      <h4 class="text-blue-500 font-bold">
        Company Name, Location - Job Title
      </h4>
      <p>Month 20xx to Month 20xx</p>
      <ul>
        <li>List of achievements</li>
        <li>List of achievements</li>
        <li>List of achievements</li>
      </ul>
      <p>Skills: List of skills used or gained at this company.</p>
    </article>
  </section>
  ```

---

## Step 4: Footer Section:

#### Add social media links in the footer.

- Include links to your LinkedIn, GitHub, or portfolio

  ```html
  <!-- FOOTER  -->
  <footer class="py-4">
    <h3 class="text-green-600 font-bold">Across the Internet</h3>
    <p>
      <a href="https://linkedin.com/in/jchademwiri">LinkedIn</a> |
      <a href="https://github.com/jchademwiri">GitHub</a>
    </p>
  </footer>
  ```

---

## Step 5: Styling with Tailwind CSS

#### Key Tailwind Utilities Used:

- Spacing: `my-4`, `py-4` for margin and padding.
- Typography: `text-4xl`, `font-bold` for font sizes and weights.
- Colors: `text-green-600`, `text-blue-500` for consistent color schemes.
- Layout: `max-w-4xl`, `mx-auto` for content centering and width.

---

## Step 6: Running the Project

#### Run the development server:

```bash
pnpm run dev
```

- If you found this tutorial helpful, give it a thumbs up, subscribe to my channel, and let me know in the comments what you'd like to learn next!