# PentMind.ai

**AI-powered pentesting with human judgment.**

> The mind behind the machine.

## About

PentMind is a hybrid cybersecurity service combining AI automation with human expert validation. We find your critical vulnerabilities before attackers do — faster, cheaper, and with zero noise.

## Tech stack

- Pure HTML/CSS/JS — no frameworks, no dependencies
- Google Fonts (IBM Plex Mono, IBM Plex Sans, Bebas Neue)
- Hosted on GitHub Pages

## Languages supported

- 🇬🇧 English
- 🇦🇷 Spanish (Español)
- 🇧🇷 Portuguese (Português)
- 🇫🇷 French (Français)

## How to deploy on GitHub Pages

1. Fork or clone this repo
2. Go to **Settings → Pages**
3. Source: **Deploy from a branch**
4. Branch: `main` / folder: `/ (root)`
5. Save — site will be live at `https://yourusername.github.io/pentmind-site`

## Custom domain (pentmind.ai)

After GitHub Pages is live:

1. In repo root, create a file called `CNAME` with content:
   ```
   pentmind.ai
   ```
2. In your domain registrar (Namecheap/GoDaddy), add DNS records:
   ```
   A     @     185.199.108.153
   A     @     185.199.109.153
   A     @     185.199.110.153
   A     @     185.199.111.153
   CNAME www   yourusername.github.io
   ```
3. In GitHub Pages settings, enter your custom domain and enable **Enforce HTTPS**

## Contact form

The contact form currently simulates submission. To make it functional, connect it to [Formspree](https://formspree.io):

1. Create a free account at formspree.io
2. Create a new form — you'll get an endpoint like `https://formspree.io/f/xyzabcde`
3. In `index.html`, find the `submitForm` function and replace the `setTimeout` with:
   ```javascript
   fetch('https://formspree.io/f/YOUR_ID', {
     method: 'POST',
     headers: { 'Content-Type': 'application/json' },
     body: JSON.stringify({
       name: document.getElementById('inp_name').value,
       company: document.getElementById('inp_company').value,
       email: document.getElementById('inp_email').value,
       interest: document.getElementById('inp_interest').value,
       message: document.getElementById('inp_msg').value
     })
   }).then(() => {
     document.getElementById('contact-form-el').style.display = 'none';
     document.getElementById('form-success').style.display = 'block';
   });
   ```

## License

© 2025 PentMind. All rights reserved.
