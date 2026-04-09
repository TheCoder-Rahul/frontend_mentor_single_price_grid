# Frontend Mentor - Single price grid component solution

This is a solution to the [Single price grid component challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/single-price-grid-component-5ce41129d0ff452fec5abbbc). Frontend Mentor challenges help you improve your coding skills by building realistic projects. 

## Table of contents

- [Overview](#overview)
  - [The challenge](#the-challenge)
  - [Screenshot](#screenshot)
  - [Links](#links)
- [My process](#my-process)
  - [Built with](#built-with)
  - [What I learned](#what-i-learned)
- [Author](#author)

## Overview

### The challenge

Users should be able to:

- View the optimal layout for the component depending on their device's screen size
- See a hover state on desktop for the Sign Up call-to-action

### Screenshot

![Design screenshot](https://github.com/TheCoder-Rahul/frontend_mentor_single_price_grid/blob/main/project_screenshot.png)

### Links

- 👉 [Solution URL](https://github.com/TheCoder-Rahul/frontend_mentor_single_price_grid.git)
- 👉 [Live Site URL](https://thecoder-rahul.github.io/frontend_mentor_single_price_grid/)

## My process

### Built with

- 👉 **Markup:** Semantic HTML5 for better accessibility and SEO.
- 👉 **Styling:** CSS3 with Custom Properties (variables) for a maintainable color scheme, font-properties, and different sizes.
- 👉 **Layout:** Flexbox for centering the card and managing the internal alignment.
- 👉 **Workflow:** Mobile-first approach and Responsive Design using Media Queries.

### What I learned

Check my code snippets below:

```html
<main>
  <section class="intro">
    <h1>Join our community</h1>
    <h2>30-day, hassle-free money back guarantee</h2>
    <p>Gain access to our full library of tutorials along with expert code reviews. Perfect for any developers who are serious about honing their skills.</p>
  </section>
  <section class="susbcription">
    <h3>Monthly Subscription</h3>
    <p class="plan">&dollar;29 <span>per month</span></p>
    <p>Full access for less than &dollar;1 a day</p>
    <button type="button" class="btn">Sign Up</button>
  </section>
  <section class="reason">
    <h3>Why Us</h3>
    <ul>
      <li>Tutorials by industry experts</li>
      <li>Peer &amp; expert code review</li>
      <li>Coding exercises</li>
      <li>Access to our GitHub repos</li>
      <li>Community forum</li>
      <li>Flashcard decks</li>
      <li>New videos every week</li>
    </ul>
  </section>
</main>
```
```css
*, *::before, *::after {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
:root {
  --body-size: 1rem;
  --white: hsl(0, 0%, 100%);
  --teal-100: hsl(204, 43%, 93%);
  --gray-500: hsl(218, 22%, 67%);
  --teal-500: hsl(179, 62%, 43%);
  --green-300: hsl(61, 93%, 84%);
  --green-400: hsl(71, 73%, 54%);
  --font: "Karla", sans-serif;
}
body {
  display: flex;
  min-height: 100vh;
  align-items: center;
  color: var(--gray-500);
  flex-direction: column;
  font-family: var(--font);
  font-size: var(--body-size);
  justify-content: space-between;
  background-color: var(--teal-100);
}
main {
  display: grid;
  overflow: clip;
  width: min(40rem, 90%);
  background-color: var(--white);
  border-radius: calc(var(--body-size) / 4);
  box-shadow: 0 1rem 2rem hsla(179, 82%, 23%, 0.2);
  margin: clamp(2.5rem, calc(var(--body-size) * 3 + 10vw), 10rem);
}
h1 {
  color: var(--teal-500);
  margin-block-end: 1.5rem;
  font-size: clamp(1.125rem, calc(1vw + 1rem), 1.5rem);
}
h2 {
  margin-block-end: 1rem;
  color: var(--green-400);
  font-size: clamp(0.875rem, calc(1vw + 0.75rem), 1.125rem);
}
h3 {
  margin-block-end: 1.5rem;
}
.intro {
  padding: clamp(1.25rem, calc(var(--body-size) * 1.25 + 1vw), 3rem);
}
.intro p {
  line-height: 1.5;
  font-size: clamp(0.75rem, calc(1vw + 0.65rem), 1rem);
}
.susbcription, .reason {
  color: var(--white);
  padding: clamp(1.25rem, calc(var(--body-size) * 1.25 + 1vw), 3rem);
  background-color: var(--teal-500);
}
.susbcription {
  background-color: hsl(179, 90%, 35%);

  & .plan {
    gap: 1rem;
    display: flex;
    font-weight: bold;
    align-items: center;
    margin-block-end: 0.5rem;
    font-size: calc(var(--body-size) * 2);
    & span {
      opacity: 0.75;
      font-weight: 100;
      font-size: var(--body-size);
    }
  }

  & .btn {
    width: stretch;
    cursor: pointer;
    line-height: 1.5;
    font-weight: 700;
    color: var(--green-300);
    margin-block-start: 2rem;
    font-family: var(--font);
    border-color: transparent;
    font-size: var(--body-size);
    padding: 0.75rem var(--body-size);
    background-color: var(--green-400);
    border-radius: calc(var(--body-size) / 4);
    -webkit-transition: all 0.3s ease-in-out;
    -moz-transition: all 0.3s ease-in-out;
    -ms-transition: all 0.3s ease-in-out;
    -o-transition: all 0.3s ease-in-out;
    transition: all 0.3s ease-in-out;
    box-shadow: 0 0.5rem 1rem -0.5rem hsla(179, 88%, 10%, 0.5);

    &:hover, &:focus {
      color: hsl(179, 88%, 10%);
      border-radius: calc(var(--body-size) / 2);
      transform: scale(1.025) translateY(-0.125rem);
    }
  }
}
ul {
  list-style: none;
  line-height: 1.5;
  font-weight: lighter;
  font-size: clamp(0.75rem, calc(1vw + 0.65rem), 0.875rem);
}
.attribution { font-size: 0.6875rem; text-align: center; }
.attribution a { color: hsl(228, 45%, 44%); }
@media (min-width: 48rem) {
  main {
    margin-block: auto;
    grid-template-columns: repeat(2, 1fr);
    border-radius: calc(var(--body-size) / 2);
  }
  .intro {
    grid-column: span 2;
  }
}
```

## Author

- 👉 GitHub - [TheCoder-Rahul](https://github.com/TheCoder-Rahul)
- 👉 Frontend Mentor - [@TheCoder-Rahul](https://www.frontendmentor.io/profile/TheCoder-Rahul)
- 👉 LinkedIn - [@Rahul Kumar](https://www.linkedin.com/in/rahul-the-developer/)