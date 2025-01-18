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

## Step 2: Structuring the Page

In this step, we'll create the structure of our recipe page by dividing it into logical sections. Let’s get started!

### Start with the HTML Skeleton

Open your `index.html` file and make sure it has the standard HTML boilerplate:

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Recipe Page</title>
  </head>
  <body></body>
</html>
```

### Add the Main Page Structure

Next, we'll divide the body tag into sections:

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Recipe Page</title>
  </head>
  <body>
    <!-- Header Section -->
    <header></header>

    <!-- Main Website Section -->
    <main>
      <!-- Info Section -->
      <section></section>
      <hr />

      <!-- Instructions Section -->
      <section></section>
      <hr />

      <!-- Nutrition Section -->
      <section></section>
    </main>

    <!-- Footer Section -->
    <footer></footer>
  </body>
</html>
```

### Save Your Work

Make sure to save the file. Our structure is now ready, and in the next step, we’ll start filling these sections with content.

# Step 3: Styling the Body and Layout

In this step, we’ll focus on enhancing the layout and appearance of our page by adding some styling to the `body` and overall layout structure.

### Add a Background and Padding to the Body

To give the page a subtle background and some breathing space, we’ll style the `body` element:

```html
<body class="bg-stone-100 md:py-10">
  <div class="max-w-4xl bg-white md:rounded-md md:p-5 mx-auto sm:p-5">
    <!-- Content goes here -->
  </div>
</body>
```

#### Explanation:

- `bg-stone-100`: A light stone-gray background color for the body.
- `md:py-10`: Adds vertical padding on medium and larger screens for better spacing.

#### Create a Centered Container

```html
<div class="max-w-4xl bg-white md:rounded-md md:p-5 mx-auto sm:p-5">
  <!-- Content goes here -->
</div>
```

#### Styling:

- `max-w-4xl`: Sets a maximum width for the container, keeping the content neat and centered.
- `bg-white`: Adds a white background to the container for contrast against the body.
- `md:rounded-md`: Adds slightly rounded corners on medium and larger screens.
- `md:p-5` and `sm:p-5`: Adds padding inside the container for a clean layout.
- `mx-auto`: Centers the container horizontally.

#### Add the Header with an Image

```html
<header class="w-full aspect-[16/9]">
  <img
    src="/images/image-omelette.jpeg"
    alt="roti with greens and meat"
    class="w-full h-full object-cover sm:rounded-lg"
  />
</header>
```

#### Styling:

- `w-full`: Ensures the header spans the full width of the container.
- `aspect-[16/9]`: Maintains a 16:9 aspect ratio for the header, making it visually appealing.
- `img` styles:
  - `w-full h-full object-cover`: Ensures the image covers the entire header area without distortion.
  - `sm:rounded-lg`: Adds rounded corners to the image on smaller screens and larger.

#### Save and Preview

Save the file and preview the page in your browser. You should see:
A centered white container with a light gray background.
A visually appealing header image with rounded corners.

```html
<body class="bg-stone-100 md:py-10">
  <div class="max-w-4xl bg-white md:rounded-md md:p-5 mx-auto sm:p-5">
    <header class="w-full aspect-[16/9]">
      <img
        src="/images/image-omelette.jpeg"
        alt="roti with greens and meat"
        class="w-full h-full object-cover sm:rounded-lg"
      />
    </header>
    <main></main>
  </div>
</body>
```

## Step 4: Styling individual sections within the layout!

### Adding and Styling Title and Description

In this step, we will add a recipe title and description to the webpage. The title will be styled to make it bold and prominent, while the description will have a subtle and clean appearance to complement the design. These elements will help introduce the recipe to the user in an appealing manner.

### HTML and Styling

Below is the complete structure for the title and description, integrated with the previous layout:

```html
<body class="bg-stone-100 md:py-10">
  <div class="max-w-4xl bg-white md:rounded-md md:p-5 mx-auto sm:p-5">
    <!-- Header Section -->
    <header class="w-full aspect-[16/9]">
      <img
        src="/images/image-omelette.jpeg"
        alt="roti with greens and meat"
        class="w-full h-full object-cover sm:rounded-lg"
      />
    </header>

    <!-- Main Section -->
    <main>
      <!-- Recipe Title -->
      <h1 class="font-serif text-5xl py-4">Simple Omelette Recipe</h1>

      <!-- Recipe Description -->
      <p class="text-stone-600 py-4">
        An easy and quick dish, perfect for any meal. This classic omelette
        combines beaten eggs cooked to perfection, optionally filled with your
        choice of cheese, vegetables, or meats.
      </p>
    </main>
  </div>
</body>
```

