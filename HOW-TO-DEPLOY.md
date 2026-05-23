# How To Deploy Swellbridgedigital.com To Netlify

You bought `swellbridgedigital.com` on Namecheap. Now let's get this site live.

There are two ways to deploy. Pick whichever is easier for you:

---

## OPTION A — Netlify Drop (Easiest, ~5 minutes)

Best if you don't use Git yet. You'll need to repeat this every time you want to update the site.

### Steps:

1. **Sign up at Netlify**: Go to [netlify.com](https://netlify.com) and create a free account (use the same email you used for Namecheap if possible — keeps things tidy).

2. **Drop your site folder**: Once you're logged in, you'll see a page that says "Drag and drop your site folder here." Drag the entire `swellbridge` folder onto that area. Netlify will upload it.

3. **Wait ~30 seconds**: Netlify will give your site a random URL like `https://wonderful-puppy-12345.netlify.app`. Click it to see your site live.

4. **Skip to "Connect Your Domain"** below.

---

## OPTION B — GitHub + Netlify (Best, ~15 minutes setup, then easy forever)

Best if you want to update the site easily over time. After this is set up, you push changes to GitHub and Netlify auto-deploys.

### Steps:

1. **Create a GitHub account** at [github.com](https://github.com) if you don't have one.

2. **Create a new repository** called `swellbridge-website`. Set it to private or public — your choice.

3. **Upload your `swellbridge` folder** to the repo. You can do this via the GitHub web UI (drag and drop the files), or via the command line if you know Git.

4. **Sign up at Netlify** at [netlify.com](https://netlify.com).

5. **Click "Add new site" → "Import an existing project" → "GitHub"**. Authorise GitHub access, then pick your `swellbridge-website` repo.

6. **Leave the build settings empty** (we have no build step — just static files). Click "Deploy site".

7. **Wait ~30 seconds**: Netlify deploys and gives you a URL. Test it.

8. **Skip to "Connect Your Domain"** below.

---

## Connect Your Domain (swellbridgedigital.com)

Once your site is on Netlify, point your domain to it:

### On Netlify:

1. Open your site in the Netlify dashboard.
2. Click **"Domain settings"** (left sidebar).
3. Click **"Add a domain"**.
4. Type `swellbridgedigital.com` and confirm.
5. Netlify will show you DNS records to add. You can either:
   - **Easy path**: Use Netlify DNS (Netlify becomes your DNS host). They'll give you 4 nameservers to put in Namecheap.
   - **Advanced path**: Keep Namecheap as DNS host. You'll add A + CNAME records.

### On Namecheap (Easy Path — recommended):

1. Log into Namecheap. Go to **Domain List → "Manage"** next to `swellbridgedigital.com`.
2. Find **"Nameservers"**, change to **"Custom DNS"**.
3. Enter the 4 Netlify nameservers (Netlify shows them to you, they look like `dns1.p01.nsone.net`).
4. Save.
5. Wait 1–24 hours for DNS to propagate (usually under an hour).

### Verify:

After propagation, visit `https://swellbridgedigital.com` — your site should load. Netlify will automatically provision an SSL certificate so HTTPS works.

---

## Updating Your Site Later

### If you used Netlify Drop:

1. Open your site on Netlify.
2. Click **"Deploys"** in the left sidebar.
3. Drag your updated `swellbridge` folder onto the page.
4. Netlify replaces the live version. Done.

### If you used GitHub:

1. Edit any file locally.
2. Push to GitHub (whether via web UI or command line).
3. Netlify auto-deploys within 30 seconds.
4. Done.

---

## File Structure (For Reference)

```
swellbridge/
├── index.html              # Homepage
├── real-estate.html        # Real Estate Developer page (3 tiers)
├── meta-ads.html           # Meta Ads service page
├── funnels.html            # Funnels & landing pages
├── web-design.html         # Web Design with portfolio
├── automation.html         # Automation service page
├── case-studies.html       # Results & case studies
├── blog.html               # Blog index
├── about.html              # About page
├── contact.html            # Contact page
├── netlify.toml            # Netlify config (redirects, headers)
├── HOW-TO-ADD-A-BLOG-POST.md     # Blog publishing guide
├── HOW-TO-DEPLOY.md        # This file
├── css/
│   ├── main.css            # Master design system
│   └── post.css            # Blog post styles
├── js/
│   └── main.js             # Site interactions
├── blog/
│   ├── why-most-nigerian-real-estate-ads-fail.html
│   ├── awareness-levels-eugene-schwartz-applied-to-nigeria.html
│   ├── whatsapp-first-follow-up-system.html
│   ├── realtor-army-recruitment-playbook.html
│   └── should-i-do-my-own-marketing-or-hire.html
└── samples/                # Live sample sites
    ├── luxury-estates/index.html
    ├── empire-consulting/index.html
    ├── serene-clinic/index.html
    └── oak-and-amber/index.html
```

---

## Things You Can Change Easily

- **Your photo on the homepage and about page**: Currently pulls from `https://swellbridge.netlify.app/emmanuel.jpg`. Replace by hosting a new image somewhere (Netlify, ImgBB, etc.) and updating the URL in `index.html` and `about.html`.

- **Your WhatsApp number**: Currently hardcoded as `2348064158087` in every CTA. To change globally, do a project-wide find-and-replace.

- **Your email**: Currently `hello@swellbridgedigital.com`. To change, find-and-replace project-wide.

- **Prices**: All prices are in the service pages (`real-estate.html`, `meta-ads.html`, `funnels.html`, etc.). Edit the HTML to update.

- **Testimonials**: Currently using real ones from your Natweng Realtors work. Add more by copying the existing testimonial blocks in `index.html`, `real-estate.html`, etc.

---

## SEO Quick Wins (Do These After Launch)

1. **Set up Google Search Console** ([search.google.com/search-console](https://search.google.com/search-console)) — verify your site, submit your sitemap.
2. **Set up Google Analytics 4** — add the tracking code to all pages.
3. **Set up Meta Pixel** — for retargeting Facebook ads at your site visitors.
4. **Submit your site to Bing Webmaster Tools** — easy and gives you a backup search source.

These take 30 minutes total and make a big difference.

---

## You're Done.

Your site is live. Updates are easy. Blog publishing is documented. Sample sites work as portfolio.

Any questions, the answers are usually in the file structure itself — most pages are commented and labeled clearly.

Welcome to your new website. Now let's go close some clients.
