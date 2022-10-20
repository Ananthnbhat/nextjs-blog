---
title: "When to Use Static Generation v.s. Server-side Rendering"
date: "2022-02-02"
---

We recommend using **Static Generation** (with and without data) whenever possible because your page can be built once and served by CDN, which makes it much faster than having a server render the page on every request.

You can use Static Generation for many types of pages, including:

- Marketing pages
- Blog posts
- E-commerce product listings
- Help and documentation

You should ask yourself: "Can I pre-render this page **ahead** of a user's request?" If the answer is yes, then you should choose Static Generation.

On the other hand, Static Generation is **not** a good idea if you cannot pre-render a page ahead of a user's request. Maybe your page shows frequently updated data, and the page content changes on every request.

In that case, you can use **Server-Side Rendering**. It will be slower, but the pre-rendered page will always be up-to-date. Or you can skip pre-rendering and use client-side JavaScript to populate data.

## CSR

Client Side Rendering is the traditional way of rendering a page in the browser. A user requests for a page and server sends all the resources & scripts to the browser, then a DOM tree is formed to create a HTML page IN the browser on the client side. The rendering process takes some time during which the user has to wait.

## SSR

SSR stands for Server Side Rendering. When a user sends a request through the browser, the server receives the request, generates a complete HTML site and returns it to the browser. So, the rendering happens in the server, not in the browser. While server is rendering(generating) the HTML page, a placeholder HTML (a loader animation) can be displayed to the user instead of showing a blank screen, which is what happends in Client Side Rendering.

Next.js supports SSR out of the box ([link](https://nextjs.org/docs/advanced-features/react-18/streaming)) whereas in React 18, it can be done with a combination of React.suspense & React.lazy ([link](https://reactjs.org/docs/react-api.html#reactsuspense))

## SSG

SSG stands for Static Site Generation. It means that a static HTML page is created for every route of the website. So, when a page is displayed on the browser, it doesn't wait to download & parse all the required scripts & resources for the DOM tree. It just displays the HTML page. This makes the React js (or Next js) page looks like a simple HTML page leading to fast load time & higher performance.

Amazing resource on rehydration issue which is related to SSR/SSG - [Josh Cameau's blog](https://www.joshwcomeau.com/react/the-perils-of-rehydration/)
