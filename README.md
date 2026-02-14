<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <meta name="theme-color" content="#22d3ee" />
  <title>Confirmación | KOAPE</title>

  <style>
    :root{
      --bg1:#f7fbff;
      --bg2:#eaf6ff;
      --card: rgba(255,255,255,.78);
      --border: rgba(255,255,255,.65);
      --text:#0b1220;
      --muted:#5b6b82;
      --cyan:#22d3ee;
      --cyan2:#0ea5e9;
      --shadow: 0 24px 60px rgba(10, 25, 60, .16);
      --shadow2: 0 10px 22px rgba(10, 25, 60, .12);
      --radius: 22px;
    }

    *{ box-sizing:border-box; }
    html,body{ height:100%; }
    body{
      margin:0;
      font-family: ui-sans-serif, system-ui, -apple-system, Segoe UI, Roboto, Arial, "Apple Color Emoji","Segoe UI Emoji";
      color:var(--text);
      background:
        radial-gradient(1100px 700px at 20% 20%, rgba(34,211,238,.22), transparent 60%),
        radial-gradient(900px 650px at 80% 30%, rgba(14,165,233,.18), transparent 55%),
        linear-gradient(180deg, var(--bg1), var(--bg2));
      display:flex;
      align-items:center;
      justify-content:center;
      padding: 20px;
    }

    .wrap{
      width:min(980px, 100%);
      display:grid;
      grid-template-columns: 1.1fr .9fr;
      gap: 22px;
      align-items:stretch;
    }

    @media (max-width: 880px){
      .wrap{ grid-template-columns: 1fr; }
    }

    .hero, .card{
      border-radius: var(--radius);
      background: var(--card);
      backdrop-filter: blur(12px);
      -webkit-backdrop-filter: blur(12px);
      border: 1px solid var(--border);
      box-shadow: var(--shadow);
      overflow:hidden;
      position:relative;
    }

    .hero{
      padding: 28px 26px 26px;
      min-height: 420px;
    }

    .hero:before{
      content:"";
      position:absolute;
      inset:-80px -80px auto auto;
      width: 320px;
      height: 320px;
      background: radial-gradient(circle at 30% 30%, rgba(34,211,238,.55), rgba(14,165,233,.08) 70%, transparent 72%);
      filter: blur(0px);
      transform: rotate(12deg);
      pointer-events:none;
    }

    .brand{
      display:flex;
      align-items:center;
      gap: 12px;
    }

    .logo{
      width: 44px;
      height: 44px;
      border-radius: 14px;
      box-shadow: var(--shadow2);
      overflow:hidden;
      flex: 0 0 auto;
      background: linear-gradient(135deg, rgba(34,211,238,.9), rgba(14,165,233,.92));
    }

    .brand h1{
      font-size: 18px;
      margin:0;
      letter-spacing:.18em;
      font-weight: 800;
    }

    .brand p{
      margin: 2px 0 0;
      font-size: 13px;
      color: var(--muted);
    }

    .hero h2{
      margin: 20px 0 10px;
      font-size: clamp(22px, 3.6vw, 34px);
      line-height: 1.1;
      letter-spacing: -0.02em;
    }

    .hero .subtitle{
      margin: 0 0 18px;
      color: var(--muted);
      font-size: 14.5px;
      line-height: 1.5;
      max-width: 56ch;
    }

    .features{
      display:grid;
      grid-template-columns: 1fr 1fr;
      gap: 12px;
      margin-top: 16px;
    }

    @media (max-width: 520px){
      .features{ grid-template-columns: 1fr; }
    }

    .feat{
      border-radius: 16px;
      border: 1px solid rgba(14,165,233,.15);
      background: linear-gradient(180deg, rgba(255,255,255,.7), rgba(255,255,255,.4));
      padding: 12px 12px;
      box-shadow: 0 8px 18px rgba(10, 25, 60, .06);
    }

    .feat .t{
      display:flex;
      align-items:center;
      gap: 10px;
      font-weight: 700;
      font-size: 14px;
      margin:0;
    }

    .dot{
      width: 10px;
      height: 10px;
      border-radius: 999px;
      background: linear-gradient(135deg, var(--cyan), var(--cyan2));
      box-shadow: 0 8px 18px rgba(14,165,233,.24);
      flex: 0 0 auto;
    }

    .feat .d{
      margin: 6px 0 0;
      font-size: 13px;
      color: var(--muted);
      line-height: 1.45;
    }

    /* Right card */
    .card{
      padding: 22px 20px 18px;
      display:flex;
      flex-direction:column;
      justify-content:space-between;
      min-height: 420px;
    }

    .card header{
      display:flex;
      align-items:flex-start;
      justify-content:space-between;
      gap: 14px;
    }

    .pill{
      display:inline-flex;
      align-items:center;
      gap: 8px;
      padding: 8px 12px;
      border-radius: 999px;
      font-size: 12.5px;
      color: #055d7a;
      background: rgba(34,211,238,.16);
      border: 1px solid rgba(34,211,238,.28);
      user-select:none;
    }

    .pill .spin{
      width: 14px;
      height: 14px;
      border-radius: 999px;
      border: 2px solid rgba(5,93,122,.25);
      border-top-color: rgba(5,93,122,.85);
      display:none;
      animation: spin .9s linear infinite;
    }
    @keyframes spin { to { transform: rotate(360deg); } }

    .card h3{
      margin: 12px 0 6px;
      font-size: 20px;
      letter-spacing: -.01em;
    }

    .card p{
      margin: 0 0 14px;
      color: var(--muted);
      font-size: 13.8px;
      line-height: 1.55;
    }

    .panel{
      border-radius: 18px;
      border: 1px solid rgba(14,165,233,.16);
      background: rgba(255,255,255,.64);
      padding: 14px;
      box-shadow: 0 10px 22px rgba(10, 25, 60, .06);
      margin-top: 12px;
    }

    .row{
      display:flex;
      align-items:center;
      justify-content:space-between;
      gap: 12px;
      padding: 10px 10px;
      border-radius: 14px;
      background: rgba(255,255,255,.55);
      border: 1px solid rgba(255,255,255,.8);
    }

    .row + .row{ margin-top: 10px; }

    .label{
      font-size: 12px;
      color: var(--muted);
      margin-bottom: 2px;
    }

    .value{
      font-size: 13.5px;
      font-weight: 700;
      color: var(--text);
      word-break: break-word;
    }

    .actions{
      display:flex;
      flex-direction:column;
      gap: 10px;
      margin-top: 14px;
    }

    .btn{
      appearance:none;
      border: none;
      border-radius: 16px;
      padding: 13px 14px;
      font-weight: 800;
      letter-spacing: .02em;
      cursor:pointer;
      transition: transform .06s ease, filter .12s ease, opacity .12s ease;
      display:flex;
      align-items:center;
      justify-content:center;
      gap: 10px;
      user-select:none;
    }

    .btn:active{ transform: translateY(1px); }
    .btn-primary{
      color: white;
      background: linear-gradient(135deg, var(--cyan), var(--cyan2));
      box-shadow: 0 18px 38px rgba(14,165,233,.22);
    }
    .btn-secondary{
      color: var(--text);
      background: rgba(255,255,255,.72);
      border: 1px solid rgba(14,165,233,.18);
    }
    .btn[disabled]{ opacity:.65; cursor:not-allowed; }

    .msg{
      margin-top: 14px;
      padding: 12px 12px;
      border-radius: 16px;
      border: 1px solid rgba(14,165,233,.16);
      background: rgba(255,255,255,.62);
      display:none;
    }

    .msg strong{ display:block; margin-bottom: 3px; }
    .msg.ok{ border-color: rgba(16,185,129,.26); }
    .msg.err{ border-color: rgba(244,63,94,.26); }

    .footer{
      margin-top: 14px;
      display:flex;
      justify-content:space-between;
      align-items:center;
      gap: 10px;
      color: var(--muted);
      font-size: 12px;
    }

    a{
      color: #0369a1;
      text-decoration: none;
      font-weight: 700;
    }
    a:hover{ text-decoration: underline; }

    /* Small phone tightening */
    @media (max-width: 420px){
      .hero{ padding: 22px 18px; }
      .card{ padding: 18px 16px 14px; }
    }
  </style>
