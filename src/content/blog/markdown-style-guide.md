---
title: 'Markdown Style Guide'
description: 'A reference for the Markdown syntax supported in this blog, with examples of headings, lists, code blocks, and more.'
pubDate: 'Feb 01 2026'
heroImage: '/assets/blog/blog-placeholder-1.jpg'
---

This post serves as a reference for the Markdown syntax you can use when writing content for an Astro blog. It's also a useful test page to verify that all formatting renders correctly.

## Headings

The following HTML `<h1>`—`<h6>` elements represent six levels of section headings. `<h1>` is the highest section level while `<h6>` is the lowest.

# H1

## H2

### H3

#### H4

##### H5

###### H6

## Paragraph

Standard paragraph text renders with comfortable line height and spacing. Multiple paragraphs are separated by blank lines in the source Markdown.

This is a second paragraph demonstrating the spacing between blocks of text.

## Blockquotes

The blockquote element represents content quoted from another source.

> Don't communicate by sharing memory, share memory by communicating.<br>
> — <cite>Rob Pike[^1]</cite>

[^1]: From Rob Pike's talk during Gopherfest, November 18, 2015.

## Tables

| Feature    | Markdown | MDX   |
| ---------- | -------- | ----- |
| Headings   | Yes      | Yes   |
| Components | No       | Yes   |
| JSX        | No       | Yes   |
| File ext   | `.md`    | `.mdx`|

## Code Blocks

Syntax-highlighted code blocks are supported for many languages:

```typescript
interface BlogPost {
  title: string;
  description: string;
  pubDate: Date;
  heroImage?: string;
}

function getLatestPosts(posts: BlogPost[], count: number): BlogPost[] {
  return posts
    .sort((a, b) => b.pubDate.getTime() - a.pubDate.getTime())
    .slice(0, count);
}
```

## Lists

### Ordered List

1. First item
2. Second item
3. Third item

### Unordered List

- List item
- Another item
- And another item

### Nested list

- Frontend
  - React
  - Astro
  - Tailwind
- Backend
  - Node.js
  - Python
  - PostgreSQL

## Other Elements

<abbr title="Graphics Interchange Format">GIF</abbr> is a bitmap image format.

H<sub>2</sub>O

X<sup>n</sup> + Y<sup>n</sup> = Z<sup>n</sup>

Press <kbd>CTRL</kbd> + <kbd>ALT</kbd> + <kbd>Delete</kbd> to end the session.

Most <mark>salamanders</mark> are nocturnal, and hunt for insects, worms, and other small creatures.
