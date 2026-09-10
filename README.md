# CynthiaSite

A simple static creative-writing portfolio site (plain HTML/CSS, no build step),
meant to be hosted on GitHub Pages with a custom domain from Namecheap.

## Structure

```
index.html          Home page
writing.html         Full list of writing, grouped by category
about.html           Bio
contact.html         Contact info / links
writing/*.html       Individual pieces (short story, poem, essay placeholders)
css/style.css        Shared stylesheet
CNAME                Custom domain for GitHub Pages
```

Everything marked `[PLACEHOLDER: ...]` in the HTML should be replaced with real
content: name, bio, actual writing pieces, email, and social links.

## 1. Replace the placeholder content

- Swap "Cynthia Reyes" for the real name throughout (`index.html`, `writing.html`,
  `about.html`, `contact.html`, and each file in `writing/`), or leave it if that's
  correct.
- Replace each `[PLACEHOLDER: ...]` block with real text.
- Add more pieces by copying one of the files in `writing/`, editing it, and adding
  a link to it from `writing.html` (and optionally `index.html` if it's featured).

## 2. Turn on GitHub Pages

1. Push this repository to GitHub (if it isn't already there).
2. In the repo, go to **Settings → Pages**.
3. Under **Build and deployment**, set **Source** to "Deploy from a branch".
4. Pick the branch this site lives on (e.g. `main`) and folder `/ (root)`, then save.
5. GitHub will build a URL like `https://<username>.github.io/<repo>/` — confirm the
   site loads there before moving on to the custom domain.

## 3. Point your Namecheap domain at GitHub Pages

Edit the `CNAME` file in this repo and replace `yourdomain.com` with your actual
domain (e.g. `cynthiawrites.com`), then commit it. GitHub Pages reads this file to
know which custom domain to serve.

Then, in **Namecheap → Domain List → Manage → Advanced DNS** for your domain, add
these records (remove any conflicting default "Parking Page" records first):

**If using the root/apex domain (`yourdomain.com`):**

| Type  | Host | Value               |
|-------|------|---------------------|
| A     | @    | 185.199.108.153     |
| A     | @    | 185.199.109.153     |
| A     | @    | 185.199.110.153     |
| A     | @    | 185.199.111.153     |

**If also using `www.yourdomain.com`:**

| Type  | Host | Value                        |
|-------|------|------------------------------|
| CNAME | www  | `<username>.github.io.`      |

(You can set up both — the apex with A records, and `www` with a CNAME.)

## 4. Finish in GitHub

1. Back in **Settings → Pages**, enter your custom domain in the **Custom domain**
   field and save (this writes/confirms the `CNAME` file for you too).
2. Wait for DNS to propagate (usually minutes, sometimes up to ~24 hours) — GitHub
   will show a green checkmark once it verifies the domain.
3. Check **Enforce HTTPS** once it becomes available, so the site serves over
   `https://`.

Your site should then be live at your custom domain.
