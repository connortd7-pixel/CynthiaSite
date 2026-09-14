# CynthiaSite

A simple static writing portfolio site (plain HTML/CSS, no build step) for Cynthia
Theresa Doyle, showcasing journalism, social media campaign work, research writing,
fiction, and poetry. Hosted on GitHub Pages with a custom domain from Namecheap.

## Structure

```
index.html          Home page (bio + featured writing)
writing.html         Full list of writing, grouped by category
resume.html          Resume (education, volunteer work, leadership, skills)
contact.html         Contact info
writing/*.html       Individual pieces (newswire, social campaign, research
                     paper, flash fiction, poetry)
assets/*.png         Figures used in the research paper
css/style.css        Shared stylesheet
CNAME                Custom domain for GitHub Pages
```

## Adding more writing

Copy one of the files in `writing/`, edit its content, then add a link to it from
`writing.html` (in the relevant category) and optionally from `index.html` if it
should be featured.

## 2. Turn on GitHub Pages

1. Push this repository to GitHub (if it isn't already there).
2. In the repo, go to **Settings → Pages**.
3. Under **Build and deployment**, set **Source** to "Deploy from a branch".
4. Pick the branch this site lives on (e.g. `main`) and folder `/ (root)`, then save.
5. GitHub will build a URL like `https://<username>.github.io/<repo>/` — confirm the
   site loads there before moving on to the custom domain.

## 3. Point your Namecheap domain at GitHub Pages

The `CNAME` file in this repo is already set to `cynthiatheresadoyle.com`.

Then, in **Namecheap → Domain List → Manage → Advanced DNS** for `cynthiatheresadoyle.com`,
add these records (remove any conflicting default "Parking Page" records first):

**For the root/apex domain (`cynthiatheresadoyle.com`):**

| Type  | Host | Value               |
|-------|------|---------------------|
| A     | @    | 185.199.108.153     |
| A     | @    | 185.199.109.153     |
| A     | @    | 185.199.110.153     |
| A     | @    | 185.199.111.153     |

**If also using `www.cynthiatheresadoyle.com`:**

| Type  | Host | Value                          |
|-------|------|---------------------------------|
| CNAME | www  | `connortd7-pixel.github.io.`   |

(You can set up both — the apex with A records, and `www` with a CNAME.)

## 4. Finish in GitHub

1. Back in **Settings → Pages**, enter `cynthiatheresadoyle.com` in the **Custom
   domain** field and save (this writes/confirms the `CNAME` file for you too).
2. Wait for DNS to propagate (usually minutes, sometimes up to ~24 hours) — GitHub
   will show a green checkmark once it verifies the domain.
3. Check **Enforce HTTPS** once it becomes available, so the site serves over
   `https://`.

Your site should then be live at your custom domain.
