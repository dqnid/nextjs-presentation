## Server components

## Presentation flow
1. Introduction without strategies.
2. Benefits.
3. Actual process and why its important to know it.
4. Brief introduction to strategies.

### Introduction

UI rendered in the server and optionally cached. Split by route segments and 3
strategies:

- Static Rendering (default)
- Dynamic Rendering
- Streaming

### Benefits

- Fetch data directly on the server, performance and load benefits.
- Security: sensitive data is kept int the server (API keys and tokens)
- Caching: results can be cached to improve performance between users.
- Bundle size: will be reduced as part of the application will reside in the
  server.
- SEO: because the pages will be rendered the search engine bots will make good
  use of it.
- Streaming: to split the rendering into chunks and stream them as they become
  ready.

### Process of rendering

The rendering works is split into chunks:

- By individual route segments
- By React Suspense boundaries (react way of having a fallback while a
  components has finished loading) Each chunk is rendered in the server, then,
  on the client:

1. The HTML is used to immediately show fast preview.
2. The server components rendered are inserted to update the DOM (components
   rendered in server with placeholders for client components and props).
3. `JS` instructions are used to hydrate? Client Components and make the
   application interactive.

### Strategies

- Static rendering