### Save and Preview

# Adding the Preparation Time and Ingredients Section

In this step, we will define a structured section with preparation time details and a list of ingredients. We'll use semantic HTML and apply styling for a clean and readable layout.

---

### Preparation Time

We’ll use an `<article>` element for the preparation time details.

```html
<section class="py-4">
  <article class="p-4 bg-rose-50 rounded-md">
    <h2 class="text-rose-800 font-sans font-semibold">Preparation time</h2>
    <ul>
      <li class="list-disc list-inside">
        <span class="font-semibold">Total</span>: Approximately 10 minutes
      </li>
      <li class="list-disc list-inside">
        <span class="font-semibold">Preparation</span>: 5 minutes
      </li>
      <li class="list-disc list-inside">
        <span class="font-semibold">Cooking</span>: 5 minutes
      </li>
    </ul>
  </article>
</section>
```

#### Styling:

- `p-4`: Adds padding inside the article for a comfortable layout.
- `bg-rose-50`: Sets a soft rose background color for visual distinction.
- `rounded-md`: Adds rounded corners for a softer appearance.
- `text-rose-800`: Ensures the heading text contrasts well with the background.
- `list-disc list-inside`: Displays bullet points with indentation inside the `<ul>`.

### Ingredients

We’ll list the ingredients under another `<article>` element.

```html
<article>
  <h2 class="py-4 font-serif text-brown-800 text-2xl">Ingredients</h2>
  <ul class="list-disc list-inside">
    <li>2-3 large eggs</li>
    <li>Salt, to taste</li>
    <li>Pepper, to taste</li>
    <li>1 tablespoon of butter or oil</li>
    <li>Optional fillings: cheese, diced vegetables, cooked meats, herbs</li>
  </ul>
</article>
```

#### Styling:

- `py-4`: Adds vertical padding to space out the heading.
- `font-serif`: Applies a serif font for the ingredients heading.
- `text-brown-800`: Uses a brown color for a warm and organic feel.
- `text-2xl`: Ensures the heading stands out by increasing its size.
- `list-disc list-inside`: Maintains consistency with bullet-point styling.

### Add a Horizontal Rule

Insert an `<hr />` tag to visually separate the section.

```html
<hr />
```

### Final Section Code

```html
<section class="py-4">
  <article class="p-4 bg-rose-50 rounded-md">
    <h2 class="text-rose-800 font-sans font-semibold">Preparation time</h2>
    <ul>
      <li class="list-disc list-inside">
        <span class="font-semibold">Total</span>: Approximately 10 minutes
      </li>
      <li class="list-disc list-inside">
        <span class="font-semibold">Preparation</span>: 5 minutes
      </li>
      <li class="list-disc list-inside">
        <span class="font-semibold">Cooking</span>: 5 minutes
      </li>
    </ul>
  </article>
  <article>
    <h2 class="py-4 font-serif text-brown-800 text-2xl">Ingredients</h2>
    <ul class="list-disc list-inside">
      <li>2-3 large eggs</li>
      <li>Salt, to taste</li>
      <li>Pepper, to taste</li>
      <li>1 tablespoon of butter or oil</li>
      <li>Optional fillings: cheese, diced vegetables, cooked meats, herbs</li>
    </ul>
  </article>
</section>
<hr />
```

# Adding Instructions and Nutrition Sections

This guide focuses on creating a clear set of cooking instructions and a nutrition facts table. Both sections will be styled for clarity and usability.

---

## Instructions Section

We'll use an ordered list (`<ol>`) to show step-by-step instructions.

```html
<section class="py-4">
  <h2 class="py-4 font-serif text-brown-800 text-2xl">Instructions</h2>
  <ol class="list-decimal list-inside">
    <li>
      <span class="font-semibold">Beat the eggs</span>: In a bowl, beat the eggs
      with a pinch of salt and pepper until they are well mixed. You can add a
      tablespoon of water or milk for a fluffier texture.
    </li>
    <li>
      <span class="font-semibold">Heat the pan</span>: Place a non-stick frying
      pan over medium heat and add butter or oil.
    </li>
    <li>
      <span class="font-semibold">Cook the omelette</span>: Once the butter is
      melted and bubbling, pour in the eggs. Tilt the pan to ensure the eggs
      evenly coat the surface.
    </li>
    <li>
      <span class="font-semibold">Add fillings (optional)</span>: When the eggs
      begin to set at the edges but are still slightly runny in the middle,
      sprinkle your chosen fillings over one half of the omelette.
    </li>
    <li>
      <span class="font-semibold">Fold and serve</span>: As the omelette
      continues to cook, carefully lift one edge and fold it over the fillings.
      Let it cook for another minute, then slide it onto a plate.
    </li>
    <li>
      <span class="font-semibold">Enjoy</span>: Serve hot, with additional salt
      and pepper if needed.
    </li>
  </ol>
</section>
```

