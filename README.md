#ZIVA REGISTRATION FORM
🔶ZIVA  official website
<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>ZIVA Catering — Labourers Registration</title>
  <meta name="description" content="ZIVA Catering and Events labourers registration form" />
  <style>
    :root{
      --bg:#fafafa;--card:#ffffff;--muted:#6b7280;
      --accent:#0f766e;--accent-2:#065f46;
      --success:#16a34a;--danger:#dc2626;
      font-family:Inter,system-ui,-apple-system,"Segoe UI",Roboto,"Helvetica Neue",Arial;
    }
    *{box-sizing:border-box}
    body{
      margin:0;
      min-height:100vh;
      background:linear-gradient(180deg,rgba(6,95,70,0.03),rgba(6,95,70,0.01)),var(--bg);
      display:flex;align-items:center;justify-content:center;
      padding:32px;
    }
    .wrap{width:100%;max-width:980px;display:grid;grid-template-columns:420px 1fr;gap:28px}
    .card{background:linear-gradient(180deg,rgba(255,255,255,0.9),var(--card));
      border-radius:14px;padding:26px;
      box-shadow:0 8px 30px rgba(15,23,42,0.06);
      border:1px solid rgba(15,23,42,0.03);}
    .brand{display:flex;gap:12px;align-items:center;margin-bottom:18px}
    .logo{width:64px;height:64px;border-radius:10px;display:grid;place-items:center;
      background:linear-gradient(135deg,var(--accent),var(--accent-2));
      color:#fff;font-weight:700;font-size:20px;box-shadow:0 6px 18px rgba(6,95,70,0.12);}
    .brand h1{margin:0;font-size:20px;letter-spacing:.8px}
    .brand p{margin:0;color:var(--muted);font-size:13px}
    form .row{display:flex;gap:12px;margin-bottom:12px}
    label{display:block;font-size:13px;margin-bottom:6px;color:#374151}
    input,select,textarea{width:100%;padding:10px 12px;border-radius:8px;
      border:1px solid rgba(15,23,42,0.08);background:#fff;font-size:14px;outline:none}
    input:focus,select:focus,textarea:focus{box-shadow:0 0 0 4px rgba(6,95,70,0.06);
      border-color:rgba(6,95,70,0.25);}
    .small{font-size:12px;color:var(--muted)}
    .phone-group{display:flex;gap:8px;align-items:center}
    .cc{min-width:72px;display:inline-flex;align-items:center;justify-content:center;
      padding:10px 8px;border-radius:8px;
      background:linear-gradient(180deg,#f7fdfc,#fff);
      border:1px solid rgba(15,23,42,0.04);font-weight:600;color:var(--accent-2);}
    .actions{display:flex;gap:12px;align-items:center;margin-top:8px}
    .btn{padding:10px 14px;border-radius:10px;border:0;cursor:pointer;font-weight:600;font-size:14px}
    .btn-primary{background:linear-gradient(90deg,var(--accent),var(--accent-2));
      color:#fff;box-shadow:0 8px 20px rgba(6,95,70,0.12);}
    .btn-ghost{background:transparent;border:1px solid rgba(15,23,42,0.06);color:#0f172a}
    .note{font-size:13px;color:var(--muted);margin-top:10px}
    .hero{background:linear-gradient(180deg,rgba(255,255,255,0.78),rgba(255,255,255,0.95));
      border-radius:14px;padding:28px;display:flex;flex-direction:column;justify-content:center;gap:10px;
      border:1px solid rgba(15,23,42,0.03);box-shadow:0 10px 40px rgba(2,6,23,0.03);}
    .hero h2{margin:0;font-size:22px}
    .hero p{margin:0;color:var(--muted);line-height:1.5}
    .message{display:none;align-items:center;gap:10px;padding:10px 12px;border-radius:8px;
      background:rgba(16,185,129,0.08);color:var(--success);
      border:1px solid rgba(16,185,129,0.12);font-weight:600}
    .message.show{display:flex}
    @media(max-width:880px){.wrap{grid-template-columns:1fr}}
  </style>
</head>
<body>
<div class="wrap">
  <section class="card">
    <div class="brand">
      <div class="logo">ZIVA</div>
      <div>
        <h1>ZIVA</h1>
        <p>Catering and Events — Team Registration</p>
      </div>
    </div>

    <div class="message" id="successMsg">✅ Registration successful! Welcome to ZIVA family!</div>

    <form id="zivaForm" novalidate>
      <div><label>Full Name *</label><input name="fullname" required placeholder="Enter full name"></div>
      <div class="row">
        <div><label>Age *</label><input name="age" type="number" min="15" max="80" required></div>
        <div><label>Height (cm) *</label><input name="height" type="number" min="100" max="250" required></div>
      </div>
      <div>
        <label>Phone Number *</label>
        <div class="phone-group">
          <div class="cc">+91</div><input name="phone" required placeholder="98765 43210" pattern="[0-9\s\-]{6,15}">
        </div>
        <div class="small">Use Indian mobile number (+91)</div>
      </div>
      <div><label>Experience (Optional)</label><textarea name="experience" rows="3"></textarea></div>
      <div><label>Preferred Role</label>
        <select name="role">
          <option value="">— Select a role —</option>
          <option>Cook</option><option>Server</option><option>Cleaner</option>
          <option>Helper</option><option>Manager</option>
        </select>
      </div>
      <div class="actions">
        <button class="btn btn-primary" type="submit">Join ZIVA Family</button>
        <button class="btn btn-ghost" type="button" id="clearBtn">Clear</button>
      </div>
      <div class="note">NB: Registration is mandatory. Non-registered individuals will not be assigned work.</div>
    </form>
  </section>
<div style="display:flex;gap:10px;margin-top:12px;align-items:center">
      <button class="btn btn-primary" id="startBtn">Start Your Journey</button>
      <a>View Original</a>
    </div>
  </aside>
</div>
  <aside class="hero">
    <h2>Welcome to ZIVA Family!</h2>
    <p>We’re excited to have you join our catering and events team. Fill the form to register as a team member for upcoming ZIVA projects.</p>
<script>
const form=document.getElementById('zivaForm'),
      msg=document.getElementById('successMsg'),
      clearBtn=document.getElementById('clearBtn'),
      startBtn=document.getElementById('startBtn');

function showSuccess(){msg.classList.add('show');setTimeout(()=>msg.classList.remove('show'),5000);}
function save(data){
  const key='ziva_registrations';
  const arr=JSON.parse(localStorage.getItem(key)||'[]');
  arr.push(data);
  localStorage.setItem(key,JSON.stringify(arr));
}
function normalizePhone(p){const d=p.replace(/\D+/g,'');return d.length===10?'+91'+d:'+'+d;}
form.addEventListener('submit',e=>{
  e.preventDefault();
  const f=form.fullname.value.trim(),a=form.age.value,h=form.height.value,p=form.phone.value.trim();
  if(!f||!a||!h||!p){alert('Please fill required fields.');return;}
  save({fullname:f,age:a,height:h,phone:normalizePhone(p),
        experience:form.experience.value.trim(),role:form.role.value,registeredAt:new Date().toISOString()});
  form.reset();showSuccess();startBtn.focus();
});
clearBtn.onclick=()=>{if(confirm('Clear the form?'))form.reset();}
startBtn.onclick=()=>form.fullname.focus();
</script>
</body>
</html>
