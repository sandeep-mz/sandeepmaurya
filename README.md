# Sandeep Maurya — Portfolio

A single-file, production-ready portfolio site (`index.html`) — dark/light mode, glassmorphism, particle background, scroll animations, animated stats/skill bars, and a full contact form with client-side validation.

## 1. Put it online (2 minutes, free)

Pick one:

**Vercel (recommended)**
1. Go to vercel.com → New Project → "Deploy without Git" (drag & drop) and drop this folder in, or push it to a GitHub repo and import it.
2. You'll get a live URL like `sandeep-maurya.vercel.app`.

**Netlify**
1. Go to app.netlify.com/drop and drag this folder in. Done — instant live URL.

**GitHub Pages**
1. Create a repo (e.g. `sandeep-maurya-portfolio`), push `index.html` to it.
2. Repo Settings → Pages → Deploy from branch → `main` / root.
3. Live at `https://<your-username>.github.io/sandeep-maurya-portfolio/`.

Once live, add the link to your LinkedIn profile under **"Featured"** or the **Contact info → Website** field.

## 2. Personalize before publishing

Open `index.html` and update:
- Real email/phone: search for `sandeep.maurya@example.com` and `+910000000000` and replace everywhere (hero socials, footer, contact section, WhatsApp link `wa.me/...`).
- Real LinkedIn/GitHub URLs: replace the `https://linkedin.com` / `https://github.com` placeholders.
- Photo: replace the `🖥️` / `🧑‍💻` emoji placeholders in `.avatar-frame .inner` and `.about-photo` with an `<img src="your-photo.jpg">`.
- Resume: add a `resume.pdf` file next to `index.html`, then change the two `id="downloadResume"` / `id="downloadResume2"` links' `href="#"` to `href="resume.pdf"` and remove the placeholder toast in the `<script>`.

## 3. Make the contact form actually send emails

Right now the form validates and shows a success state, but doesn't send anywhere. Pick one:

**Formspree (easiest, no signup code needed)**
1. Create a form at formspree.io, copy your form ID.
2. In the `<script>`, inside the `submit` handler, replace the `setTimeout(...)` block with a `fetch` POST:
```js
fetch('https://formspree.io/f/YOUR_FORM_ID', {
  method: 'POST',
  body: new FormData(form),
  headers: { Accept: 'application/json' }
}).then(() => { /* show success block, same as now */ });
```

**EmailJS**
1. Add `<script src="https://cdn.jsdelivr.net/npm/@emailjs/browser@4/dist/email.min.js"></script>` before `</body>`.
2. Call `emailjs.init('YOUR_PUBLIC_KEY')` once on load.
3. Replace the `setTimeout` block with `emailjs.sendForm('SERVICE_ID','TEMPLATE_ID', form)`.

## 4. Notes

- All animations respect `prefers-reduced-motion`.
- Colors/fonts follow your brief: Primary `#2563EB`, Secondary `#1E293B`, Accent `#06B6D4`, Poppins + Inter.
- No build step, no npm install required — it's a static file, so it opens directly in a browser too.
