# NextJS notes

## Command to create a new project

> npx create-next-app@latest nextjs-blog --use-npm --example "https://github.com/vercel/next-learn/tree/master/basics/learn-starter"

## File System Routing

#### Link Tag

- Very similar to anchor tag, helps in redirecting to pages.
- This is client side navigation using JavaScript.
- Also , enables NextJs to do code splitting, i.e. each page only loads the code that is necessary for that page.
- In production environment, NextJS prefetches all the lnked pages for faster loading

## Assets

#### Image Tag

Drawbacks of adding images using an `img` tag:

Have to handle
- Ensuring your image is responsive on different screen sizes
- Optimizing your images with a third-party tool or library
- Only loading images when they enter the viewport

These cases are automatically handled by NextJS's `Image` component

## Meta Data and CSS

#### Head Tag

Allows you to change the Data in `head` tag of the page

#### Script Tag

Used to add third party scripts. Normal `<script>` tag will also work but it sometimes fails to deal with the dynamic loading mechanisms of NextJS

#### Styling

CSS, SaSS and Styled Objects are supported

Two types of CSS Modules
- Module level (module.css extension)
- Global Level (.css extension) : can only be imported in _app.js

## Pre - Rendering

- By default, Next.js pre-renders every page. This means that Next.js generates HTML for each page in advance, instead of having it all done by client-side JavaScript. 
- Pre-rendering can result in better performance and SEO.
- Each generated HTML is associated with minimal JavaScript code necessary for that page. 
- When a page is loaded by the browser, its JavaScript code runs and makes the page fully interactive. (This process is called hydration.)

**NextJS uses 2 types of pre-rendering**

1. Static Generation is the pre-rendering method that generates the HTML at build time. The pre-rendered HTML is then reused on each request.
2. Server-side Rendering is the pre-rendering method that generates the HTML on each request.

#### Static Generation with Data

If a page doesn't require fetching external data it is automatically generated using static generation.

But if there are any dependencies then NextJS uses `getStaticProps`

**How does `getStaticProps` work**

In Next.js, when you export a page component, you can also export an async function called getStaticProps. If you do this, then:

- getStaticProps runs at build time in production, and…
- Inside the function, you can fetch external data and send it as props to the page.
- If you want to fetch the data at build time use Static Rendering
- If you want to fetch the data at the time at which the request is sent use Server-side rendering
- For using Server-Side rendering use `getServerSideProps` instead of `getStaticProps`
- The team behind Next.js has created a React hook for data fetching called SWR.

## Important concepts 

- [File System Routing](https://nextjs.org/docs/routing/introduction)
- [Fast Refresh](https://nextjs.org/docs/basic-features/fast-refresh)
- [Pages](https://nextjs.org/docs/basic-features/pages)
- [_app.js](https://nextjs.org/docs/advanced-features/custom-app)
- [Styling Tips](https://nextjs.org/learn/basics/assets-metadata-css/styling-tips)
- [`getStaticProp` Tips](https://nextjs.org/learn/basics/data-fetching/getstaticprops-details)
- [SWR Documentation](https://swr.vercel.app/)
- [Dynamic Routes Tip](https://nextjs.org/learn/basics/dynamic-routes/dynamic-routes-details)


