---
title: Dave Cross
permalink: /me/
layout: single
---

Perl consultant, author, trainer and open source developer based in London.

## 📇 Add me to your contacts

The easiest way to keep my details up to date is to add me using my vCard.

👉 **[Add Dave Cross to your contacts](/contact.vcf)**

If my contact details ever change, simply return to this page and download the
latest version.

<p>
  <a href="#qr" class="qr-trigger" id="show-qr">
    Show QR code
  </a>
</p>

<div
  id="qr"
  class="qr-modal"
  role="dialog"
  aria-modal="true"
  aria-labelledby="qr-title"
  aria-hidden="true">

  <button
    type="button"
    class="qr-backdrop"
    aria-label="Close QR code"></button>

  <div class="qr-panel">
    <button
      type="button"
      class="qr-close"
      aria-label="Close QR code">
      &times;
    </button>

    <h2 id="qr-title">Dave Cross</h2>

    <img
      src="/img/me-qr.svg"
      alt="QR code linking to Dave Cross’s contact page">

    <p>Scan to view my contact details</p>
  </div>
</div>

## 🌐 Find me online

* Website: <https://davecross.co.uk/>
* GitHub: <https://github.com/davorg>
* LinkedIn: <https://www.linkedin.com/in/davecross/>
* Mastodon: *(or Bluesky, whichever you prefer)*
* Perl Hacks: <https://perlhacks.com/>

## 💼 What I do

I've been building web applications professionally since 1995 and specialise
in Perl development, training and technical writing.

Current interests include:

* Perl
* GitHub Actions
* Open source
* Static websites
* AI-assisted software development

## 📚 Recent projects

* [*GitHub Actions Essentials*](https://actions.davecross.co.uk/)
* [*The Horsell Transmissions*](https://horsell.substack.com/)
* [Austenpunk](https://austenpunk.dev/)
* [Perl Ads](https://perl-ads.perlhacks.com/)

---

*Met me at a conference? Feel free to get in touch.*

<script>
document.addEventListener('DOMContentLoaded', function () {
  const modal = document.getElementById('qr');
  const trigger = document.getElementById('show-qr');

  // Minimal Mistakes creates stacking contexts around parts of the layout.
  // Moving the modal directly beneath <body> allows its z-index to work.
  document.body.appendChild(modal);

  const closeButton = modal.querySelector('.qr-close');
  const backdrop = modal.querySelector('.qr-backdrop');

  function isQrMode() {
    const params = new URLSearchParams(window.location.search);

    return window.location.hash === '#qr' || params.has('qr');
  }

  function openQrModal() {
    modal.classList.add('is-open');
    modal.setAttribute('aria-hidden', 'false');
    document.body.classList.add('qr-is-open');
    closeButton.focus();
  }

  function closeQrModal() {
    modal.classList.remove('is-open');
    modal.setAttribute('aria-hidden', 'true');
    document.body.classList.remove('qr-is-open');

    // Remove both #qr and ?qr while preserving any other query parameters.
    const url = new URL(window.location.href);

    url.hash = '';
    url.searchParams.delete('qr');

    history.replaceState(null, '', url);
  }

  function respondToLocation() {
    if (isQrMode()) {
      openQrModal();
    } else {
      modal.classList.remove('is-open');
      modal.setAttribute('aria-hidden', 'true');
      document.body.classList.remove('qr-is-open');
    }
  }

  trigger.addEventListener('click', function (event) {
    event.preventDefault();

    // Use the URL supplied by the link, allowing either href="#qr"
    // or href="?qr" to be used in the HTML.
    history.pushState(null, '', trigger.href);
    openQrModal();
  });

  closeButton.addEventListener('click', closeQrModal);
  backdrop.addEventListener('click', closeQrModal);

  document.addEventListener('keydown', function (event) {
    if (event.key === 'Escape' && modal.classList.contains('is-open')) {
      closeQrModal();
    }
  });

  window.addEventListener('hashchange', respondToLocation);
  window.addEventListener('popstate', respondToLocation);

  respondToLocation();
});
</script>
