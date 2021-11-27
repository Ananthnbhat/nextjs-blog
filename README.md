This is a starter template for [Learn Next.js](https://nextjs.org/learn).

Run below command start the dev server:

```javascript
npm run dev
```

* routing using file system inside the pages folder

* layout.js acts like the root component App.js

* layout.js uses CSS-Modules for css

* The App component (\_app.js) is the top-level component which will be common across all the different pages. This is the only
place where we import the global css (global.css), which will be applied for each and every page.

Pre-rendering: There are 2 types: Static generation & Server-side rendering.

Static Generation: is the pre-rendering method that generates the HTML at **build time**. The pre-rendered HTML is then reused on each request. (using getStaticProps)

Server-side Rendering: is the pre-rendering method that generates the HTML on each request during **request time**. (using getServerSideProps)

Static generation: if a component needs data before mounting, then that is Static generation with data (use getStaticProps). if a component dpesn't need data before mounting, then that is Static generation without data

#### Development vs. Production

In development (npm run dev or yarn dev), getStaticProps runs on every request.

In production, getStaticProps runs at **build time**. However, this behavior can be enhanced using the fallback key returned by getStaticPaths

Because it’s meant to be run at build time, you won’t be able to use data that’s only available during request time, such as query parameters or HTTP headers (use server-side rendering in this case).

#### Only Allowed in a Page

getStaticProps can only be exported from a page. You can’t export it from non-page files.

If you do not need to pre-render the data, you can also use the following strategy called **Client-side Rendering**:

- Statically generate (pre-render) parts of the page that do not require external data.
- When the page loads, fetch external data from the client using JavaScript and populate the remaining parts.

This approach works well for user dashboard pages. Because a dashboard is a private, user-specific page, SEO is not relevant, and the page doesn’t need to be pre-rendered. The data is frequently updated, which requires request-time data fetching.