</head>

<body>
  <main class="wrap">
    <!-- Left: brand/marketing -->
    <section class="hero" aria-label="KOAPE info">
      <div class="brand">
        <div class="logo" aria-hidden="true">
          <!-- Simple KOAPE mark (SVG) -->
          <svg viewBox="0 0 64 64" width="44" height="44" xmlns="http://www.w3.org/2000/svg" role="img" aria-label="KOAPE logo">
            <defs>
              <linearGradient id="g" x1="0" y1="0" x2="1" y2="1">
                <stop offset="0" stop-color="#22d3ee"/>
                <stop offset="1" stop-color="#0ea5e9"/>
              </linearGradient>
            </defs>
            <rect x="0" y="0" width="64" height="64" rx="18" fill="url(#g)"/>
            <path d="M18 38c8-2 12-10 18-14 5-3 11-2 14 2-3 9-10 18-22 18-4 0-7-1-10-6z"
                  fill="rgba(255,255,255,.92)"/>
            <path d="M18 30c2-7 8-12 16-12 4 0 7 1 9 3-6 2-10 7-13 10-4 3-8 4-12-1z"
                  fill="rgba(255,255,255,.78)"/>
          </svg>
        </div>
        <div>
          <h1>KOAPE</h1>
          <p>Confirmación de correo</p>
        </div>
      </div>

      <h2>Tu cuenta está a un paso de activarse.</h2>
      <p class="subtitle">
        Confirmá tu correo para empezar a explorar el mapa, ver lugares cercanos,
        crear publicaciones temporales y chatear con tu comunidad.
      </p>

      <div class="features">
        <div class="feat">
          <p class="t"><span class="dot"></span>Mapa dinámico</p>
          <p class="d">Descubrí lugares y actividades cerca tuyo.</p>
        </div>
        <div class="feat">
          <p class="t"><span class="dot"></span>Publicaciones temporales</p>
          <p class="d">Ventas, ferias, eventos — todo con duración.</p>
        </div>
        <div class="feat">
          <p class="t"><span class="dot"></span>Chats rápidos</p>
          <p class="d">Contactá al instante con otros usuarios.</p>
        </div>
        <div class="feat">
          <p class="t"><span class="dot"></span>Perfil seguro</p>
          <p class="d">Tu cuenta queda protegida con verificación.</p>
        </div>
      </div>
    </section>

    <!-- Right: confirmation card -->
    <section class="card" aria-label="Confirmación">
      <div>
        <header>
          <div>
            <div class="pill" id="statusPill">
              <span class="spin" id="spinner"></span>
              <span id="statusText">Listo para confirmar</span>
            </div>
            <h3>Confirmá tu correo</h3>
            <p>
              Verificamos que sos vos y activamos tu cuenta. Si este enlace expiró,
              pedí un nuevo correo desde la app.
            </p>
          </div>
        </header>

        <div class="panel" role="group" aria-label="Detalles">
          <div class="row">
            <div>
              <div class="label">Correo</div>
              <div class="value" id="emailValue">—</div>
            </div>
            <div class="pill" title="Dato de la URL">URL</div>
          </div>

          <div class="row">
            <div>
              <div class="label">Código / token</div>
              <div class="value" id="tokenValue">—</div>
            </div>
            <div class="pill" title="Dato de la URL">Token</div>
          </div>

          <div class="actions">
            <button class="btn btn-primary" id="confirmBtn">
              Confirmar correo
              <span aria-hidden="true">→</span>
            </button>
            <button class="btn btn-secondary" id="openAppBtn" type="button">
              Abrir KOAPE
            </button>
          </div>

          <div class="msg ok" id="okMsg" role="status" aria-live="polite">
            <strong>¡Correo confirmado!</strong>
            Ya podés volver a KOAPE e iniciar sesión.
          </div>

          <div class="msg err" id="errMsg" role="alert">
            <strong>No se pudo confirmar.</strong>
            El enlace puede haber expirado o ser inválido. Probá reenviar el correo desde la app.
          </div>
        </div>
      </div>

      <div class="footer">
        <span>© <span id="year"></span> KOAPE</span>
        <span>
          <a href="#" id="helpLink">Ayuda</a>
        </span>
      </div>
    </section>
  </main>

  <script>
    // --- Helpers UI ---
    const $ = (id) => document.getElementById(id);

    const statusPill = $("statusPill");
    const spinner = $("spinner");
    const statusText = $("statusText");

    const emailValue = $("emailValue");
    const tokenValue = $("tokenValue");

    const confirmBtn = $("confirmBtn");
    const openAppBtn = $("openAppBtn");

    const okMsg = $("okMsg");
    const errMsg = $("errMsg");

    $("year").textContent = new Date().getFullYear();

    function setStatus(type, text, spinning=false){
      statusText.textContent = text;
      spinner.style.display = spinning ? "inline-block" : "none";

      // reset styles
      statusPill.style.background = "rgba(34,211,238,.16)";
      statusPill.style.borderColor = "rgba(34,211,238,.28)";
      statusPill.style.color = "#055d7a";

      if(type === "ok"){
        statusPill.style.background = "rgba(16,185,129,.14)";
        statusPill.style.borderColor = "rgba(16,185,129,.26)";
        statusPill.style.color = "#065f46";
      }
      if(type === "err"){
        statusPill.style.background = "rgba(244,63,94,.12)";
        statusPill.style.borderColor = "rgba(244,63,94,.22)";
        statusPill.style.color = "#881337";
      }
    }

    function showMsg(which){
      okMsg.style.display = which === "ok" ? "block" : "none";
      errMsg.style.display = which === "err" ? "block" : "none";
    }

    // --- Read URL params (example: ?email=...&token=...) ---
    const params = new URLSearchParams(location.search);
    const email = params.get("email") || params.get("user") || "";
    const token = params.get("token") || params.get("code") || params.get("access_token") || "";

    emailValue.textContent = email ? email : "No detectado en la URL";
    tokenValue.textContent = token ? (token.length > 24 ? token.slice(0, 24) + "…" : token) : "No detectado en la URL";

    // --- Demo confirmation flow (replace with real API call) ---
    async function fakeConfirm(){
      // Simula llamada a servidor
      await new Promise(r => setTimeout(r, 1200));
      // Regla demo: si hay token => éxito
      return Boolean(token);
    }

    confirmBtn.addEventListener("click", async () => {
      showMsg(null);
      confirmBtn.disabled = true;
      setStatus("info", "Confirmando…", true);

      try{
        const ok = await fakeConfirm();

        if(ok){
          setStatus("ok", "Confirmado", false);
          showMsg("ok");
        }else{
          setStatus("err", "Enlace inválido", false);
          showMsg("err");
        }
      }catch(e){
        setStatus("err", "Error", false);
        showMsg("err");
      }finally{
        confirmBtn.disabled = false;
      }
    });

    // Deep link / fallback (cambialo por tu esquema real)
    openAppBtn.addEventListener("click", () => {
      // Ejemplo: koape://confirm?token=...
      const deepLink = "koape://open" + (token ? ("?token=" + encodeURIComponent(token)) : "");
      // Intentar abrir app:
      window.location.href = deepLink;

      // Fallback web (por si no existe el deep link):
      setTimeout(() => {
        // Poné tu web o store acá si querés
        // window.location.href = "https://koape.app";
      }, 800);
    });

    $("helpLink").addEventListener("click", (e) => {
      e.preventDefault();
      alert("Si el enlace expiró, reenviá el correo de confirmación desde la app KOAPE.");
    });
  </script>
</body>
</html>
