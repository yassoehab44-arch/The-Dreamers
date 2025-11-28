<!doctype html>
<html lang="en" dir="ltr">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Donate — The Dreamers Orphanage</title>
  <style>
    :root{--accent:#ff6b6b;--muted:#6b7280;--bg:#f7f7fb}
    *{box-sizing:border-box}
    body{margin:0;font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;background:var(--bg);color:#111;line-height:1.4}
    header{background:white;box-shadow:0 2px 6px rgba(16,24,40,.06);padding:18px 20px;display:flex;align-items:center;justify-content:space-between}
    .brand{display:flex;gap:12px;align-items:center}
    .brand img{width:64px;height:64px;object-fit:contain;border-radius:10px;background:#fff}
    .brand h1{font-size:18px;margin:0}
    nav{display:flex;gap:14px;align-items:center}
    a.btn{background:var(--accent);color:white;padding:10px 14px;border-radius:10px;text-decoration:none;font-weight:600}
    .container{max-width:1100px;margin:28px auto;padding:0 20px}
    .hero{display:grid;grid-template-columns:1fr 420px;gap:28px;align-items:start}
    .card{background:white;border-radius:14px;padding:20px;box-shadow:0 6px 18px rgba(12,18,35,.05)}
    .hero h2{margin:0 0 10px;font-size:24px}
    .muted{color:var(--muted)}
    .stats{display:flex;gap:12px;margin-top:12px;flex-wrap:wrap}
    .stat{background:#fff6f6;padding:12px;border-radius:10px;min-width:120px}
    .stat strong{display:block;font-size:18px}
    form label{display:block;margin:10px 0 6px;font-weight:600}
    input[type=text],input[type=email],input[type=number],select{width:100%;padding:10px;border-radius:8px;border:1px solid #e6e9ef}
    .inline{display:flex;gap:10px}
    .inline .half{flex:1}
    .donate-amt{display:flex;gap:8px;flex-wrap:wrap;margin-top:8px}
    .donate-amt button{padding:8px 12px;border-radius:10px;border:1px solid #eee;background:white;cursor:pointer}
    .donate-amt button.active{background:var(--accent);color:white;border-color:transparent}
    .submit{width:100%;padding:12px;border-radius:10px;border:0;background:var(--accent);color:white;font-weight:700;margin-top:14px;cursor:pointer}
    .why{display:grid;grid-template-columns:repeat(auto-fit,minmax(220px,1fr));gap:12px;margin-top:18px}
    .why-item{padding:14px;border-radius:10px;background:linear-gradient(180deg,#fff,#fff);border:1px solid #f1f5f9}
    footer{margin:28px 0 60px;color:var(--muted);text-align:center}
    @media (max-width:880px){
      .hero{grid-template-columns:1fr;}
      .brand img{width:54px;height:54px}
    }
  </style>
</head>
<body>
  <header>
    <div class="brand">
      <!-- Replace with your real logo file -->
      <img src="yasso.jpg" alt="The Dreamers logo" id="site-logo"/>
      <div>
        <h1>The Dreamers</h1>
        <div class="muted">Charity supporting orphaned children</div>
      </div>
    </div>
    <nav aria-label="Main navigation">
      <a href="#about">About</a>
      <a href="#donate" class="btn">Donate Now</a>
    </nav>
  </header>

  <main class="container">
    <section class="hero" aria-labelledby="hero-heading">
      <div class="card">
        <h2 id="hero-heading">Help a child reach their dream</h2>
        <p class="muted"><strong>The Dreamers Orphanage</strong> believes every child deserves love, education, and a safe place to grow. Your donation supports our education programs, healthcare, and psychosocial services for orphaned children.</p>

        <div class="stats" aria-hidden="false">
          <div class="stat" aria-live="polite">
            <strong id="stat-supported">1,250+</strong>
            Children supported
          </div>
          <div class="stat">
            <strong id="stat-projects">48</strong>
            Active projects
          </div>
        </div>

        <div class="why" aria-hidden="false">
          <div class="why-item">
            <strong>Education</strong>
            <p class="muted">School supplies, scholarships, and vocational training.</p>
          </div>
          <div class="why-item">
            <strong>Healthcare</strong>
            <p class="muted">Basic medical care and regular check-ups.</p>
          </div>
          <div class="why-item">
            <strong>Psychosocial Support</strong>
            <p class="muted">Counseling and family support programs.</p>
          </div>
        </div>
      </div>

      <aside class="card" id="donate" aria-labelledby="donate-heading">
        <h3 id="donate-heading">Make a Donation</h3>
        <form id="donation-form" onsubmit="return handleDonate(event)" novalidate>
          <label>Amount</label>
          <div class="donate-amt" role="list" aria-label="Preset donation amounts">
            <button type="button" class="amt" data-amount="50" aria-pressed="false">50 EGP</button>
            <button type="button" class="amt" data-amount="100" aria-pressed="false">100 EGP</button>
            <button type="button" class="amt" data-amount="250" aria-pressed="false">250 EGP</button>
            <button type="button" class="amt" data-amount="500" aria-pressed="false">500 EGP</button>
          </div>

          <label for="other">Other amount (EGP)</label>
          <input id="other" name="other" type="number" min="1" step="1" inputmode="numeric" placeholder="Enter an amount (EGP)" aria-describedby="amount-help" />

          <div id="amount-help" class="muted" style="font-size:13px;margin-top:6px">Choose a preset amount above or enter a custom amount in Egyptian Pounds (EGP).</div>

          <div class="inline" style="margin-top:8px">
            <div class="half">
              <label for="name">Full name</label>
              <input id="name" name="name" type="text" required autocomplete="name" />
            </div>
            <div class="half">
              <label for="email">Email address</label>
              <input id="email" name="email" type="email" required autocomplete="email" />
            </div>
          </div>

          <label for="method">Payment method</label>
          <select id="method" name="method" aria-label="Payment method">
            <option value="card">Card (Visa/Master)</option>
            <option value="wallet">Digital wallet</option>
            <option value="cash">Cash on delivery</option>
          </select>

          <button class="submit" type="submit">Confirm Donation</button>
        </form>

        <p class="muted" style="font-size:13px;margin-top:12px">Note: This is a template. To accept real payments, connect this form to a secure payment gateway (Stripe, PayPal, Fawry, or your bank) and handle server-side payment processing and webhooks.</p>
      </aside>
    </section>

    <section class="card" id="about" style="margin-top:18px">
      <h3>About Us</h3>
      <p class="muted">The Dreamers Orphanage is a non-profit organization dedicated to improving the lives of orphaned children through education, healthcare, and emotional support. Our vision: a world where every child has opportunity. Our mission: provide sustainable, meaningful care to children who need it most.</p>
      <p style="margin-top:10px">Contact: <strong>contact@thedreamers.org</strong> | Phone: <strong>0100376786</strong></p>
    </section>
  </main>

  <footer>
    &copy; <span id="year"></span> The Dreamers — All rights reserved
  </footer>

  <script>
    // auto year
    document.getElementById('year').textContent = new Date().getFullYear();

    // donation amount preset buttons
    const amtButtons = document.querySelectorAll('.amt');
    const otherInput = document.getElementById('other');

    amtButtons.forEach(b => {
      b.addEventListener('click', () => {
        amtButtons.forEach(x => { x.classList.remove('active'); x.setAttribute('aria-pressed','false'); });
        b.classList.add('active');
        b.setAttribute('aria-pressed','true');
        otherInput.value = b.dataset.amount;
      });
    });

    function isValidEmail(email) {
      return /^[^\s@]+@[^\s@]+\.[^\s@]+$/.test(email);
    }

    function handleDonate(e) {
      e.preventDefault();

      const name = document.getElementById('name').value.trim();
      const email = document.getElementById('email').value.trim();
      const amountRaw = otherInput.value.trim();
      const amount = Number(amountRaw);

      if (!name) {
        alert('Please enter your full name.');
        return false;
      }
      if (!email || !isValidEmail(email)) {
        alert('Please enter a valid email address.');
        return false;
      }
      if (!amountRaw || isNaN(amount) || amount <= 0) {
        alert('Please enter a valid donation amount greater than zero.');
        return false;
      }

      // Demo success notification.
      // Replace this section with a secure server call to process the payment (fetch to your API).
      alert(`Thank you, ${name}! We received a donation request of ${amount} EGP. We will contact you at ${email} to complete the donation.`);

      // Example (commented) server request:
      // fetch('/api/donate', {
      //   method: 'POST',
      //   headers: { 'Content-Type': 'application/json' },
      //   body: JSON.stringify({ name, email, amount, method: document.getElementById('method').value })
      // }).then(r => r.json()).then(data => { /* handle payment redirection or confirmation */ });

      document.getElementById('donation-form').reset();
      amtButtons.forEach(x => { x.classList.remove('active'); x.setAttribute('aria-pressed','false'); });
      return false;
    }
  </script>
</body>
</html>
