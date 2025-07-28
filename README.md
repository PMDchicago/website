# PMD Chicago Static Site

This repository contains a static replacement for **Prairie Management & Development, Inc.** (pmdchicago.com).  The goal of this project is to provide a clean, modern and accessible website that preserves the existing navigation (Home, About Us, Careers and Contact Us) while improving the overall design and mobile responsiveness.

The site was built using **HTML5** and **[Tailwind CSS](https://tailwindcss.com/)** to keep the markup minimal and easy to maintain.  No CMS or server–side processing is used; all pages are static.

## File Structure

The project is organised as follows:

```
pmdchicago-site/
├── index.html         – Landing page with hero section, mission statement and highlights
├── about.html         – Company mission, background and history
├── careers.html       – Sample job opportunities and application instructions
├── contact.html       – Contact information, business hours and placeholder contact form
├── assets/
│   ├── css/
│   │   └── (future custom styles can go here)
│   └── img/
│       ├── hero.png   – Abstract hero image used on the home page
│       ├── about.png  – Illustration for the about page
│       └── careers.png– Illustration for the careers page
└── README.md          – This document
```

### Design Notes

* **Accessibility:** Semantic HTML elements (`<header>`, `<nav>`, `<main>`, `<footer>`, `<section>`, `<address>`) are used throughout.  Form controls include labels, placeholders and ARIA attributes.  Colour contrasts meet WCAG recommendations.
* **Responsive Layout:** The layout adapts from mobile through desktop using Tailwind’s responsive utilities.  The navigation collapses into a hamburger menu on small screens.
* **Placeholder Images:** Abstract images were generated to represent concepts such as community, collaboration and growth.  They do not depict specific real‑world places or people and may be replaced with actual photos later.

## Running the Site Locally

Because the site is completely static, you can open it directly in your browser by double‑clicking `index.html`.  However, some browsers enforce security policies that prevent loading local resources.  To avoid these, serve the site through a simple HTTP server:

```bash
# From within the `pmdchicago-site` directory
python3 -m http.server 8000

# Then visit http://localhost:8000 in your browser
```

## Version Control

To initialise a Git repository and commit your work:

```bash
cd pmdchicago-site
git init
git add .
git commit -m "Initial commit of PMD Chicago static site"

# Create a new repository on GitHub under your account (e.g. btec/pmdchicago-site)
# and then push your local repository to it:
git remote add origin git@github.com:<your‑username>/pmdchicago-site.git
git branch -M main
git push -u origin main
```

Replace `<your‑username>` with your GitHub user name.  Once pushed, the files will be available for deployment via Vercel.

## Deploying to Vercel

Vercel makes it simple to deploy static sites with HTTPS support by default.  To deploy:

1. **Sign in to Vercel** at [vercel.com](https://vercel.com/) using your GitHub account (btec).  Authorise Vercel to access your repositories if prompted.
2. Click **“Add New Project”** and select the newly created `pmdchicago-site` repository.  Vercel will detect that this is a static project.
3. Set the **Framework Preset** to **“Other”** and leave the **Build Command** empty because no build step is required.  The **Output Directory** should be the root (`.`).
4. Click **“Deploy”**.  Vercel will copy your files and assign a default `.vercel.app` domain.  You can view the deployed site immediately.
5. (Optional) **Custom Domain:** To use your custom domain (e.g. `pmdchicago.com`), go to the Vercel project’s **Settings → Domains** and add the domain.  Vercel will provide DNS records (typically CNAME or ANAME) that you must add at your domain registrar (GoDaddy).  After the DNS changes propagate, the site will be served securely over HTTPS at your custom domain.

## DNS Setup Notes (GoDaddy)

* Log in to your GoDaddy account and open the **DNS Management** page for your domain.
* Remove existing A records pointing to the old hosting provider.
* Add the DNS records provided by Vercel (usually an A record pointing to `76.76.21.21` and/or CNAME records for the root and `www` subdomain).  Vercel’s dashboard will show exactly what to enter.
* Save your changes.  DNS propagation can take up to 24 hours but is typically faster.

Once the DNS records have propagated, your site will be served over HTTPS.  Vercel automatically provisions and renews SSL certificates—no additional configuration is needed.

## Sources

* Mission, commitment and address information were summarized from publicly available descriptions of the company’s focus on residents, employees and investors【734601439959159†L34-L49】 and contact information【734601439959159†L34-L49】【637830709140045†L196-L199】.  
* The business founding year comes from the Better Business Bureau profile【637830709140045†L226-L233】.