#### Styling:

`py-4`: Adds vertical padding to the section.
`font-serif text-brown-800 text-2xl`: Styles the heading with a serif font, brown color, and large size.
`list-decimal list-inside`: Ensures a numbered list with indentation.

### Nutrition Section

We'll use a table for the nutritional facts.

```html
<section class="py-4">
  <h2 class="py-4 font-serif text-brown-800 text-2xl">Nutrition</h2>
  <p class="pb-4">
    The table below shows nutritional values per serving without the additional
    fillings.
  </p>
  <table class="w-full py-4">
    <tr class="border-b border-gray-200 h-10 px-4">
      <td>Calories</td>
      <td class="text-brown-800 font-semibold">277kcal</td>
    </tr>
    <tr class="border-b border-gray-200 h-10 px-4">
      <td>Carbs</td>
      <td class="text-brown-800 font-semibold">0g</td>
    </tr>
    <tr class="border-b border-gray-200 h-10 px-4">
      <td>Protein</td>
      <td class="text-brown-800 font-semibold">20g</td>
    </tr>
    <tr class="border-b border-gray-200 h-10 px-4">
      <td>Fat</td>
      <td class="text-brown-800 font-semibold">22g</td>
    </tr>
  </table>
</section>
<hr />
```

#### Styling:

`w-full`: Ensures the table spans the full width of the section.
`border-b border-gray-200`: Adds a subtle border below each row for better readability.
`h-10`: Adjusts the height of rows for a cleaner layout.
`text-brown-800 font-semibold`: Highlights the values in bold brown text for emphasis.

### Final Section Code

```html
<section class="py-4">
  <h2 class="py-4 font-serif text-brown-800 text-2xl">Instructions</h2>
  <ol class="list-decimal list-inside">
    <li>
      <span class="font-semibold">Beat the eggs</span>: In a bowl, beat the eggs
      with a pinch of salt and pepper until they are well mixed. You can add a
      tablespoon of water or milk for a fluffier texture.
    </li>
    <li>
      <span class="font-semibold">Heat the pan</span>: Place a non-stick frying
      pan over medium heat and add butter or oil.
    </li>
    <li>
      <span class="font-semibold">Cook the omelette</span>: Once the butter is
      melted and bubbling, pour in the eggs. Tilt the pan to ensure the eggs
      evenly coat the surface.
    </li>
    <li>
      <span class="font-semibold">Add fillings (optional)</span>: When the eggs
      begin to set at the edges but are still slightly runny in the middle,
      sprinkle your chosen fillings over one half of the omelette.
    </li>
    <li>
      <span class="font-semibold">Fold and serve</span>: As the omelette
      continues to cook, carefully lift one edge and fold it over the fillings.
      Let it cook for another minute, then slide it onto a plate.
    </li>
    <li>
      <span class="font-semibold">Enjoy</span>: Serve hot, with additional salt
      and pepper if needed.
    </li>
  </ol>
</section>
<hr />
<section class="py-4">
  <h2 class="py-4 font-serif text-brown-800 text-2xl">Nutrition</h2>
  <p class="pb-4">
    The table below shows nutritional values per serving without the additional
    fillings.
  </p>
  <table class="w-full py-4">
    <tr class="border-b border-gray-200 h-10 px-4">
      <td>Calories</td>
      <td class="text-brown-800 font-semibold">277kcal</td>
    </tr>
    <tr class="border-b border-gray-200 h-10 px-4">
      <td>Carbs</td>
      <td class="text-brown-800 font-semibold">0g</td>
    </tr>
    <tr class="border-b border-gray-200 h-10 px-4">
      <td>Protein</td>
      <td class="text-brown-800 font-semibold">20g</td>
    </tr>
    <tr class="border-b border-gray-200 h-10 px-4">
      <td>Fat</td>
      <td class="text-brown-800 font-semibold">22g</td>
    </tr>
  </table>
</section>
```

With these sections added, your recipe layout will be informative, visually appealing, and easy to follow!

## Adding Footer

```html
<footer class="attribution py-4">
  Challenge by
  <a
    href="https://www.frontendmentor.io?ref=challenge"
    rel="noopener"
    target="_blank"
    >Frontend Mentor</a
  >. Coded by <a href="https://www.jacobc.co.za/">Jacob Chademwiri</a>.
</footer>
```
