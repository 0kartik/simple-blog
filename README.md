# Kartikeya's Blog — Built on Simple

A customized static blog generator. Write posts in Markdown, publish instantly to GitHub Pages — no server, no database, no build step required.

---

## What this is

Simple is a single-page blog engine that talks directly to the GitHub API from your browser. Every time you save a post, it commits a static HTML file to your `username.github.io` repo, which GitHub Pages serves for free. This fork is styled and configured for personal use by Kartikeya.

---

## Getting started

### 1. Set up GitHub Pages

Create a repo named exactly `kartikeya.github.io` on GitHub. Check the box to initialize it with a README so the repo isn't empty.

### 2. Deploy the blog engine

Clone this repo, then push the entire `src/` folder to a `gh-pages` branch:

```bash
git clone https://github.com/kartikeya/<this-repo>.git
cd <this-repo>
git subtree push --prefix src origin gh-pages
```

### 3. Initialize your blog

Open `https://kartikeya.github.io/simple` in your browser, sign in with your GitHub credentials, and click **Initialize**. This copies the template files into your `kartikeya.github.io` repo.

### 4. Start writing

Click **Go**, then **New post**. Write in Markdown. Click **Save** — your post is live.

---

## Configuration

All blog settings live in `src/template/main.json`:

## Features

- No backend — runs entirely in the browser
- Writes directly to GitHub via the GitHub API
- Markdown editor with live preview
- Syntax highlighting (Prism.js)
- LaTeX / TeX formula support (MathJax)
- Drag-and-drop image upload to your repo
- Tag system and archive view
- Responsive layout
- Dark mode (added in this fork)

---

## Folder structure

```
src/
├── app.js               # Main application logic (GitHub API calls, routing)
├── editor.html          # Standalone Markdown editor
├── index.html           # Blog engine entry point (login + post management)
├── css/
│   ├── bootstrap.min.css
│   ├── main.css
│   └── loading.css
├── lib/
│   ├── github.js        # GitHub API wrapper
│   ├── showdown.js      # Markdown → HTML converter
│   ├── spine.js         # MVC framework
│   └── ...
└── template/            # ← Edit these to customize your blog
    ├── index.html       # Blog homepage template
    ├── post.html        # Post page template
    ├── page.html        # Static page template
    ├── main.json        # Blog config and post index
    ├── main.css         # Compiled stylesheet (auto-generated)
    ├── main.js          # Compiled JS (auto-generated)
    └── css/
        ├── style.css    # Homepage styles (source)
        ├── entry.css    # Post content styles (source)
        └── darkmode.css # Dark mode (added in this fork)
```

---

## Local development

```bash
npm install
grunt
```

Grunt compiles `src/template/css/` and `src/template/js/` into `main.css` and `main.js`. Open `src/index.html` in a browser to run locally (you'll still need internet access for the GitHub API calls).

---

## Roadmap

- [x] Dark mode
- [ ] Full-text search (Pagefind)
- [ ] RSS feed auto-generation
- [ ] SEO meta tags (Open Graph, sitemap)
- [ ] OAuth login (replace basic auth)
- [ ] Reading time on post listings

---

## License

Licensed by Kartikeya.