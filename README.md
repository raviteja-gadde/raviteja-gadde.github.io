# raviteja-gadde.github.io

Personal site and blog, served by GitHub Pages from `main`. Plain HTML and CSS, no build step.

## Structure

```
index.html      home page: about + article list with excerpts
style.css       shared styles (index and article pages)
posts/          one HTML file per article: YYYY-MM-DD-slug.html
```

## Adding an article

1. Create `posts/YYYY-MM-DD-slug.html` using the template below.
2. Add an entry to the `<section class="articles">` in `index.html` (newest first):
   ```html
   <article>
     <h2><a href="posts/YYYY-MM-DD-slug.html">Title</a></h2>
     <time datetime="YYYY-MM-DD">Month DD, YYYY</time>
     <p class="excerpt">Opening 2-3 sentences — what the reader gets from this piece.</p>
   </article>
   ```
3. Commit and push. Pages rebuilds in about a minute.

## Article template

```html
<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>TITLE — Ravi Teja Gadde</title>
  <meta name="description" content="DESCRIPTION">
  <meta name="author" content="Ravi Teja Gadde">
  <link rel="stylesheet" href="../style.css">
  <script type="application/ld+json">
  {
    "@context": "https://schema.org",
    "@type": "BlogPosting",
    "headline": "TITLE",
    "datePublished": "YYYY-MM-DD",
    "author": {
      "@type": "Person",
      "name": "Ravi Teja Gadde",
      "url": "https://raviteja-gadde.github.io"
    },
    "url": "https://raviteja-gadde.github.io/posts/YYYY-MM-DD-slug.html"
  }
  </script>
</head>
<body>
<div class="page">
  <nav aria-label="Back">
    <a href="/" class="back-link">← All articles</a>
  </nav>
  <article>
    <header class="article-header">
      <h1>TITLE</h1>
      <time datetime="YYYY-MM-DD">Month DD, YYYY</time>
    </header>
    <div class="article-body">
      <!-- Article content: <p>, <h2>, <pre><code>, <blockquote> -->
    </div>
  </article>
  <footer class="site-footer">
    <a href="/">← All articles</a>
  </footer>
</div>
</body>
</html>
```

## Agent-friendliness

- Semantic HTML5 elements (`<article>`, `<nav>`, `<time>`, `<header>`, `<section>`)
- JSON-LD structured data: `Blog` on index, `BlogPosting` on each article
- No JS dependency for content — everything is in the HTML
- Clean URL structure: `/posts/YYYY-MM-DD-slug.html`

## Design

- System fonts, no external dependencies, self-contained
- Light/dark theme via `prefers-color-scheme`
- Mobile-responsive, single-column layout
