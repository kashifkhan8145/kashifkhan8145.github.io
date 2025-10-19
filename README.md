Kashif Khan — Research Portfolio (ML × RF)

Live site: https://kashifkhan8145.github.io

Tech stack: HTML, Tailwind (CDN), Vanilla JS, GA4

Highlights

Responsive, polished layout with light/dark mode toggle

Interactive ML demo (draggable linear regression)

Sections for projects, publications, experience, education, skills, awards, gallery

Accessible UI (focus trap in lightbox, reduced-motion support, semantic HTML)

Analytics with Google Analytics 4 (GA4)

Quick start
# Clone
git clone https://github.com/kashifkhan8145/kashifkhan8145.github.io
cd kashifkhan8145.github.io

# Option A: open index.html directly
# Option B (recommended): run a local server
python -m http.server 8000
# then visit http://localhost:8000

Project structure
.
├─ index.html                 # Main single-page site
├─ Kashif_Khan.jpg            # Hero portrait / OG image
├─ Kashif_Khan_CV.pdf         # CV download
├─ gallery/                   # Gallery images
├─ favicon-*.png, site.webmanifest, apple-touch-icon.png
└─ (optional) assets/         # Extra images or JS if you add later

Configuration
1) Google Analytics 4 (already included)

In <head> of index.html:

<script async src="https://www.googletagmanager.com/gtag/js?id=G-FXBPVE8T4P"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){ dataLayer.push(arguments); }
  gtag('js', new Date());
  gtag('config', 'G-FXBPVE8T4P', {
    anonymize_ip: true,
    page_title: document.title,
    page_path: location.pathname
  });
</script>


Check traffic in GA4: Admin → Data Streams → Web → DebugView / Reports.

2) Contact options

Email link (already on the site)

If you want a form later, use Formspree:

<!-- Replace YOUR_FORM_ID after creating it on formspree.io -->
<form id="contactForm" action="https://formspree.io/f/YOUR_FORM_ID" method="POST">
  <input type="text" name="name" required placeholder="Your name">
  <input type="email" name="email" required placeholder="Your email">
  <textarea name="message" rows="4" required placeholder="Your message"></textarea>
  <button type="submit">Send</button>
</form>
<p id="formStatus" aria-live="polite"></p>


And a minimal JS handler (optional):

<script>
const f = document.getElementById('contactForm');
const status = document.getElementById('formStatus');
if (f) {
  f.addEventListener('submit', async (e) => {
    e.preventDefault();
    const data = new FormData(f);
    try {
      const r = await fetch(f.action, { method: 'POST', body: data, headers: { 'Accept': 'application/json' }});
      if (r.ok) { status.textContent = 'Thanks! Message sent.'; f.reset(); }
      else { status.textContent = 'Error sending message. Please try email.'; }
    } catch {
      status.textContent = 'Network error. Please try email.';
    }
  });
}
</script>

Accessibility & performance notes

Respects prefers-reduced-motion (disables starfield/animations).

Lightbox has a simple focus trap and supports Escape.

Hero image is preloaded to improve LCP.

Semantic headings and descriptive link text.

Deployment (GitHub Pages)

This repo is published from the main branch.

GitHub → Settings → Pages

Source: “Deploy from a branch”

Branch: main — Folder: /root

Changes to main will auto-deploy.

License

MIT License — feel free to reuse/modify the site code with attribution.

MIT License

Copyright (c) 2025 Kashif Khan

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the “Software”), to deal
in the Software without restriction…

Contact

Email: kashif.khan@nu.edu.kz

Scholar: https://scholar.google.com/citations?user=e0CeRSUAAAAJ

LinkedIn: https://www.linkedin.com/in/kashifkhan8145

GitHub: https://github.com/kashifkhan8145
