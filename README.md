# koyantaw.app

The Koyantaw - ကိုယ်ရံတော် landing page and privacy policy, hosted on
Hostinger at https://koyantaw.app.

Plain static files, no build step. To publish a change:

1. Zip the site (everything except `.git`, `README.md` and `.gitignore`):

       zip -qr -X ../koyantaw-landing.zip .htaccess 404.html favicon.ico \
         index.html styles.css fonts images privacy-policy -x "*.DS_Store"

2. In hPanel, open File Manager for koyantaw.app, upload the zip into
   `public_html`, extract it there (replacing existing files), and delete
   the zip.

Preview locally with `python3 -m http.server 5173`.

`.htaccess` does what Firebase Hosting used to: HTTPS and www redirects to
https://koyantaw.app, the custom 404 page, caching, and security headers.
File Manager hides it unless "Show hidden files" is on; make sure it is
uploaded.

**Do not move or rename `images/brand/logo-192.png`.** Every account email
the Koyantaw server sends embeds it by URL, including ones already in
people's inboxes.

Firebase Hosting and GitHub Pages were both tried and dropped: Firebase is
unreachable from some regions, and Pages never issued a certificate for the
domain.
