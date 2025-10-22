# ZIVA-REGISTER-FOAM
Ziva website
<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>ZIVA Catering — Labourers Registration</title>
  <meta name="description" content="Ziva Catering and Events labourers registration form" />
  <style>
    /* Reset & base */
    :root{
      --bg: #fafafa;
      --card: #ffffff;
      --muted: #6b7280;
      --accent: #0f766e;
      --accent-2: #065f46;
      --success: #16a34a;
      --danger: #dc2626;
      --glass: rgba(255,255,255,0.6);
      font-family: Inter, system-ui, -apple-system, "Segoe UI", Roboto, "Helvetica Neue", Arial;
    }
    *{box-sizing:border-box}
    html,body{height:100%}
    body{
      margin:0;
      background:
        linear-gradient(180deg, rgba(6,95,70,0.03), rgba(6,95,70,0.01)),
        var(--bg);
      -webkit-font-smoothing:antialiased;
      -moz-osx-font-smoothing:grayscale;
      display:flex;
      align-items:center;
      justify-content:center;
      padding:32px;
    }

    /* Container */
    .wrap{
      width:100%;
      max-width:980px;
      display:grid;
      grid-template-columns: 420px 1fr;
      gap:28px;
      align-items:stretch;
    }

    /* Left panel (branding + form) */
    .card{
      background:linear-gradient(180deg, rgba(255,255,255,0.9), var(--card));
      border-radius:14px;
      padding:26px;
      box-shadow: 0 8px 30px rgba(15,23,42,0.06);
      border: 1px solid rgba(15,23,42,0.03);
    }

    .brand{
      display:flex;
      gap:12px;
      align-items:center;
      margin-bottom:18px;
    }
    .logo{
      width:64px;
      height:64px;
      border-radius:10px;
      flex:0 0 64px;
      display:inline-grid;
      place-items:center;
      background: linear-gradient(135deg,var(--accent),var(--accent-2));
      color: #fff;
      font-weight:700;
      font-size:20px;
      box-shadow: 0 6px 18px rgba(6,95,70,0.12);
    }
    .brand h1{
      margin:0;
      font-size:20px;
      letter-spacing:0.8px;
    }
    .brand p{margin:0;color:var(--muted);font-size:13px}

    form .row{
      display:flex;
      gap:12px;
      margin-bottom:12px;
    }
    label{display:block;font-size:13px;margin-bottom:6px;color:#374151}
    input[type="text"], input[type="number"], select, textarea {
      width:100%;
      padding:10px 12px;
      border-radius:8px;
      border:1px solid rgba(15,23,42,0.08);
      background: #fff;
      outline:none;
      font-size:14px;
    }
    input[type="text"]:focus, input[type="number"]:focus, select:focus, textarea:focus {
      box-shadow: 0 0 0 4px rgba(6,95,70,0.06);
      border-color: rgba(6,95,70,0.25);
    }

    .small{font-size:12px;color:var(--muted)}

    .phone-group{display:flex;gap:8px;align-items:center}
    .cc{
      min-width:72px;
      display:inline-flex;
      align-items:center;
      justify-content:center;
      padding:10px 8px;
      border-radius:8px;
      background: linear-gradient(180deg, #f7fdfc, #ffffff);
      border:1px solid rgba(15,23,42,0.04);
      font-weight:600;
      color:var(--accent-2);
    }

    .actions{
      display:flex;
      gap:12px;
      align-items:center;
      margin-top:8px;
    }
    button.btn{
      padding:10px 14px;
      border-radius:10px;
      border:0;
      cursor:pointer;
      font-weight:600;
      font-size:14px;
    }
    .btn-primary{
      background: linear-gradient(90deg,var(--accent),var(--accent-2));
      color: #fff;
      box-shadow: 0 8px 20px rgba(6,95,70,0.12);
    }
    .btn-ghost{
      background:transparent;
      border:1px solid rgba(15,23,42,0.06);
      color:#0f172a;
    }

    .note{font-size:13px;color:var(--muted);margin-top:10px}

    /* Right panel (welcome & hero) */
    .hero{
      background: linear-gradient(180deg, rgba(255,255,255,0.78), rgba(255,255,255,0.95));
      border-radius:14px;
      padding:28px;
      display:flex;
      flex-direction:column;
      justify-content:center;
      gap:10px;
      border:1px solid rgba(15,23,42,0.03);
      box-shadow: 0 10px 40px rgba(2,6,23,0.03);
    }
    .hero h2{margin:0;font-size:22px}
    .hero p{margin:0;color:var(--muted);line-height:1.5}

    /* Success / message */
    .message{
      display:none;
      align-items:center;
      gap:10px;
      padding:10px 12px;
      border-radius:8px;
      background: rgba(16,185,129,0.08);
      color: var(--success);
      border:1px solid rgba(16,185,129,0.12);
      font-weight:600;
    }
    .message.show{display:flex}

    /* small screens */
    @media (max-width:880px){
      .wrap{grid-template-columns:1fr; padding:0}
      .brand h1{font-size:18px}
    }

    footer.small-centered{
      margin-top:12px;
      font-size:12px;
      color:var(--muted);
      text-align:center;
    }

    /* accessibility focus outlines */
    button:focus, a:focus {outline:3px solid rgba(6,95,70,0.12); outline-offset:2px}
  </style>
</head>
<body>
  <div class="wrap">
    <!-- Left: Form -->
    <section class="card" aria-labelledby="form-title">
      <div class="brand" role="img" aria-label="ziva Catering Logo">
        <div class="logo">ZIVA</div>
        <div>
          <h1>ziva</h1>
          <p>Catering and Events — Team Registration</p>
        </div>
      </div>

      <div id="form-area">
        <div class="message" id="successMsg" role="status" aria-live="polite">
          <span style="font-size:20px;">✅</span>
          <div>Registration successful! Welcome to ziva family!</div>
        </div>

        <form id="ziva Form" novalidate>
          <div>
            <label for="fullname">Full Name *</label>
            <input id="fullname" name="fullname" type="text" placeholder="Enter full name" required autocomplete="name" />
          </div>

          <div class="row">
            <div style="flex:1;">
              <label for="age">Age *</label>
              <input id="age" name="age" type="number" placeholder="e.g. 28" min="15" max="80" required />
            </div>
            <div style="flex:1;">
              <label for="height">Height (cm) *</label>
              <input id="height" name="height" type="number" placeholder="e.g. 170" min="100" max="250" required />
            </div>
          </div>

          <div>
            <label for="phone">Phone Number *</label>
            <div class="phone-group">
              <div class="cc">+91</div>
              <input id="phone" name="phone" type="text" inputmode="tel" placeholder="98765 43210" pattern="[0-9\s\-]{6,15}" required />
            </div>
            <div class="small">Use Indian mobile number (we store +91 by default)</div>
          </div>

          <div>
            <label for="experience">Experience (Optional)</label>
            <textarea id="experience" name="experience" rows="3" placeholder="Briefly describe any experience (e.g. cook, waiter)"></textarea>
          </div>

          <div>
            <label for="role">Preferred Role (Optional)</label>
            <select id="role" name="role" aria-placeholder="Select a role">
              <option value="">— Select a role —</option>
              <option>Cook</option>
              <option>Server</option>
              <option>Cleaner</option>
              <option>Helper</option>
              <option>Manager</option>
            </select>
          </div>

          <div class="actions">
            <button type="submit" class="btn btn-primary" id="submitBtn">Join ziva Family</button>
            <button type="button" class="btn btn-ghost" id="clearBtn">Clear</button>
          </div>

          <div class="note">NB: Registration is mandatory. Individuals who do not register will not be assigned work. This is needed for scheduling and payroll.</div>
        </form>

        <footer class="small-centered">
          <small>Form reference: ziva Catering and Events — Labourers Registration</small>
        </footer>
      </div>
    </section>

    <!-- Right: Hero/Welcome -->
    <aside class="hero" aria-labelledby="welcome-title">
      <h2 id="welcome-title">Welcome to ziva Family!</h2>
      <p>We're thrilled to have you join our team of culinary professionals. Your journey with ziva Catering and Events begins now!</p>
      <p>Get ready to create unforgettable experiences and be part of something extraordinary. Please fill the form to register as a team member for ziva projects.</p>

      <div style="display:flex;gap:10px;margin-top:12px;align-items:center">
        <button class="btn btn-primary" id="startBtn">Start Your Journey</button>
        <a href="https://askakicks.github.io/ziva-CATERING-AND-EVENTS-LABOURERS-REGISTRATION-FROM-/" target="_blank" rel="noopener" class="btn btn-ghost" style="text-decoration:none;padding:10px 12px;border-radius:10px">Open Original</a>
      </div>
    </aside>
  </div>

  <script>
    // DOM refs
    const form = document.getElementById('kasaForm');
    const successMsg = document.getElementById('successMsg');
    const submitBtn = document.getElementById('submitBtn');
    const clearBtn = document.getElementById('clearBtn');
    const startBtn = document.getElementById('startBtn');

    // Utility: show a transient success message
    function showSuccess() {
      successMsg.classList.add('show');
      setTimeout(()=> successMsg.classList.remove('show'), 7000);
    }

    // Save registration to localStorage (for demo; in real use send to server)
    function saveRegistration(data) {
      const key = 'ZIVA_registrations_v1';
      const existing = JSON.parse(localStorage.getItem(key) || "[]");
      existing.push(data);
      localStorage.setItem(key, JSON.stringify(existing, null, 2));
    }

    // Basic phone normalization
    function normalizePhone(raw) {
      if (!raw) return '';
      // remove non-digits
      const digits = raw.replace(/\\D+/g, '');
      // if user typed 10-digit number, prefix +91
      if (digits.length === 10) return '+91' + digits;
      if (digits.startsWith('0') && digits.length === 11) return '+91' + digits.slice(1);
      if (digits.startsWith('91') && digits.length===12) return '+'+digits;
      // fallback: return as-is with + prefix
      return (digits ? ('+' + digits) : '');
    }

    // Validate pattern-friendly phone
    function isPhoneValid(raw){
      const digits = raw.replace(/\\D+/g,'');
      return digits.length >= 10 && digits.length <= 13;
    }

    form.addEventListener('submit', (e) => {
      e.preventDefault();

      // Manual validation for accessibility & better feedback
      const fullname = form.fullname.value.trim();
      const age = Number(form.age.value);
      const height = Number(form.height.value);
      const phoneRaw = form.phone.value.trim();
      const experience = form.experience.value.trim();
      const role = form.role.value;

      // required checks
      if (!fullname) { alert('Please enter full name.'); form.fullname.focus(); return; }
      if (!age || age < 15 || age > 80) { alert('Please enter a valid age (15–80).'); form.age.focus(); return; }
      if (!height || height < 100 || height > 250) { alert('Please enter a valid height in cm.'); form.height.focus(); return; }
      if (!phoneRaw || !isPhoneValid(phoneRaw)) { alert('Please enter a valid phone number (10 digits).'); form.phone.focus(); return; }

      // Build payload
      const payload = {
        fullname,
        age,
        height,
        phone: normalizePhone(phoneRaw),
        experience,
        role,
        registeredAt: new Date().toISOString()
      };

      // Save locally (demo). Replace with fetch() POST to your server when ready.
      try {
        saveRegistration(payload);
      } catch (err) {
        console.error('Local save failed', err);
      }

      // Show success UI
      showSuccess();

      // Clear form but keep last entered name (optional)
      form.reset();

      // small UX: focus start button
      startBtn.focus();
    });

    clearBtn.addEventListener('click', () => {
      if (confirm('Clear the form?')) form.reset();
    });

    startBtn.addEventListener('click', () => {
      // Jump to form (small UX)
      document.getElementById('fullname').focus();
      window.scrollTo({top:0,behavior:'smooth'});
    });

    // Accessibility: allow Enter on start button to focus form
    document.addEventListener('keydown', (e) => {
      if (e.key === 'Escape') {
        // hide success if visible
        successMsg.classList.remove('show');
      }
    });
  </script>
</body>
</html>
