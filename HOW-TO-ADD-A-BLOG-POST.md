# How To Publish A New Blog Post On Swellbridgedigital.com

Quick, no-fluff guide. The blog is a folder of HTML files. To publish a new post:

---

## Step 1: Copy an existing post as a template

The easiest one to start from is `blog/awareness-levels-eugene-schwartz-applied-to-nigeria.html` — it has a clean article structure with headings, lists, blockquotes, and a callout box.

Copy it and rename it to your new post's URL slug. The slug becomes part of the URL, so use lowercase words separated by hyphens:

✅ `how-to-write-better-ad-copy.html`
❌ `How To Write Better Ad Copy.html`

So if your post is "How to write better ad copy", the file should be at:

```
blog/how-to-write-better-ad-copy.html
```

---

## Step 2: Update the meta tags (very top of file)

Change these three things in the `<head>` section:

```html
<title>Your post title — Swellbridge Digital</title>
<meta name="description" content="Your post's 1-2 sentence summary.">
```

The title shows in Google search results and browser tabs. The description shows under the title in Google. Both should be benefit-led and human-sounding.

---

## Step 3: Update the post header

Find this section near the top of the visible page:

```html
<section class="post-hero">
  <div class="container">
    <div class="post-meta">
      <span class="pill amber">Copywriting</span>
      <span>8 min read</span>
      <span>By Emmanuel Uzoma Anofienem</span>
    </div>
    <h1>Your headline here.</h1>
    <p class="deck">Your subheading or deck.</p>
  </div>
</section>
```

Replace:

- The `pill` tag (category): Use one of: `Real Estate`, `Sales`, `Strategy`, `Copywriting`, `Automation`. Change `amber` to nothing for blue pills, keep `amber` for amber pills.
- The read time
- The H1 (main title)
- The deck (subtitle/summary line)

---

## Step 4: Write your article inside the `<article>` tag

The article body is structured with simple HTML. Here are the elements you have:

### Paragraph
```html
<p>Your paragraph of text. You can <strong>bold things</strong> and <em>italicise things</em>. Italicised text gets the special serif treatment automatically.</p>
```

### Subheading (H2)
```html
<h2>This is a section heading</h2>
```

### Smaller subheading (H3)
```html
<h3>This is a sub-section heading</h3>
```

### Bulleted list
```html
<ul>
  <li>First point</li>
  <li>Second point</li>
  <li>Third point</li>
</ul>
```

### Numbered list
```html
<ol>
  <li>First step</li>
  <li>Second step</li>
</ol>
```

### Blockquote (highlighted big quote)
```html
<blockquote>"This pulls a line out and makes it look important."</blockquote>
```

### Callout box (highlighted insight)
```html
<div class="callout">
  <strong>Key insight:</strong> Use this when you want to draw attention to a single important point.
</div>
```

### Link
```html
<a href="https://example.com">Click here</a>
```

---

## Step 5: Update the closing call-to-action

At the bottom of the article, you'll see:

```html
<p class="post-end">If you want help with X, <a href="https://wa.me/...">message me on WhatsApp</a>...</p>
```

Update this to match your post's topic — what should the reader do next?

---

## Step 6: Add your post to the blog index page

Open `blog.html` and find the `.post-grid` section. Each post is a card like this:

```html
<a href="blog/your-slug-here.html" class="post-card reveal">
  <div class="post-card-visual pv-1">
    <div class="post-card-visual-text">Short evocative tagline</div>
  </div>
  <div class="post-card-body">
    <span class="pill">Category</span>
    <h3>Your post title</h3>
    <p>Your post summary in 1–2 sentences.</p>
    <div class="meta"><span>8 min read</span><span>Category</span></div>
  </div>
</a>
```

Add a new card just like this at the top of `.post-grid`, with:
- The new `href` pointing to your post
- A short tagline for the card image (the gradient placeholder)
- The same title, summary, read time, and category as your post
- One of the gradient classes: `pv-1`, `pv-2`, `pv-3`, or `pv-4`

---

## Step 7: Deploy

1. Save all your changes.
2. If you're using Netlify with GitHub: just push to your main branch and Netlify auto-deploys.
3. If you're using Netlify drop: drag your whole `swellbridge` folder back to Netlify.
4. The post is live within ~1 minute.

---

## Tips for writing posts that perform

- **One idea per post.** Don't try to cover everything. Pick the smallest useful insight and unpack it.
- **Open with a real scene or pain.** Don't open with "In today's competitive market…". Open with what the reader is feeling.
- **Use real numbers and real examples.** "₦40M deal closed" beats "great results". "2,000 realtors recruited" beats "we have many realtors".
- **End with a clear next step.** Reading is wasted without action. Tell them exactly what to do next.
- **Length: 1,000–2,500 words.** Long enough to be useful, short enough to actually read.
- **Headings every 200–300 words.** Mobile readers skim. Help them.

---

## Where the design styles live

If you want to change how all blog posts look, edit `css/post.css`. That stylesheet controls all the post page typography, callouts, blockquotes, etc.

For changes to nav, footer, or anything outside the article body, edit `css/main.css`.

---

That's it. Each new post is one HTML file you copy, edit, and link to from the blog index. No databases, no plugins, no Wordpress. Just files.
