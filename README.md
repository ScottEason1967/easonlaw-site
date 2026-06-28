# Eason Law website

Static website for Eason Law (easonlaw.co.uk). Plain HTML and CSS, no build step.
Designed to be hosted free on GitHub Pages using your own domain.

## Structure

```
index.html        Home
services.html     Services (four areas)
about.html        About + regulatory statement
contact.html      Contact
404.html          Not-found page
assets/css/       Stylesheet
assets/img/       Logo and favicons
CNAME             Custom domain for GitHub Pages (easonlaw.co.uk)
sitemap.xml, robots.txt
```

## Preview locally

Open `index.html` in a browser. Everything uses relative paths, so it works
straight from the folder. The fonts load from Google Fonts, so you need to be
online to see them exactly as designed.

## Put it live on GitHub Pages

1. Create a new repository on GitHub (for example `easonlaw-site`). It can be
   public or private; Pages works with both on current plans.
2. Upload the contents of this folder to the repository (drag the files into
   the GitHub web uploader, or push with git):

   ```bash
   git init
   git add .
   git commit -m "Initial site"
   git branch -M main
   git remote add origin https://github.com/<your-username>/easonlaw-site.git
   git push -u origin main
   ```

3. In the repository, go to **Settings -> Pages**. Under **Build and
   deployment**, set **Source** to *Deploy from a branch*, branch `main`,
   folder `/ (root)`. Save.
4. Still on the Pages screen, under **Custom domain**, enter
   `easonlaw.co.uk` and save. (The `CNAME` file in this repo already sets this.)
5. Tick **Enforce HTTPS** once it becomes available (it can take a little while
   after the DNS is in place).

## DNS at your domain registrar

Point the domain at GitHub. In your registrar's DNS settings:

**Apex domain (easonlaw.co.uk)** — add four A records, all with host `@`:

```
185.199.108.153
185.199.109.153
185.199.110.153
185.199.111.153
```

(Optionally add the matching AAAA/IPv6 records from GitHub's docs.)

**www subdomain** — add a CNAME record:

```
Host:  www
Value: <your-username>.github.io
```

DNS changes can take anywhere from a few minutes to a few hours to take effect.
GitHub then issues a free HTTPS certificate automatically.

> The IP addresses above are GitHub's published Pages addresses. They rarely
> change, but if anything fails to resolve, confirm the current values in
> GitHub's documentation: "Managing a custom domain for your GitHub Pages site".

## Editing content

All copy lives directly in the `.html` files. Brand colours and layout are in
`assets/css/styles.css`. To replace the logo, swap the file at
`assets/img/eason-law-logo.png` (keep the same name) or update the references.
