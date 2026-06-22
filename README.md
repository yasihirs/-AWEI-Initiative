# AWEI Website — Setup & Deployment Guide

## Project Structure
```
awei-website/
├── index.html          ← All 4 pages (Home, Framework, Pilot, Leadership)
├── style.css           ← All styles & responsive layout
├── assets/
│   ├── awei_vest.jpeg  ← Field photo (already included)
│   ├── awei_field.mov  ← Field video (already included)
│   └── favicon.ico     ← ADD your AWEI circular emblem here (rename to favicon.ico)
└── README.md
```

---

## Opening in VS Code
1. Open VS Code
2. File → Open Folder → select the `awei-website` folder
3. Install the **Live Server** extension (search in Extensions panel)
4. Right-click `index.html` → **Open with Live Server**
5. Your browser opens at `http://127.0.0.1:5500` — live preview!

---

## Adding More Photos
1. Drop new photos into the `assets/` folder
2. Replace image `src` paths in `index.html`:
   - Hero background: look for `awei_vest.jpeg` in the `<video>` fallback section
   - Mission section: look for `class="mission-img"`
   - Framework page: look for `class="crisis-visual"`

---

## Swapping in Your Crowdfunding Link (Pilot Page)
Find this line in `index.html`:
```html
<a href="#CAMPAIGN_LINK_PLACEHOLDER" class="btn-primary" ...>
```
Replace `#CAMPAIGN_LINK_PLACEHOLDER` with your actual crowdfunding URL.

---

## Setting Up the Contact Form (Real Email Delivery)
The form currently shows a success message but doesn't send emails yet.
To connect it to real email delivery:

**Option A — Formspree (free, easiest):**
1. Go to https://formspree.io and create a free account
2. Create a new form → get your form endpoint URL
3. In `index.html`, change both `<form>` tags:
   - Add `action="https://formspree.io/f/YOUR_ID"` to the form tag
   - Change `method` to `POST`
   - Remove the `onsubmit="submitForm..."` attribute
4. Formspree forwards submissions to `contact@awdalinitiative.org`

---

## Deploying to GitHub Pages (Free Hosting)
1. Create a GitHub account at github.com
2. Create a new repository named `awei-website` (or any name)
3. Upload all files in the `awei-website/` folder to the repo
4. Go to repo Settings → Pages → Source: **Deploy from branch** → `main` → `/ (root)`
5. Your site goes live at: `https://yourusername.github.io/awei-website/`

### Connecting Your Custom Domain
1. In GitHub Pages settings, enter your domain (e.g. `awdalinitiative.org`)
2. At your domain registrar (GoDaddy, Namecheap, etc.), add these DNS records:
   - Type: `A`, Host: `@`, Points to: `185.199.108.153`
   - Type: `A`, Host: `@`, Points to: `185.199.109.153`
   - Type: `CNAME`, Host: `www`, Points to: `yourusername.github.io`
3. Wait up to 24 hours for DNS to propagate

---

## Things Still To Do
- [ ] Add your official AWEI circular logo as `assets/favicon.ico`
- [ ] Add more field photos (landscape, school, community shots)
- [ ] Fill in Legal Counsel's last name on the Leadership page
- [ ] Fill in Diplomatic Advisor's first name on the Leadership page
- [ ] Paste in your crowdfunding link on the Pilot page
- [ ] Set up Formspree for real contact form email delivery
- [ ] Add headshot photos for board members (optional)
