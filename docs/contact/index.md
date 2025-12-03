---
title: Contact me
---

If you’d like to get in touch about consulting, training, or
[anything else](/services/), use the form below or email me at
[hello@davecross.co.uk](mailto:hello@davecross.co.uk).

<form
  id="contact-form"
  action="https://formspree.io/f/xvgerbnq"
  method="POST"
  class="contact-form"
>
  <label for="name">Name</label>
  <input type="text" id="name" name="name" required>

  <label for="email">Email</label>
  <input type="email" id="email" name="_replyto" required>

  <label for="message">Message</label>
  <textarea id="message" name="message" rows="6" required></textarea>

  <!-- Optional: subject line in the email you receive -->
  <input type="hidden" name="_subject" value="New message from your website">

  <!-- Spam honeypot: humans leave this blank -->
  <input type="text" name="_gotcha" style="display:none">
  <button type="submit">Send message</button>
  <p id="contact-form-status" class="form-status" aria-live="polite"></p>
</form>

<script>
(function () {
  const form = document.getElementById("contact-form");
  if (!form) return;

  const statusEl = document.getElementById("contact-form-status");

  async function handleSubmit(event) {
    event.preventDefault();
    if (statusEl) statusEl.textContent = "Sending…";

    const data = new FormData(form);

    try {
      const response = await fetch(form.action, {
        method: form.method,
        body: data,
        headers: { "Accept": "application/json" }
      });

      if (response.ok) {
        if (statusEl) statusEl.textContent = "Thanks – your message has been sent.";
        form.reset();
      } else {
        let message = "Oops – there was a problem sending your message.";
        try {
          const data = await response.json();
          if (data.errors) {
            message = data.errors.map(e => e.message).join(", ");
          }
        } catch (e) {
          // ignore JSON parse errors, fall back to generic message
        }
        if (statusEl) statusEl.textContent = message;
      }
    } catch (err) {
      if (statusEl) statusEl.textContent = "Network error – please try again in a moment.";
    }
  }

  form.addEventListener("submit", handleSubmit);
})();
</script>

