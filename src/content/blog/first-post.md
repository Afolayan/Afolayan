---
title: 'Building a Personal Blog with Astro'
description: 'A walkthrough of why I chose Astro for my personal blog and the key decisions that shaped this site.'
pubDate: 'Feb 20 2026'
heroImage: '/assets/blog/blog-placeholder-3.jpg'
---

I recently rebuilt my personal blog using Astro, and I want to share the reasoning behind that choice and a few things I learned along the way.

## Why Astro?

When I started looking for a framework, my main requirements were simple: fast page loads, Markdown support for writing, and minimal JavaScript shipped to the browser. Astro checks all three boxes.

Astro generates static HTML by default. Unlike React-based frameworks that ship a JavaScript runtime to the client, Astro strips out all JS unless you explicitly opt in with client directives. For a content-heavy site like a blog, this means pages load almost instantly.

## The Stack

Here's what powers this site:

- **Astro** for the framework and static site generation
- **Tailwind CSS** for styling without writing custom CSS classes
- **MDX** for blog posts that can embed components when needed
- **RSS** and **Sitemap** integrations for discoverability

The entire project structure is straightforward:

```
src/
  content/blog/    # Markdown blog posts
  components/      # Reusable Astro components
  layouts/         # Page layouts
  pages/           # Route-based pages
  styles/          # Global CSS
```

## Content Collections

Astro's content collections feature is one of its strongest selling points. You define a schema for your blog posts using Zod, and Astro validates every post at build time:

```typescript
import { defineCollection, z } from 'astro:content';

const blog = defineCollection({
  schema: z.object({
    title: z.string(),
    description: z.string(),
    pubDate: z.coerce.date(),
    heroImage: z.string().optional(),
  }),
});
```

If I forget a required field or use the wrong date format, the build fails with a clear error message. This catches mistakes before they reach production.

## Performance Results

After deploying, I ran Lighthouse and the results speak for themselves: 100 across the board for Performance, Accessibility, Best Practices, and SEO. That's the advantage of shipping zero JavaScript by default.

## What I'd Do Differently

If I were starting over, I'd set up image optimization from day one. Astro has a built-in `<Image>` component that handles responsive images and format conversion, but I initially used regular `<img>` tags and had to go back and update them.

I'd also plan the content structure earlier. Moving blog posts between directories after you've published URLs is a pain.

## Wrapping Up

Astro is an excellent choice for content-focused sites. The developer experience is smooth, the output is fast, and the ecosystem is growing steadily. If you're thinking about starting a blog, give it a look.
