# Bodrum Property Group

Static website for Bodrum Property Group Ltd., a Manchester-based creative
property investment company run by Ceyhan Sarac.

## Structure

```
.
├── index.html    # The entire site (HTML + CSS + a little JS, single file)
├── assets/       # Images and videos
└── README.md
```

That's it. No build step, no dependencies, no framework. Pure static HTML/CSS/JS.

## Running locally

Open `index.html` in a browser. That's it.

If you want a local web server (recommended so `file://` paths behave
themselves), from the project root run any of:

```bash
# Python 3
python3 -m http.server 8000

# Node (if http-server is installed)
npx http-server
```

Then open http://localhost:8000.

## Editing content

Everything is in `index.html`. Open it in any text editor and edit directly.
Sections are clearly commented (NAVIGATION, HERO, ABOUT, SERVICES, LEASE
OPTIONS, VIDEOS, PROPERTIES, TESTIMONIALS, GALLERY, CONTACT, FOOTER).

To swap an image, drop a new file into `assets/` and update the `src` in the
corresponding `<img>` tag.

## Contact form

The contact form uses [Formspree](https://formspree.io) — a free service
that forwards form submissions to an email address with no backend required.

### Setup (one-time)

1. Go to https://formspree.io and sign up (free tier is fine)
2. Create a new form, enter the email address to receive submissions at
3. Copy the form's endpoint URL (looks like `https://formspree.io/f/xyzabc123`)
4. In `index.html`, find the line:
   ```html
   <form class="contact-form reveal" action="https://formspree.io/f/YOUR_FORM_ID" method="POST">
   ```
5. Replace `YOUR_FORM_ID` with the ID from step 3 (just the part after `/f/`)
6. Save and re-deploy

On first submission, Formspree sends a confirmation email to activate the
form. After that, submissions flow through automatically.

## Deployment

Any static host works:

- **GitHub Pages**: push to a GitHub repo, enable Pages in Settings
- **Netlify**: drag-and-drop the folder at https://app.netlify.com/drop
- **Traditional web host**: upload files via FTP/SFTP to the web root
