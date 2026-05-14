// ── RSVP form component ──────────────────────────────────────────────────────
// Handles validation, submission, and success state.

function escapeHtml(str) {
  return str
    .replace(/&/g, '&amp;')
    .replace(/</g, '&lt;')
    .replace(/>/g, '&gt;')
    .replace(/"/g, '&quot;');
}

function setFieldError(fieldEl, hasError) {
  fieldEl.classList.toggle('field--error', hasError);
}

function clearErrorOnFocus(inputEl, fieldEl) {
  inputEl.addEventListener('focus', () => setFieldError(fieldEl, false), { once: false });
}

export function initRSVP() {
  const submitBtn = document.getElementById('rsvp-submit');
  const formWrap  = document.getElementById('rsvp-form-wrap');
  if (!submitBtn || !formWrap) return;

  const nameInput  = document.getElementById('name');
  const emailInput = document.getElementById('email');
  const nameField  = nameInput.closest('.field');
  const emailField = emailInput.closest('.field');

  clearErrorOnFocus(nameInput,  nameField);
  clearErrorOnFocus(emailInput, emailField);

  submitBtn.addEventListener('click', () => {
    const name     = nameInput.value.trim();
    const email    = emailInput.value.trim();
    const attending = document.getElementById('attending').value;
    const guests   = document.getElementById('guests').value;
    const dietary  = document.getElementById('dietary').value.trim();

    // Validate
    let hasError = false;
    if (!name)  { setFieldError(nameField,  true); hasError = true; }
    if (!email) { setFieldError(emailField, true); hasError = true; }
    if (hasError) return;

    // TODO: POST to your backend (Formspree, Airtable, Supabase, etc.)
    // Example with Formspree:
    // fetch('https://formspree.io/f/YOUR_ID', {
    //   method: 'POST',
    //   headers: { 'Content-Type': 'application/json' },
    //   body: JSON.stringify({ name, email, attending, guests, dietary }),
    // });

    console.log('RSVP:', { name, email, attending, guests, dietary });

    formWrap.innerHTML = `
      <p class="rsvp-success">
        Thank you, ${escapeHtml(name)}!<br>
        We can't wait to celebrate with you. ✦
      </p>
    `;
  });
}
