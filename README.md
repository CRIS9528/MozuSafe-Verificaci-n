
<style>
@import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@300;400;500;600;700;800;900&family=Poppins:wght@300;400;500;600;700&display=swap');

*{margin:0;padding:0;box-sizing:border-box}
:root{
  --y:#FFC107;--k:#0D0D0D;--d:#2B2B2B;--m:#A6A6A6;--l:#F2F2F2;--w:#FFFFFF;
  --g:#22C55E;--o:#F97316;--r:#EF4444;--b:#3B82F6;
}
body{font-family:'Poppins',sans-serif;background:#0D0D0D;color:#fff;min-height:100vh;overflow-x:hidden}

/* BG */
.bg-layer{position:fixed;inset:0;pointer-events:none;z-index:0;overflow:hidden}
.bg-grid{position:absolute;inset:0;background-image:linear-gradient(rgba(255,193,7,.025) 1px,transparent 1px),linear-gradient(90deg,rgba(255,193,7,.025) 1px,transparent 1px);background-size:50px 50px}
.bg-glow{position:absolute;width:600px;height:600px;border-radius:50%;background:radial-gradient(circle,rgba(255,193,7,.06) 0%,transparent 70%);top:-200px;right:-100px}
.bg-ring{position:absolute;border-radius:50%;border:1px solid rgba(255,193,7,.05)}
.bg-ring:nth-child(3){width:400px;height:400px;top:-100px;right:-100px;animation:spin 20s linear infinite}
.bg-ring:nth-child(4){width:700px;height:700px;top:-250px;right:-250px;animation:spin 35s linear infinite reverse}
@keyframes spin{to{transform:rotate(360deg)}}

/* NAV */
nav{position:sticky;top:0;z-index:200;display:flex;align-items:center;justify-content:space-between;padding:0 28px;height:60px;background:rgba(13,13,13,.97);border-bottom:1px solid rgba(255,193,7,.12);backdrop-filter:blur(16px)}
.nav-logo img{height:28px;display:block}
.nav-logo-fallback{font-family:'Montserrat',sans-serif;font-weight:900;font-size:18px;color:var(--y);letter-spacing:1px}
.nav-right{display:flex;align-items:center;gap:16px}
.live-badge{display:flex;align-items:center;gap:6px;font-size:11px;color:var(--m);letter-spacing:.5px}
.live-dot{width:6px;height:6px;border-radius:50%;background:var(--g);box-shadow:0 0 6px var(--g);animation:pulse 2s ease-in-out infinite}
@keyframes pulse{0%,100%{opacity:1}50%{opacity:.3}}
.nav-tabs{display:flex;gap:4px}
.ntab{padding:6px 16px;border-radius:6px;font-size:12px;font-weight:600;cursor:pointer;border:none;font-family:'Poppins',sans-serif;transition:all .2s;letter-spacing:.3px}
.ntab.on{background:var(--y);color:#0D0D0D}
.ntab.off{background:transparent;color:var(--m);border:1px solid rgba(255,255,255,.08)}
.ntab.off:hover{background:rgba(255,255,255,.05);color:#fff}

/* PAGES */
main{position:relative;z-index:10}
.page{display:none}.page.on{display:block}

/* ══════════ VERIFY PAGE ══════════ */
.verify-wrap{max-width:900px;margin:0 auto;padding:48px 24px}

.hero{text-align:center;margin-bottom:48px}
.hero-eyebrow{display:inline-flex;align-items:center;gap:8px;background:rgba(255,193,7,.1);border:1px solid rgba(255,193,7,.25);border-radius:100px;padding:5px 16px;font-size:10px;color:var(--y);letter-spacing:2px;font-weight:700;text-transform:uppercase;margin-bottom:20px}
.hero h1{font-family:'Montserrat',sans-serif;font-size:38px;font-weight:900;line-height:1.1;margin-bottom:10px}
.hero h1 em{color:var(--y);font-style:normal}
.hero p{color:var(--m);font-size:14px;max-width:460px;margin:0 auto;line-height:1.7}

/* Search box */
.search-box{background:rgba(255,255,255,.03);border:1px solid rgba(255,255,255,.09);border-radius:16px;padding:28px;margin-bottom:24px;position:relative;overflow:hidden}
.search-box::before{content:'';position:absolute;top:0;left:0;right:0;height:1px;background:linear-gradient(90deg,transparent,rgba(255,193,7,.4),transparent)}
.search-box h3{font-size:11px;letter-spacing:2px;text-transform:uppercase;color:var(--y);font-weight:700;margin-bottom:18px}
.search-row{display:flex;gap:12px}
.search-input{flex:1;padding:13px 18px;background:rgba(255,255,255,.06);border:1px solid rgba(255,255,255,.12);border-radius:10px;color:#fff;font-family:'Poppins',sans-serif;font-size:14px;transition:border-color .2s;outline:none}
.search-input:focus{border-color:var(--y);background:rgba(255,193,7,.04)}
.search-input::placeholder{color:rgba(166,166,166,.6)}
.search-btn{padding:13px 24px;background:var(--y);color:#0D0D0D;border:none;border-radius:10px;font-family:'Montserrat',sans-serif;font-weight:800;font-size:13px;cursor:pointer;letter-spacing:.5px;white-space:nowrap;transition:all .2s}
.search-btn:hover{background:#FFD54F;transform:translateY(-1px)}
.search-hint{margin-top:12px;font-size:11px;color:rgba(166,166,166,.5)}

/* Suggestions dropdown */
.suggestions{position:absolute;left:28px;right:28px;top:100%;background:#1a1a1a;border:1px solid rgba(255,193,7,.2);border-radius:10px;z-index:50;overflow:hidden;display:none;margin-top:4px;box-shadow:0 8px 32px rgba(0,0,0,.5)}
.sug-item{padding:11px 16px;cursor:pointer;font-size:13px;transition:background .15s;border-bottom:1px solid rgba(255,255,255,.04)}
.sug-item:last-child{border-bottom:none}
.sug-item:hover{background:rgba(255,193,7,.08)}
.sug-id{font-size:10px;color:var(--y);font-family:monospace;margin-right:8px}
.sug-wrap{position:relative}

/* Empty / not found */
.result-empty{text-align:center;padding:48px;background:rgba(239,68,68,.05);border:1px solid rgba(239,68,68,.15);border-radius:16px;display:none}
.result-empty h3{font-size:18px;color:#FCA5A5;margin-bottom:8px}
.result-empty p{font-size:13px;color:var(--m)}

/* Profile card */
.profile{background:rgba(255,255,255,.03);border:1px solid rgba(255,255,255,.09);border-radius:16px;overflow:hidden;display:none;animation:fadeUp .4s ease}
@keyframes fadeUp{from{opacity:0;transform:translateY(12px)}to{opacity:1;transform:translateY(0)}}

/* Status bar */
.status-bar{padding:20px 28px;display:flex;align-items:center;justify-content:space-between;gap:16px}
.status-bar.active{background:rgba(34,197,94,.08);border-bottom:1px solid rgba(34,197,94,.15)}
.status-bar.vacation{background:rgba(59,130,246,.08);border-bottom:1px solid rgba(59,130,246,.15)}
.status-bar.suspended{background:rgba(249,115,22,.08);border-bottom:1px solid rgba(249,115,22,.15)}
.status-bar.inactive{background:rgba(239,68,68,.08);border-bottom:1px solid rgba(239,68,68,.15)}
.status-left{display:flex;align-items:center;gap:16px}
.status-icon-big{font-size:36px}
.status-title{font-family:'Montserrat',sans-serif;font-weight:900;font-size:20px}
.status-bar.active .status-title{color:var(--g)}
.status-bar.vacation .status-title{color:var(--b)}
.status-bar.suspended .status-title{color:var(--o)}
.status-bar.inactive .status-title{color:var(--r)}
.status-desc{font-size:12px;color:var(--m);margin-top:2px;max-width:360px;line-height:1.5}
.status-meta{text-align:right;font-size:11px;color:var(--m);line-height:1.8}
.status-meta strong{color:rgba(255,255,255,.7);font-size:12px}

/* Profile body */
.prof-header{padding:24px 28px;display:flex;align-items:center;gap:20px;border-bottom:1px solid rgba(255,255,255,.06)}
.avatar{width:68px;height:68px;border-radius:50%;background:rgba(255,193,7,.12);border:2px solid rgba(255,193,7,.3);display:flex;align-items:center;justify-content:center;font-family:'Montserrat',sans-serif;font-weight:900;font-size:24px;color:var(--y);flex-shrink:0}
.prof-name{font-family:'Montserrat',sans-serif;font-size:20px;font-weight:800;line-height:1.2}
.prof-ced{font-size:12px;color:var(--m);margin-top:3px;font-family:monospace}
.prof-badge{display:inline-block;margin-top:7px;padding:3px 12px;background:rgba(255,193,7,.12);border:1px solid rgba(255,193,7,.25);border-radius:100px;font-size:11px;color:var(--y);font-weight:600}

/* Sections grid */
.prof-grid{display:grid;grid-template-columns:1fr 1fr 1fr;border-top:1px solid rgba(255,255,255,.06)}
.prof-section{padding:22px 24px;border-right:1px solid rgba(255,255,255,.05)}
.prof-section:last-child{border-right:none}
.sec-label{font-size:9px;text-transform:uppercase;letter-spacing:2px;color:var(--y);font-weight:700;margin-bottom:14px}
.info-row{margin-bottom:11px}
.info-k{font-size:10px;color:var(--m);margin-bottom:2px}
.info-v{font-size:13px;color:#fff;font-weight:500}

/* Certs */
.cert-list{display:flex;flex-direction:column;gap:7px}
.cert-item{display:flex;align-items:center;gap:8px;font-size:12px}
.cert-tick{width:18px;height:18px;border-radius:4px;display:flex;align-items:center;justify-content:center;font-size:11px;flex-shrink:0}
.cert-ok{background:rgba(34,197,94,.15);color:var(--g)}
.cert-no{background:rgba(255,255,255,.05);color:rgba(166,166,166,.5)}
.cert-label-ok{color:#fff}
.cert-label-no{color:rgba(166,166,166,.5);text-decoration:line-through}

/* Footer */
.prof-footer{padding:14px 28px;background:rgba(255,255,255,.02);border-top:1px solid rgba(255,255,255,.05);display:flex;align-items:center;justify-content:space-between}
.footer-co{font-size:11px;color:var(--m)}
.footer-co strong{color:rgba(255,255,255,.6)}
.footer-ts{font-size:10px;color:rgba(166,166,166,.4);font-family:monospace}

/* Contact strip */
.contact-strip{margin-top:20px;background:rgba(255,193,7,.06);border:1px solid rgba(255,193,7,.12);border-radius:12px;padding:16px 20px;display:flex;align-items:center;justify-content:space-between;gap:16px;flex-wrap:wrap}
.contact-item{font-size:12px;color:var(--m)}
.contact-item strong{color:var(--y);font-size:13px;display:block;margin-bottom:1px}

/* ══════════ ADMIN ══════════ */
.admin-wrap{display:grid;grid-template-columns:200px 1fr;min-height:calc(100vh - 60px)}
.sidebar{background:rgba(255,255,255,.02);border-right:1px solid rgba(255,255,255,.06);padding:20px 0}
.sb-user{padding:0 16px 16px;border-bottom:1px solid rgba(255,255,255,.05);margin-bottom:12px}
.sb-user-name{font-size:12px;font-weight:600;color:#fff}
.sb-user-role{font-size:10px;color:var(--y);letter-spacing:.5px;text-transform:uppercase}
.sb-item{display:flex;align-items:center;gap:8px;padding:9px 16px;cursor:pointer;font-size:12px;color:var(--m);border-left:2px solid transparent;transition:all .15s}
.sb-item:hover{background:rgba(255,255,255,.03);color:#fff}
.sb-item.on{background:rgba(255,193,7,.07);color:var(--y);border-left-color:var(--y)}
.sb-icon{width:16px;text-align:center}
.acontent{padding:28px;overflow-x:hidden}

/* login */
.login-wrap{display:flex;align-items:center;justify-content:center;min-height:calc(100vh - 60px)}
.login-card{background:rgba(255,255,255,.03);border:1px solid rgba(255,255,255,.09);border-radius:16px;padding:36px;width:360px}
.login-title{font-family:'Montserrat',sans-serif;font-size:20px;font-weight:800;margin-bottom:4px}
.login-sub{font-size:12px;color:var(--m);margin-bottom:24px}
.fl{display:flex;flex-direction:column;gap:14px}
.fg label{font-size:11px;color:var(--m);font-weight:600;letter-spacing:.3px;display:block;margin-bottom:5px}
.fg input{width:100%;padding:11px 14px;background:rgba(255,255,255,.05);border:1px solid rgba(255,255,255,.1);border-radius:8px;color:#fff;font-size:13px;font-family:'Poppins',sans-serif;outline:none;transition:border-color .2s}
.fg input:focus{border-color:var(--y)}
.err{background:rgba(239,68,68,.1);border:1px solid rgba(239,68,68,.25);border-radius:8px;padding:9px 13px;font-size:12px;color:#FCA5A5;display:none}
.login-hint{font-size:10px;color:rgba(166,166,166,.4);text-align:center;margin-top:12px}

/* Stats */
.stats-row{display:grid;grid-template-columns:repeat(4,1fr);gap:14px;margin-bottom:24px}
.scard{background:rgba(255,255,255,.03);border:1px solid rgba(255,255,255,.07);border-radius:12px;padding:18px}
.scard-n{font-family:'Montserrat',sans-serif;font-size:28px;font-weight:900}
.scard-l{font-size:11px;color:var(--m);margin-top:3px}

/* Tables */
.tbl-wrap{background:rgba(255,255,255,.02);border:1px solid rgba(255,255,255,.07);border-radius:12px;overflow:hidden}
table{width:100%;border-collapse:collapse}
th{padding:11px 14px;text-align:left;font-size:10px;text-transform:uppercase;letter-spacing:1.5px;color:var(--m);border-bottom:1px solid rgba(255,255,255,.06);background:rgba(255,255,255,.02);font-weight:600}
td{padding:12px 14px;font-size:12px;border-bottom:1px solid rgba(255,255,255,.03)}
tr:last-child td{border-bottom:none}
tr:hover td{background:rgba(255,255,255,.015)}
.pill{display:inline-flex;align-items:center;gap:4px;padding:2px 9px;border-radius:100px;font-size:10px;font-weight:700}
.p-act{background:rgba(34,197,94,.12);color:#4ADE80;border:1px solid rgba(34,197,94,.2)}
.p-sus{background:rgba(249,115,22,.12);color:#FB923C;border:1px solid rgba(249,115,22,.2)}
.p-ina{background:rgba(239,68,68,.12);color:#FCA5A5;border:1px solid rgba(239,68,68,.2)}
.p-vac{background:rgba(59,130,246,.12);color:#93C5FD;border:1px solid rgba(59,130,246,.2)}

/* btns */
.btn-y{padding:9px 18px;background:var(--y);color:#0D0D0D;border:none;border-radius:7px;font-family:'Montserrat',sans-serif;font-weight:800;font-size:12px;cursor:pointer;transition:all .2s;letter-spacing:.3px}
.btn-y:hover{background:#FFD54F}
.btn-g{padding:9px 18px;background:rgba(255,255,255,.06);color:#fff;border:1px solid rgba(255,255,255,.1);border-radius:7px;font-family:'Poppins',sans-serif;font-size:12px;cursor:pointer;transition:all .2s}
.btn-g:hover{background:rgba(255,255,255,.1)}
.btn-xs{padding:5px 10px;border-radius:5px;font-size:11px;cursor:pointer;font-family:'Poppins',sans-serif;transition:all .15s}
.btn-edit{background:rgba(255,193,7,.1);color:var(--y);border:1px solid rgba(255,193,7,.2)}
.btn-edit:hover{background:rgba(255,193,7,.2)}
.btn-del{background:rgba(239,68,68,.1);color:#FCA5A5;border:1px solid rgba(239,68,68,.2)}
.btn-del:hover{background:rgba(239,68,68,.2)}
.btn-tog{background:rgba(59,130,246,.1);color:#93C5FD;border:1px solid rgba(59,130,246,.2)}
.btn-tog:hover{background:rgba(59,130,246,.2)}

.ah{display:flex;align-items:center;justify-content:space-between;margin-bottom:22px}
.at{font-family:'Montserrat',sans-serif;font-size:20px;font-weight:800}
.sb2{display:flex;gap:10px;margin-bottom:16px}
.sinput{flex:1;padding:9px 14px;background:rgba(255,255,255,.05);border:1px solid rgba(255,255,255,.09);border-radius:7px;color:#fff;font-size:12px;font-family:'Poppins',sans-serif;outline:none}
.sinput:focus{border-color:var(--y)}

/* Modal */
.overlay{position:fixed;inset:0;background:rgba(0,0,0,.88);z-index:500;display:none;align-items:center;justify-content:center;backdrop-filter:blur(4px)}
.overlay.on{display:flex}
.modal{background:#171717;border:1px solid rgba(255,255,255,.1);border-radius:16px;padding:28px;width:90%;max-width:540px;max-height:85vh;overflow-y:auto;position:relative}
.modal-title{font-family:'Montserrat',sans-serif;font-size:17px;font-weight:800;margin-bottom:3px}
.modal-sub{font-size:12px;color:var(--m);margin-bottom:20px}
.mc{position:absolute;top:14px;right:14px;width:28px;height:28px;background:rgba(255,255,255,.06);border:none;color:#fff;cursor:pointer;border-radius:50%;font-size:16px;display:flex;align-items:center;justify-content:center}
.fgrid{display:grid;grid-template-columns:1fr 1fr;gap:12px}
.fgrid .full{grid-column:1/-1}
.fg2 label{font-size:11px;color:var(--m);font-weight:600;display:block;margin-bottom:4px;letter-spacing:.2px}
.fg2 input,.fg2 select{width:100%;padding:10px 12px;background:rgba(255,255,255,.05);border:1px solid rgba(255,255,255,.1);border-radius:7px;color:#fff;font-size:13px;font-family:'Poppins',sans-serif;outline:none}
.fg2 input:focus,.fg2 select:focus{border-color:var(--y)}
.fg2 select option{background:#1a1a1a}
.cert-grid{display:grid;grid-template-columns:1fr 1fr;gap:7px;margin-top:6px}
.ck{display:flex;align-items:center;gap:7px;font-size:12px;color:var(--m);cursor:pointer}
.ck input{accent-color:var(--y)}
.ck:hover{color:#fff}
.mfooter{display:flex;gap:10px;justify-content:flex-end;margin-top:20px}

/* Log */
.logwrap{background:rgba(255,255,255,.02);border:1px solid rgba(255,255,255,.06);border-radius:12px;max-height:380px;overflow-y:auto}
.log-item{display:flex;align-items:center;gap:12px;padding:12px 16px;border-bottom:1px solid rgba(255,255,255,.03)}
.log-item:last-child{border-bottom:none}
.ldot{width:7px;height:7px;border-radius:50%;flex-shrink:0}
.ldot.ok{background:var(--g)}.ldot.warn{background:var(--o)}.ldot.info{background:var(--b)}
.linfo{flex:1}.lname{font-size:12px;font-weight:500}.ldet{font-size:10px;color:var(--m);margin-top:1px}
.ltime{font-size:10px;color:rgba(166,166,166,.4);font-family:monospace}

/* toast */
.toast{position:fixed;bottom:20px;right:20px;background:#1c1c1c;border:1px solid rgba(255,193,7,.3);border-radius:10px;padding:12px 18px;font-size:13px;z-index:999;pointer-events:none;opacity:0;transform:translateY(8px);transition:all .3s}
.toast.show{opacity:1;transform:translateY(0)}

.atab{display:none}.atab.on{display:block}

/* Responsive tweaks */
@media(max-width:700px){
  .prof-grid{grid-template-columns:1fr}
  .prof-section{border-right:none;border-bottom:1px solid rgba(255,255,255,.05)}
  .stats-row{grid-template-columns:1fr 1fr}
  .fgrid{grid-template-columns:1fr}
  .fgrid .full{grid-column:1}
}
</style>

<div class="bg-layer">
  <div class="bg-grid"></div>
  <div class="bg-glow"></div>
  <div class="bg-ring"></div>
  <div class="bg-ring"></div>
</div>

<nav>
  <div class="nav-logo">
    <img src="/mnt/user-data/uploads/mozu_safe_w.png" alt="MozuSafe" onerror="this.style.display='none';document.getElementById('logo-fb').style.display='block'">
    <span id="logo-fb" class="nav-logo-fallback" style="display:none">MOZU<span style="color:#fff">SAFE</span></span>
  </div>
  <div class="nav-right">
    <div class="live-badge"><div class="live-dot"></div>Sistema activo</div>
    <div class="nav-tabs">
      <button class="ntab on" onclick="goPage('verify',this)">🔍 Verificar</button>
      <button class="ntab off" onclick="goPage('admin',this)">⚙️ Admin</button>
    </div>
  </div>
</nav>

<main>
<!-- ══ VERIFY ══ -->
<div id="page-verify" class="page on">
  <div class="verify-wrap">
    <div class="hero">
      <div class="hero-eyebrow">🛡 Verificación Oficial de Personal</div>
      <h1>Confirme la identidad del<br>personal <em>MozuSafe</em></h1>
      <p>Busque al colaborador por nombre, número de cédula o ID de gafete. El resultado muestra su estado de autorización en tiempo real.</p>
    </div>

    <div class="search-box">
      <h3>🔎 Buscar colaborador</h3>
      <div class="sug-wrap">
        <div class="search-row">
          <input class="search-input" id="search-inp" placeholder="Nombre, cédula o ID (ej: MSF-001 / 2-0377-0700 / Gabriel)" autocomplete="off" oninput="onSearchInput()" onkeydown="if(event.key==='Enter')doSearch()">
          <button class="search-btn" onclick="doSearch()">VERIFICAR →</button>
        </div>
        <div class="suggestions" id="suggestions"></div>
      </div>
      <div class="search-hint">Puede escanear el QR del gafete — este será el destino de esa verificación.</div>
    </div>

    <div class="result-empty" id="result-empty">
      <h3>🔴 Colaborador no encontrado</h3>
      <p>No existe ningún registro activo con ese dato en el sistema MozuSafe.<br>Si tiene dudas, comuníquese al Centro de Operaciones: <strong style="color:var(--y)">+506 6185-9550</strong></p>
    </div>

    <div class="profile" id="profile">
      <div class="status-bar" id="prof-status-bar">
        <div class="status-left">
          <div class="status-icon-big" id="prof-icon">✅</div>
          <div>
            <div class="status-title" id="prof-stitle">VERIFICADO</div>
            <div class="status-desc" id="prof-sdesc">Este colaborador pertenece oficialmente a MozuSafe y está autorizado para desempeñar sus funciones.</div>
          </div>
        </div>
        <div class="status-meta">
          <div><strong id="prof-empresa">MozuSafe</strong></div>
          <div>3-102-961429 S.R.L.</div>
          <div id="prof-ts">—</div>
        </div>
      </div>

      <div class="prof-header">
        <div class="avatar" id="prof-av">?</div>
        <div>
          <div class="prof-name" id="prof-name">—</div>
          <div class="prof-ced" id="prof-ced">—</div>
          <div class="prof-badge" id="prof-puesto">—</div>
        </div>
      </div>

      <div class="prof-grid">
        <div class="prof-section">
          <div class="sec-label">Información laboral</div>
          <div class="info-row"><div class="info-k">ID de Gafete</div><div class="info-v" id="prof-id" style="font-family:monospace;color:var(--y)">—</div></div>
          <div class="info-row"><div class="info-k">Proyecto asignado</div><div class="info-v" id="prof-proy">—</div></div>
          <div class="info-row"><div class="info-k">Fecha de ingreso</div><div class="info-v" id="prof-ing">—</div></div>
          <div class="info-row"><div class="info-k">Horario autorizado</div><div class="info-v" id="prof-hor">—</div></div>
          <div class="info-row"><div class="info-k">CCSS / INS</div><div class="info-v" id="prof-ccss">—</div></div>
        </div>
        <div class="prof-section">
          <div class="sec-label">Certificaciones</div>
          <div class="cert-list" id="prof-certs"></div>
        </div>
        <div class="prof-section">
          <div class="sec-label">Contacto de verificación</div>
          <div class="info-row"><div class="info-k">Centro de Operaciones</div><div class="info-v" style="color:var(--y)">MozuSafe 24/7</div></div>
          <div class="info-row"><div class="info-k">Teléfono</div><div class="info-v">+506 6185-9550</div></div>
          <div class="info-row"><div class="info-k">Correo</div><div class="info-v" style="font-size:11px">mozusafe@gmail.com</div></div>
          <div class="info-row"><div class="info-k">Peñas Blancas, San Ramón</div><div class="info-v" style="font-size:11px">Alajuela, Costa Rica</div></div>
        </div>
      </div>

      <div class="prof-footer">
        <div class="footer-co">Empresa contratante: <strong>MozuSafe</strong></div>
        <div class="footer-ts" id="prof-footer-ts">—</div>
      </div>
    </div>
  </div>
</div>

<!-- ══ ADMIN ══ -->
<div id="page-admin" class="page">
  <div id="admin-login" class="login-wrap">
    <div class="login-card">
      <div style="font-size:28px;margin-bottom:12px">🔐</div>
      <div class="login-title">Panel Administrativo</div>
      <div class="login-sub">MozuSafe — Acceso restringido</div>
      <div class="fl">
        <div class="err" id="login-err">Credenciales incorrectas.</div>
        <div class="fg"><label>Usuario</label><input id="lu" placeholder="admin@mozusafe.com"></div>
        <div class="fg"><label>Contraseña</label><input id="lp" type="password" placeholder="••••••••" onkeydown="if(event.key==='Enter')doLogin()"></div>
        <button class="btn-y" style="width:100%;padding:12px" onclick="doLogin()">INGRESAR</button>
      </div>
      <div class="login-hint">Demo: admin / mozusafe2025</div>
    </div>
  </div>

  <div id="admin-dash" style="display:none">
    <div class="admin-wrap">
      <div class="sidebar">
        <div class="sb-user">
          <div class="sb-user-name" id="sb-uname">admin</div>
          <div class="sb-user-role">Administrador</div>
        </div>
        <div class="sb-item on" onclick="goTab('t-resumen',this)"><span class="sb-icon">📊</span> Resumen</div>
        <div class="sb-item" onclick="goTab('t-personal',this)"><span class="sb-icon">👥</span> Personal</div>
        <div class="sb-item" onclick="goTab('t-clientes',this)"><span class="sb-icon">🏢</span> Clientes</div>
        <div class="sb-item" onclick="goTab('t-logs',this)"><span class="sb-icon">📋</span> Registro</div>
        <div class="sb-item" style="margin-top:auto;color:#FCA5A5" onclick="doLogout()"><span class="sb-icon">🚪</span> Salir</div>
      </div>

      <div class="acontent">
        <!-- RESUMEN -->
        <div id="t-resumen" class="atab on">
          <div class="ah"><div class="at">📊 Resumen del sistema</div><div style="font-size:11px;color:var(--m)" id="dash-date"></div></div>
          <div class="stats-row">
            <div class="scard"><div class="scard-n" id="st-total">0</div><div class="scard-l">Total colaboradores</div></div>
            <div class="scard"><div class="scard-n" style="color:var(--g)" id="st-act">0</div><div class="scard-l">Activos</div></div>
            <div class="scard"><div class="scard-n" style="color:var(--b)" id="st-vac">0</div><div class="scard-l">En vacaciones</div></div>
            <div class="scard"><div class="scard-n" style="color:var(--m)" id="st-oth">0</div><div class="scard-l">Suspendidos / Inactivos</div></div>
          </div>
          <div class="tbl-wrap">
            <table><thead><tr><th>Nombre</th><th>Puesto</th><th>Proyecto</th><th>Estado</th></tr></thead>
            <tbody id="res-tbody"></tbody></table>
          </div>
        </div>

        <!-- PERSONAL -->
        <div id="t-personal" class="atab">
          <div class="ah"><div class="at">👥 Gestión de personal</div><button class="btn-y" onclick="openModal()">+ Nuevo</button></div>
          <div class="sb2"><input class="sinput" id="search-adm" placeholder="Buscar nombre, cédula, proyecto..." oninput="filterAdm()"></div>
          <div class="tbl-wrap">
            <table><thead><tr><th>ID</th><th>Nombre</th><th>Cédula</th><th>Puesto</th><th>Proyecto</th><th>Estado</th><th>Acciones</th></tr></thead>
            <tbody id="adm-tbody"></tbody></table>
          </div>
        </div>

        <!-- CLIENTES -->
        <div id="t-clientes" class="atab">
          <div class="ah"><div class="at">🏢 Clientes y proyectos</div></div>
          <div class="tbl-wrap">
            <table><thead><tr><th>Cliente</th><th>Proyecto</th><th>Servicio</th><th>Personal asignado</th><th>Estado</th></tr></thead>
            <tbody id="cli-tbody"></tbody></table>
          </div>
        </div>

        <!-- LOGS -->
        <div id="t-logs" class="atab">
          <div class="ah"><div class="at">📋 Registro de consultas</div></div>
          <div class="logwrap" id="log-wrap"></div>
        </div>
      </div>
    </div>
  </div>
</div>
</main>

<!-- MODAL NUEVO/EDITAR -->
<div class="overlay" id="modal">
  <div class="modal">
    <button class="mc" onclick="closeModal()">✕</button>
    <div class="modal-title" id="modal-title">Nuevo colaborador</div>
    <div class="modal-sub">Complete los datos del colaborador</div>
    <div class="fgrid">
      <div class="fg2"><label>Nombre completo *</label><input id="m-nombre" placeholder="NOMBRE COMPLETO"></div>
      <div class="fg2"><label>Cédula *</label><input id="m-cedula" placeholder="0-000-000000"></div>
      <div class="fg2"><label>Puesto</label>
        <select id="m-puesto">
          <option>Oficial de Seguridad</option><option>Supervisor</option>
          <option>Coordinador</option><option>Monitorista</option>
          <option>Jefe de Operaciones</option><option>Administrativo</option>
        </select>
      </div>
      <div class="fg2"><label>Estado</label>
        <select id="m-estado">
          <option>Activo</option><option>Suspendido</option>
          <option>Inactivo</option><option>En vacaciones</option>
        </select>
      </div>
      <div class="fg2"><label>Proyecto</label><input id="m-proy" placeholder="Nombre del proyecto"></div>
      <div class="fg2"><label>Horario</label><input id="m-hor" placeholder="Ej: ROTATIVO / 06:00–18:00"></div>
      <div class="fg2"><label>Fecha de ingreso</label><input id="m-ing" type="date"></div>
      <div class="fg2"><label>CCSS</label><select id="m-ccss"><option>SI</option><option>NO</option></select></div>
      <div class="fg2"><label>INS</label><select id="m-ins"><option>SI</option><option>NO</option></select></div>
      <div class="fg2"><label>Observaciones</label><input id="m-obs" placeholder="Ej: 04-OFICIAL DE SEGURIDAD"></div>
      <div class="full">
        <div class="fg2"><label>Certificaciones</label>
          <div class="cert-grid">
            <label class="ck"><input type="checkbox" id="ck-armas"> Portación de armas</label>
            <label class="ck"><input type="checkbox" id="ck-supervisor"> Supervisor de seguridad Privada</label>
            <label class="ck"><input type="checkbox" id="ck-basico"> Seguridad privada básico</label>
            <label class="ck"><input type="checkbox" id="ck-primeros"> Primeros auxilios</label>
            <label class="ck"><input type="checkbox" id="ck-brigadas"> Brigadas de emergencia</label>
            <label class="ck"><input type="checkbox" id="ck-cctv"> Manejo de CCTV</label>
            <label class="ck"><input type="checkbox" id="ck-accesos"> Control de accesos</label>
          </div>
        </div>
      </div>
    </div>
    <div class="mfooter">
      <button class="btn-g" onclick="closeModal()">Cancelar</button>
      <button class="btn-y" onclick="saveStaff()">💾 Guardar</button>
    </div>
  </div>
</div>

<div class="toast" id="toast"></div>

<script>
const STAFF = [
  {id:'MSF-001',nombre:'CRISTOPHER MORALES ZU\u00d1IGA',cedula:'0-207350592',puesto:'Administrativo',estado:'Activo',proyecto:'GENERAL',ingreso:'2023-01-15',horario:'08:00 \u2013 16:00',ccss:'SI',ins:'SI',obs:'01-ADMINISTRADOR',certs:{armas:true,basico:true,primeros:false,brigadas:false,cctv:true,accesos:true}},
  {id:'MSF-002',nombre:'MARCOS HUMBERTO MORALES GARBANZO',cedula:'0-602190233',puesto:'Supervisor',estado:'Activo',proyecto:'GENERAL',ingreso:'2023-02-01',horario:'05:00 \u2013 13:00',ccss:'SI',ins:'SI',obs:'02-SUPERVISOR',certs:{armas:false,supervisor:true,basico:true,primeros:false,brigadas:false,cctv:false,accesos:true}},
  {id:'MSF-003',nombre:'ALONSO EDUARDO MURILLO ARCE',cedula:'2-0679-0347',puesto:'Coordinador',estado:'Activo',proyecto:'A. AVIN',ingreso:'2024-03-10',horario:'ROTATIVO',ccss:'SI',ins:'SI',obs:'03-COORDINADOR',certs:{armas:false,supervisor:true,primeros:false,brigadas:false,cctv:false,accesos:true}},
  {id:'MSF-004',nombre:'GABRIEL VASQUEZ ROJAS',cedula:'2-0377-0700',puesto:'Oficial de Seguridad',estado:'Activo',proyecto:'A. AVIN',ingreso:'2024-04-01',horario:'ROTATIVO',ccss:'SI',ins:'SI',obs:'04-OFICIAL DE SEGURIDAD',certs:{armas:true,supervisor:false,basico:true,primeros:false,brigadas:false,cctv:false,accesos:true}},
  {id:'MSF-005',nombre:'TATINLLETH ALEJANDRO VARELA ALP\u00cdZAR',cedula:'2-0696-0375',puesto:'Oficial de Seguridad',estado:'Activo',proyecto:'A. AVIN',ingreso:'2025-11-01',horario:'ROTATIVO',ccss:'SI',ins:'SI',obs:'04-OFICIAL DE SEGURIDAD',certs:{armas:true,basico:true,primeros:false,brigadas:false,cctv:true,accesos:true}},
  {id:'MSF-006',nombre:'DONALD GERARDO MADRIGAL ROJAS',cedula:'2-0512-0678',puesto:'Oficial de Seguridad',estado:'Activo',proyecto:'P. PAKO',ingreso:'2024-06-15',horario:'ROTATIVO',ccss:'SI',ins:'SI',obs:'04-OFICIAL DE SEGURIDAD',certs:{armas:true,supervisor:false,basico:true,primeros:false,brigadas:false,cctv:false,accesos:true}},
  {id:'MSF-007',nombre:'GERSON ENRIQUE ARCE CASTRO',cedula:'2-0837-0633',puesto:'Oficial de Seguridad',estado:'Activo',proyecto:'P. PAKO',ingreso:'2024-07-01',horario:'ROTATIVO',ccss:'SI',ins:'SI',obs:'04-OFICIAL DE SEGURIDAD',certs:{armas:true,supervisor:false,basico:true,primeros:false,brigadas:false,cctv:false,accesos:true}},
  {id:'MSF-008',nombre:'GREIVIN ARCE Z\u00da\u00d1IGA',cedula:'2-0604-0509',puesto:'Oficial de Seguridad',estado:'Activo',proyecto:'P. PAKO',ingreso:'2024-08-10',horario:'ROTATIVO',ccss:'SI',ins:'SI',obs:'04-OFICIAL DE SEGURIDAD',certs:{armas:true,supervisor:false,basico:true,primeros:false,brigadas:false,cctv:false,accesos:true}},
  {id:'MSF-009',nombre:'LORENZO SALOM\u00d3N GONZ\u00c1LEZ ZELAYA',cedula:'2-0380-0408',puesto:'Coordinador',estado:'Activo',proyecto:'P. PAKO',ingreso:'2024-09-01',horario:'ROTATIVO',ccss:'SI',ins:'SI',obs:'05-COORDINADOR',certs:{armas:true,basico:true,supervisor:false,primeros:false,brigadas:false,cctv:false,accesos:true}},
  {id:'MSF-010',nombre:'MELENDEZ CASTRO RICHARD ALBERTO',cedula:'4-0207-0375',puesto:'Oficial de Seguridad',estado:'Inactivo',proyecto:'GENERAL',ingreso:'2024-10-01',horario:'06:00 \u2013 18:00',ccss:'SI',ins:'SI',obs:'06-BACK UP',certs:{armas:false,supervisor:false,basico:true,primeros:false,brigadas:false,cctv:true,accesos:true}},
];

let staffList = JSON.parse(JSON.stringify(STAFF));

const CLIENTES = [
  {nombre:'M\u00edstico Park',proyecto:'A. AVIN',servicio:'Seguridad F\u00edsica',ubicacion:'San Ram\u00f3n, Alajuela',estado:'Activo'},
  {nombre:'P. PAKO',proyecto:'P. PAKO',servicio:'Seguridad F\u00edsica',ubicacion:'Alajuela',estado:'Activo'},
  {nombre:'Administraci\u00f3n Interna',proyecto:'GENERAL',servicio:'Administraci\u00f3n',ubicacion:'Pe\u00f1as Blancas',estado:'Activo'},
];

let scanLog = [];
let editId = null;

const CERT_LABELS = {
  armas:'Portaci\u00f3n de armas',
  supervisor:'Supervisor de seguridad privada',
  basico:'Seguridad privada b\u00e1sico',
  primeros:'Primeros auxilios',
  brigadas:'Brigadas de emergencia',
  cctv:'Manejo de CCTV',
  accesos:'Control de accesos',
};

function initials(n){const p=n.trim().split(' ');return(p[0][0]+(p[1]?p[1][0]:'')).toUpperCase()}
function pillClass(e){return{Activo:'p-act',Suspendido:'p-sus',Inactivo:'p-ina','En vacaciones':'p-vac'}[e]||'p-ina'}
function now(){return new Date().toLocaleString('es-CR',{day:'2-digit',month:'2-digit',year:'numeric',hour:'2-digit',minute:'2-digit'})}

// ── PAGE ROUTING ──
function goPage(pg, btn){
  document.querySelectorAll('.page').forEach(p=>p.classList.remove('on'));
  document.getElementById('page-'+pg).classList.add('on');
  document.querySelectorAll('.ntab').forEach(b=>b.classList.replace('on','off'));
  btn.classList.replace('off','on');
}

// ── SEARCH / VERIFY ──
function onSearchInput(){
  const q = document.getElementById('search-inp').value.trim().toLowerCase();
  const sug = document.getElementById('suggestions');
  if(q.length < 2){sug.style.display='none';return;}
  const matches = staffList.filter(s=>
    s.nombre.toLowerCase().includes(q)||
    s.cedula.toLowerCase().includes(q)||
    s.id.toLowerCase().includes(q)
  ).slice(0,6);
  if(!matches.length){sug.style.display='none';return;}
  sug.innerHTML = matches.map(s=>`
    <div class="sug-item" onclick="selectStaff('${s.id}')">
      <span class="sug-id">${s.id}</span>${s.nombre}
      <span style="font-size:10px;color:var(--m);margin-left:8px">${s.cedula}</span>
    </div>`).join('');
  sug.style.display='block';
}

function selectStaff(id){
  const s = staffList.find(x=>x.id===id);
  if(!s)return;
  document.getElementById('search-inp').value = s.nombre;
  document.getElementById('suggestions').style.display='none';
  renderProfile(s);
}

function doSearch(){
  document.getElementById('suggestions').style.display='none';
  const q = document.getElementById('search-inp').value.trim().toLowerCase();
  if(!q){toast('⚠️ Ingrese un nombre, cédula o ID');return;}
  const s = staffList.find(x=>
    x.nombre.toLowerCase().includes(q)||
    x.cedula.toLowerCase().replace(/-/g,'').includes(q.replace(/-/g,''))||
    x.id.toLowerCase()===q
  );
  document.getElementById('result-empty').style.display = 'none';
  document.getElementById('profile').style.display = 'none';
  if(!s){
    document.getElementById('result-empty').style.display='block';
    addLog(q,'No encontrado — consulta sin resultado','warn');
  } else {
    renderProfile(s);
  }
}

function renderProfile(s){
  document.getElementById('result-empty').style.display='none';
  const prof = document.getElementById('profile');
  prof.style.display='block';

  // Status bar
  const bar = document.getElementById('prof-status-bar');
  bar.className='status-bar';
  const stMap = {
    'Activo':{cls:'active',icon:'✅',title:'PERSONAL VERIFICADO',desc:'Este colaborador pertenece oficialmente a MozuSafe y se encuentra autorizado para desempe\u00f1ar sus funciones.'},
    'Suspendido':{cls:'suspended',icon:'⚠️',title:'PERSONAL SUSPENDIDO',desc:'Este colaborador se encuentra temporalmente inhabilitado. Verifique con el Centro de Operaciones.'},
    'Inactivo':{cls:'inactive',icon:'🔴',title:'NO AUTORIZADO',desc:'Este colaborador no se encuentra activo. No est\u00e1 autorizado para representar a MozuSafe.'},
    'En vacaciones':{cls:'vacation',icon:'🔵',title:'EN VACACIONES',desc:'El colaborador se encuentra en per\u00edodo de vacaciones. Consulte con el Centro de Operaciones.'},
  };
  const st = stMap[s.estado]||stMap['Inactivo'];
  bar.classList.add(st.cls);
  document.getElementById('prof-icon').textContent=st.icon;
  document.getElementById('prof-stitle').textContent=st.title;
  document.getElementById('prof-sdesc').textContent=st.desc;

  const ts = now();
  document.getElementById('prof-ts').textContent='Consultado: '+ts;
  document.getElementById('prof-footer-ts').textContent='Verificaci\u00f3n: '+ts;

  // Header
  document.getElementById('prof-av').textContent=initials(s.nombre);
  document.getElementById('prof-name').textContent=s.nombre;
  document.getElementById('prof-ced').textContent='C\u00e9dula: '+s.cedula;
  document.getElementById('prof-puesto').textContent=s.puesto;

  // Fields
  document.getElementById('prof-id').textContent=s.id;
  document.getElementById('prof-proy').textContent=s.proyecto||'—';
  document.getElementById('prof-ing').textContent=s.ingreso||'—';
  document.getElementById('prof-hor').textContent=s.horario||'—';
  document.getElementById('prof-ccss').textContent='CCSS: '+s.ccss+' | INS: '+s.ins;

  // Certs
  const certEl = document.getElementById('prof-certs');
  certEl.innerHTML = Object.entries(CERT_LABELS).map(([k,label])=>{
    const ok = s.certs&&s.certs[k];
    return `<div class="cert-item">
      <div class="cert-tick ${ok?'cert-ok':'cert-no'}">${ok?'✓':'✗'}</div>
      <span class="${ok?'cert-label-ok':'cert-label-no'}">${label}</span>
    </div>`;
  }).join('');

  prof.scrollIntoView({behavior:'smooth',block:'nearest'});
  addLog(s.nombre,'Verificaci\u00f3n: '+st.title+' | '+s.id,'ok');
}

// Close suggestions on outside click
document.addEventListener('click', e=>{
  if(!e.target.closest('.sug-wrap')) document.getElementById('suggestions').style.display='none';
});

// ── ADMIN ──
function doLogin(){
  const u=document.getElementById('lu').value;
  const p=document.getElementById('lp').value;
  if((u==='admin'||u==='admin@mozusafe.com')&&p==='mozusafe2025'){
    document.getElementById('admin-login').style.display='none';
    document.getElementById('admin-dash').style.display='block';
    document.getElementById('sb-uname').textContent=u;
    document.getElementById('dash-date').textContent=new Date().toLocaleDateString('es-CR',{weekday:'long',year:'numeric',month:'long',day:'numeric'});
    initDash();
    addLog('Login admin','Acceso al panel administrativo','info');
  } else {
    const e=document.getElementById('login-err');
    e.style.display='block';
    setTimeout(()=>e.style.display='none',3000);
  }
}
function doLogout(){
  document.getElementById('admin-login').style.display='flex';
  document.getElementById('admin-dash').style.display='none';
  document.getElementById('lu').value='';document.getElementById('lp').value='';
}

function initDash(){renderStats();renderResumen();renderAdm();renderClientes();renderLogs();}

function renderStats(){
  document.getElementById('st-total').textContent=staffList.length;
  document.getElementById('st-act').textContent=staffList.filter(s=>s.estado==='Activo').length;
  document.getElementById('st-vac').textContent=staffList.filter(s=>s.estado==='En vacaciones').length;
  document.getElementById('st-oth').textContent=staffList.filter(s=>s.estado==='Suspendido'||s.estado==='Inactivo').length;
}

function renderResumen(){
  document.getElementById('res-tbody').innerHTML=staffList.map(s=>`<tr>
    <td><strong>${s.nombre}</strong></td><td>${s.puesto}</td><td>${s.proyecto}</td>
    <td><span class="pill ${pillClass(s.estado)}">${s.estado}</span></td>
  </tr>`).join('');
}

function renderAdm(){
  document.getElementById('adm-tbody').innerHTML=staffList.map(s=>`<tr>
    <td style="font-family:monospace;color:var(--y);font-size:11px">${s.id}</td>
    <td><strong style="font-size:12px">${s.nombre}</strong></td>
    <td style="font-family:monospace;font-size:11px">${s.cedula}</td>
    <td>${s.puesto}</td><td>${s.proyecto}</td>
    <td><span class="pill ${pillClass(s.estado)}">${s.estado}</span></td>
    <td style="display:flex;gap:5px;flex-wrap:wrap">
      <button class="btn-xs btn-edit" onclick="editStaff('${s.id}')">✏️ Editar</button>
      <button class="btn-xs btn-tog" onclick="toggleStatus('${s.id}')">${s.estado==='Activo'?'⏸ Suspender':'▶ Activar'}</button>
    </td>
  </tr>`).join('');
}

function filterAdm(){
  const q=document.getElementById('search-adm').value.toLowerCase();
  document.querySelectorAll('#adm-tbody tr').forEach(r=>{
    r.style.display=r.textContent.toLowerCase().includes(q)?'':'none';
  });
}

function renderClientes(){
  document.getElementById('cli-tbody').innerHTML=CLIENTES.map(c=>`<tr>
    <td><strong>${c.nombre}</strong></td><td>${c.proyecto}</td><td>${c.servicio}</td>
    <td>${staffList.filter(s=>s.proyecto===c.proyecto).length} persona(s)</td>
    <td><span class="pill ${c.estado==='Activo'?'p-act':'p-ina'}">${c.estado}</span></td>
  </tr>`).join('');
}

function addLog(nombre,detalle,tipo){
  scanLog.unshift({nombre,detalle,tipo,ts:now()});
  if(scanLog.length>50)scanLog.pop();
  renderLogs();
}

function renderLogs(){
  const el=document.getElementById('log-wrap');
  if(!el)return;
  if(!scanLog.length){el.innerHTML='<div style="padding:24px;text-align:center;color:var(--m);font-size:12px">Sin registros a\u00fan</div>';return;}
  el.innerHTML=scanLog.map(l=>`<div class="log-item">
    <div class="ldot ${l.tipo}"></div>
    <div class="linfo"><div class="lname">${l.nombre}</div><div class="ldet">${l.detalle}</div></div>
    <div class="ltime">${l.ts}</div>
  </div>`).join('');
}

function goTab(tabId,el){
  document.querySelectorAll('.atab').forEach(t=>t.classList.remove('on'));
  document.querySelectorAll('.sb-item').forEach(s=>s.classList.remove('on'));
  document.getElementById(tabId).classList.add('on');
  el.classList.add('on');
}

// Modal
function openModal(){
  editId=null;
  document.getElementById('modal-title').textContent='Nuevo colaborador';
  ['m-nombre','m-cedula','m-proy','m-hor','m-obs'].forEach(id=>document.getElementById(id).value='');
  document.getElementById('m-puesto').value='Oficial de Seguridad';
  document.getElementById('m-estado').value='Activo';
  document.getElementById('m-ccss').value='SI';
  document.getElementById('m-ins').value='SI';
  document.getElementById('m-ing').value=new Date().toISOString().split('T')[0];
  Object.keys(CERT_LABELS).forEach(k=>document.getElementById('ck-'+k).checked=false);
  document.getElementById('modal').classList.add('on');
}

function editStaff(id){
  const s=staffList.find(x=>x.id===id);if(!s)return;
  editId=id;
  document.getElementById('modal-title').textContent='Editar colaborador';
  document.getElementById('m-nombre').value=s.nombre;
  document.getElementById('m-cedula').value=s.cedula;
  document.getElementById('m-puesto').value=s.puesto;
  document.getElementById('m-estado').value=s.estado;
  document.getElementById('m-proy').value=s.proyecto||'';
  document.getElementById('m-hor').value=s.horario||'';
  document.getElementById('m-ing').value=s.ingreso||'';
  document.getElementById('m-ccss').value=s.ccss||'SI';
  document.getElementById('m-ins').value=s.ins||'SI';
  document.getElementById('m-obs').value=s.obs||'';
  if(s.certs)Object.keys(CERT_LABELS).forEach(k=>document.getElementById('ck-'+k).checked=!!s.certs[k]);
  document.getElementById('modal').classList.add('on');
}

function saveStaff(){
  const nombre=document.getElementById('m-nombre').value.trim().toUpperCase();
  const cedula=document.getElementById('m-cedula').value.trim();
  if(!nombre||!cedula){toast('⚠️ Nombre y cédula son requeridos');return;}
  const certs={};
  Object.keys(CERT_LABELS).forEach(k=>certs[k]=document.getElementById('ck-'+k).checked);
  const data={nombre,cedula,puesto:document.getElementById('m-puesto').value,estado:document.getElementById('m-estado').value,proyecto:document.getElementById('m-proy').value,horario:document.getElementById('m-hor').value,ingreso:document.getElementById('m-ing').value,ccss:document.getElementById('m-ccss').value,ins:document.getElementById('m-ins').value,obs:document.getElementById('m-obs').value,certs};
  if(editId){
    const i=staffList.findIndex(x=>x.id===editId);
    staffList[i]={...staffList[i],...data};
    toast('✅ Colaborador actualizado');
    addLog(nombre,'Datos editados — '+editId,'info');
  } else {
    const newId='MSF-'+(staffList.length+1).toString().padStart(3,'0');
    staffList.push({id:newId,...data});
    toast('✅ Colaborador creado: '+newId);
    addLog(nombre,'Nuevo colaborador creado — '+newId,'ok');
  }
  closeModal();
  initDash();
}

function toggleStatus(id){
  const s=staffList.find(x=>x.id===id);if(!s)return;
  s.estado=s.estado==='Activo'?'Suspendido':'Activo';
  addLog(s.nombre,'Estado cambiado a: '+s.estado,'info');
  renderAdm();renderStats();renderResumen();
  toast('Estado actualizado: '+s.estado);
}

function closeModal(){document.getElementById('modal').classList.remove('on');}

function toast(msg){
  const t=document.getElementById('toast');
  t.textContent=msg;t.classList.add('show');
  setTimeout(()=>t.classList.remove('show'),3000);
}

// Init
renderLogs();
</script>
