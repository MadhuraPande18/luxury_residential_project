# Luxury Real Estate Website

A fast, elegant marketing website for a premium 3 & 3.5 BHK residential tower in Pune, built to present the project beautifully and turn visitors into sales enquiries.

> Client project. The client's name, brand assets and data are kept private. Screenshots are shared for portfolio purposes with permission.

---

## Highlights

- **Premium, responsive design**: a cream and gold design system, fluid typography and subtle scroll animations, tested from 360 px phones to 1920 px desktops.
- **Lead capture**: an enquiry pop-up after 30 seconds that stays open until the form is filled, a brochure that downloads after the visitor shares their details, and a full contact form.
- **Email delivery**: every enquiry is emailed to the sales team with name, mobile, email, interest, message, source and time (IST).
- **Reliable fallbacks**: validation, a spam trap, a 20 second timeout and a WhatsApp backup link with the details filled in, so a lead is never lost.
- **Marketing-ready**: Meta Pixel events for PageView, Lead and Contact.
- **SEO**: an optimised title and description, canonical tags, Open Graph and Twitter cards, JSON-LD structured data, `sitemap.xml` and `robots.txt`.
- **Performance**: minified CSS and JS, self-hosted WOFF2 fonts, compressed images, lazy loading, explicit image sizes and cache-busting on assets.
- **Interactive content**: a masterplan with a legend that highlights each feature, a 22-photo gallery with category filters, and a full-screen image viewer with zoom.
- **Accessible**: alt text on every image, labelled form fields, keyboard support (Esc and arrow keys), focus kept inside dialogs, and respect for `prefers-reduced-motion`.
- **Tested**: 90+ automated browser checks with Playwright before every release.

---

## Tech stack

| Area | Tools |
|---|---|
| Front end | HTML5, CSS3 (custom properties, Grid, `clamp()`), vanilla JavaScript |
| Forms | FormSubmit (AJAX email delivery) |
| Analytics | Meta Pixel |
| Build | Python (page generation, image optimisation, CSS/JS minification with `rcssmin` and `rjsmin`, Pillow) |
| Testing | Playwright (Chromium) |
| Hosting | GoDaddy cPanel (static hosting), also tested on Netlify |

No front-end framework is used, which keeps the site light, fast and easy to host anywhere.

---

## Project structure

```
website/
├── index.html          # the page
├── css/style.css       # minified styles
├── js/main.js          # minified behaviour (reveals, gallery, viewer, forms, pop-up)
├── fonts/              # self-hosted WOFF2 fonts
├── images/             # optimised renders, plans, logos, gallery
├── brochure/           # downloadable PDF brochure
├── robots.txt
└── sitemap.xml
```

---

## Configuration

All lead settings live at the top of the lead section in `js/main.js`:

```js
var LEAD_EMAIL = "sales@example.com";   // inbox that receives every enquiry
var WA_NUMBER  = "91XXXXXXXXXX";        // WhatsApp fallback number
```

| Setting | Where | Default |
|---|---|---|
| Pop-up delay | `setTimeout(tryOpen, 30000)` | 30 seconds |
| Meta Pixel ID | `<head>` of `index.html` | your pixel ID |
| Site URL (canonical, sitemap, Open Graph) | `index.html`, `sitemap.xml`, `robots.txt` | your domain |

Add `?popup` to the page address to force the pop-up open while testing.

---

## Deployment

1. Upload the **contents** of the website folder to the web root (for example `public_html` on cPanel). `index.html` must sit directly inside it.
2. Open the live site and send one test enquiry.
3. FormSubmit sends an **Activate Form** email to the lead inbox. Click it once.
4. Send a second test. From now on, every enquiry arrives automatically.
5. Optionally, submit `sitemap.xml` in Google Search Console.

> Forms only send from a live website (`http://` or `https://`). When the page is opened as a local file, the form shows a clear message and the pop-up can be closed.

---

## Testing

The Playwright suite runs against the exact build that gets deployed and checks:

- Layout at 6 screen widths: no horizontal scroll, all images load, all sections reveal, fonts load, hero crown visible
- Navigation links, mobile menu, gallery filters, image viewer and masterplan highlights
- Pop-up timing and compulsory behaviour, the brochure gate and download, and contact form validation and delivery
- Failure handling (error message, WhatsApp fallback, typed details kept)
- SEO tags, the Meta Pixel, broken links, duplicate IDs and console errors

---

## Screenshots

| Home | Enquiry pop-up |
|---|---|
| ![Home](screenshots/website-1-home.jpg) | ![Pop-up](screenshots/website-2-enquiry-popup.jpg) |

| Gallery | Masterplan |
|---|---|
| ![Gallery](screenshots/website-3-gallery.jpg) | ![Masterplan](screenshots/website-4-masterplan.jpg) |

![Mobile](screenshots/website-7-mobile.jpg)

---

## Author

**Madhura Pande**, Web and Full Stack Developer

- Email: madhurapande18@gmail.com
- LinkedIn: [linkedin.com/in/madhura-pande-363930325](https://linkedin.com/in/madhura-pande-363930325)
- GitHub: [github.com/MadhuraPande18](https://github.com/MadhuraPande18)

Open for freelance website projects.

---

© 2026 Madhura Ajay Pande. Client content, renders and brand assets belong to their respective owners and are not included in this repository.
