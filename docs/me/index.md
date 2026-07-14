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
      src="/assets/images/me-qr.svg"
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
  const closeButton = modal.querySelector('.qr-close');
  const backdrop = modal.querySelector('.qr-backdrop');

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

    if (window.location.hash === '#qr') {
      history.replaceState(
        null,
        '',
        window.location.pathname + window.location.search
      );
    }
  }

  function respondToHash() {
    if (window.location.hash === '#qr') {
      openQrModal();
    } else {
      closeQrModal();
    }
  }

  trigger.addEventListener('click', function (event) {
    event.preventDefault();
    history.pushState(null, '', '#qr');
    openQrModal();
  });

  closeButton.addEventListener('click', closeQrModal);
  backdrop.addEventListener('click', closeQrModal);

  document.addEventListener('keydown', function (event) {
    if (event.key === 'Escape' && modal.classList.contains('is-open')) {
      closeQrModal();
    }
  });

  window.addEventListener('hashchange', respondToHash);

  respondToHash();
});
</script>
