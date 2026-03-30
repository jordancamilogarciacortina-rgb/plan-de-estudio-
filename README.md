# plan-de-estudio-
<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Plan ICFES 450+ — Jordan García</title>
<link href="https://fonts.googleapis.com/css2?family=Syne:wght@400;600;700;800&family=DM+Sans:ital,opsz,wght@0,9..40,300;0,9..40,400;0,9..40,500;1,9..40,300&display=swap" rel="stylesheet">
<style>
:root{
  --bg:#07090f;--surface:#0f1623;--s2:#161e2e;--s3:#1c2740;
  --border:#1e2d45;--accent:#00e5ff;--accent2:#ff6b35;--purple:#7c3aed;
  --green:#10b981;--yellow:#f59e0b;--red:#ef4444;
  --text:#e2e8f0;--muted:#64748b;--muted2:#94a3b8;
}
*{margin:0;padding:0;box-sizing:border-box;}
html{scroll-behavior:smooth;}
body{background:var(--bg);color:var(--text);font-family:'DM Sans',sans-serif;min-height:100vh;overflow-x:hidden;}

/* ── HERO ── */
.hero{
  background:linear-gradient(135deg,#07090f 0%,#0b1525 60%,#07090f 100%);
  border-bottom:1px solid var(--border);padding:2.5rem 1.5rem 2rem;text-align:center;position:relative;overflow:hidden;
}
.hero::before{content:'';position:absolute;top:-40%;left:50%;transform:translateX(-50%);width:700px;height:700px;
  background:radial-gradient(ellipse,rgba(0,229,255,.06) 0%,transparent 65%);pointer-events:none;}
.hero-tag{display:inline-block;background:rgba(0,229,255,.1);border:1px solid rgba(0,229,255,.3);
  color:var(--accent);font-family:'Syne',sans-serif;font-size:.65rem;letter-spacing:.15em;
  text-transform:uppercase;padding:.25rem .8rem;border-radius:20px;margin-bottom:.8rem;}
.hero h1{font-family:'Syne',sans-serif;font-size:clamp(1.8rem,5vw,3rem);font-weight:800;line-height:1.1;margin-bottom:.3rem;}
.hero h1 span{color:var(--accent);}
.hero-sub{color:var(--muted);font-size:.85rem;margin-bottom:1.2rem;}
.countdown-bar{display:flex;justify-content:center;gap:2rem;flex-wrap:wrap;margin-top:1rem;}
.cd-unit{text-align:center;}
.cd-num{font-family:'Syne',sans-serif;font-size:2.2rem;font-weight:800;color:var(--accent);display:block;line-height:1;}
.cd-label{font-size:.6rem;color:var(--muted);text-transform:uppercase;letter-spacing:.1em;}

/* ── SCORE DASHBOARD ── */
.score-dash{background:var(--surface);border-bottom:1px solid var(--border);padding:1.2rem 1.5rem;}
.score-dash-title{font-family:'Syne',sans-serif;font-size:.8rem;color:var(--muted);text-transform:uppercase;letter-spacing:.1em;margin-bottom:.8rem;display:flex;justify-content:space-between;align-items:center;}
.score-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(130px,1fr));gap:.7rem;}
.score-card{background:var(--s2);border:1px solid var(--border);border-radius:12px;padding:.8rem;cursor:pointer;transition:all .2s;position:relative;}
.score-card:hover{border-color:rgba(0,229,255,.4);transform:translateY(-1px);}
.score-card.lc{border-left:3px solid var(--red);}
.score-card.cn{border-left:3px solid var(--yellow);}
.score-card.mat{border-left:3px solid var(--green);}
.score-card.soc{border-left:3px solid var(--purple);}
.score-card.ing{border-left:3px solid var(--accent);}
.score-card.total{border-color:rgba(0,229,255,.4);background:rgba(0,229,255,.04);}
.sc-label{font-size:.6rem;color:var(--muted);text-transform:uppercase;letter-spacing:.07em;margin-bottom:.3rem;}
.sc-current{font-family:'Syne',sans-serif;font-size:1.6rem;font-weight:800;line-height:1;}
.sc-meta{font-size:.65rem;color:var(--muted);margin-top:.15rem;}
.sc-bar{height:4px;background:var(--border);border-radius:2px;margin-top:.5rem;overflow:hidden;}
.sc-bar-fill{height:100%;border-radius:2px;transition:width .8s ease;}
.edit-hint{font-size:.55rem;color:var(--muted);position:absolute;top:.5rem;right:.5rem;opacity:.5;}

/* ── MODAL ── */
.modal-overlay{display:none;position:fixed;inset:0;background:rgba(0,0,0,.7);z-index:100;align-items:center;justify-content:center;padding:1rem;}
.modal-overlay.open{display:flex;}
.modal{background:var(--s2);border:1px solid var(--border);border-radius:16px;padding:1.5rem;width:100%;max-width:400px;}
.modal h3{font-family:'Syne',sans-serif;font-size:1.1rem;margin-bottom:1rem;}
.modal-area-label{font-size:.8rem;color:var(--muted);margin-bottom:.4rem;}
.score-input{width:100%;background:var(--surface);border:1px solid var(--border);color:var(--text);font-family:'Syne',sans-serif;font-size:1.5rem;font-weight:700;text-align:center;padding:.7rem;border-radius:10px;outline:none;transition:border-color .2s;}
.score-input:focus{border-color:var(--accent);}
.modal-hint{font-size:.72rem;color:var(--muted);text-align:center;margin-top:.4rem;}
.modal-btns{display:flex;gap:.7rem;margin-top:1rem;}
.btn-save{flex:1;background:var(--accent);color:#000;border:none;font-family:'Syne',sans-serif;font-weight:700;font-size:.9rem;padding:.7rem;border-radius:8px;cursor:pointer;transition:all .2s;}
.btn-save:hover{opacity:.9;}
.btn-cancel{flex:1;background:none;border:1px solid var(--border);color:var(--muted);font-family:'Syne',sans-serif;font-size:.9rem;padding:.7rem;border-radius:8px;cursor:pointer;}
.sim-history{margin-top:1rem;border-top:1px solid var(--border);padding-top:.8rem;}
.sim-entry{display:flex;justify-content:space-between;align-items:center;padding:.4rem 0;border-bottom:1px solid var(--border);font-size:.78rem;}
.sim-entry:last-child{border-bottom:none;}
.sim-date{color:var(--muted);}
.sim-score{font-family:'Syne',sans-serif;font-weight:700;color:var(--accent);}
.sim-del{background:none;border:none;color:var(--red);cursor:pointer;font-size:.75rem;opacity:.6;}
.sim-del:hover{opacity:1;}

/* ── TABS ── */
.nav-tabs{display:flex;background:var(--surface);border-bottom:1px solid var(--border);overflow-x:auto;padding:0 1rem;gap:0;position:sticky;top:0;z-index:10;}
.tab-btn{background:none;border:none;color:var(--muted);font-family:'DM Sans',sans-serif;font-size:.82rem;padding:.9rem 1rem;cursor:pointer;border-bottom:2px solid transparent;white-space:nowrap;transition:all .2s;}
.tab-btn:hover{color:var(--text);}
.tab-btn.active{color:var(--accent);border-bottom-color:var(--accent);}

/* ── PANELS ── */
.panel{display:none;padding:1.5rem;max-width:920px;margin:0 auto;}
.panel.active{display:block;}
.sec-title{font-family:'Syne',sans-serif;font-size:1.3rem;font-weight:700;margin-bottom:.25rem;}
.sec-sub{color:var(--muted);font-size:.82rem;margin-bottom:1.2rem;}

/* ── CLASS BLOCKS ── */
.class-block{background:linear-gradient(135deg,rgba(124,58,237,.08),rgba(0,229,255,.04));border:1px solid rgba(124,58,237,.3);border-radius:14px;padding:1.2rem;margin-bottom:1.2rem;}
.class-header{display:flex;align-items:center;gap:.7rem;margin-bottom:.8rem;cursor:pointer;}
.class-icon{width:36px;height:36px;background:var(--purple);border-radius:8px;display:flex;align-items:center;justify-content:center;font-size:1rem;flex-shrink:0;}
.class-title{font-family:'Syne',sans-serif;font-size:.95rem;font-weight:700;}
.class-subtitle{font-size:.72rem;color:var(--muted);}
.class-toggle{margin-left:auto;color:var(--muted);font-size:.8rem;transition:transform .3s;}
.class-toggle.open{transform:rotate(180deg);}
.class-body{display:none;border-top:1px solid rgba(124,58,237,.2);margin-top:.8rem;padding-top:.8rem;}
.class-body.open{display:block;}
.class-body p{font-size:.85rem;line-height:1.75;color:var(--muted2);margin-bottom:.7rem;}
.class-body p strong{color:var(--text);}
.class-body .example{background:var(--s3);border-left:3px solid var(--accent);padding:.8rem;border-radius:0 8px 8px 0;font-size:.82rem;color:var(--muted2);margin:.6rem 0;line-height:1.7;}
.class-body .tip{background:rgba(16,185,129,.08);border:1px solid rgba(16,185,129,.25);border-radius:8px;padding:.7rem;font-size:.8rem;color:#6ee7b7;margin-top:.5rem;}
.class-body .warning{background:rgba(245,158,11,.08);border:1px solid rgba(245,158,11,.25);border-radius:8px;padding:.7rem;font-size:.8rem;color:#fcd34d;margin-top:.5rem;}
.competencia-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:.6rem;margin:.8rem 0;}
.comp-box{background:var(--s3);border-radius:8px;padding:.7rem;text-align:center;}
.comp-code{font-family:'Syne',sans-serif;font-size:1.2rem;font-weight:800;color:var(--accent);}
.comp-name{font-size:.7rem;color:var(--muted);margin-top:.2rem;}
.comp-desc{font-size:.72rem;color:var(--muted2);margin-top:.3rem;}

/* ── MONTH BLOCKS ── */
.month-block{margin-bottom:1.8rem;}
.month-header{display:flex;align-items:center;gap:.7rem;margin-bottom:.8rem;}
.month-badge{background:var(--purple);font-family:'Syne',sans-serif;font-size:.65rem;font-weight:700;letter-spacing:.1em;text-transform:uppercase;padding:.2rem .65rem;border-radius:6px;}
.month-name{font-family:'Syne',sans-serif;font-size:1rem;font-weight:700;}
.month-focus{color:var(--muted);font-size:.75rem;}
.week-grid{display:flex;flex-direction:column;gap:.65rem;}
.week-card{background:var(--surface);border:1px solid var(--border);border-radius:12px;padding:.9rem 1.1rem;transition:border-color .2s;}
.week-card:hover{border-color:rgba(0,229,255,.25);}
.week-card.p1{border-left:3px solid var(--red);}
.week-card.p2{border-left:3px solid var(--yellow);}
.week-card.p3{border-left:3px solid var(--green);}
.week-card.exam{border-color:rgba(0,229,255,.5);background:rgba(0,229,255,.03);}
.week-head{display:flex;justify-content:space-between;align-items:center;margin-bottom:.4rem;}
.wk-num{font-family:'Syne',sans-serif;font-size:.68rem;font-weight:700;color:var(--muted);text-transform:uppercase;letter-spacing:.1em;}
.wk-dates{font-size:.65rem;color:var(--muted);background:var(--s2);padding:.12rem .45rem;border-radius:4px;}
.wk-title{font-weight:600;font-size:.9rem;margin-bottom:.35rem;}
.wk-tasks{list-style:none;}
.wk-tasks li{font-size:.78rem;color:var(--muted);padding:.1rem 0 .1rem 1rem;position:relative;}
.wk-tasks li::before{content:'→';position:absolute;left:0;color:var(--accent);font-size:.65rem;top:.15rem;}
.area-tags{display:flex;gap:.35rem;flex-wrap:wrap;margin-top:.45rem;}
.area-tag{font-size:.6rem;padding:.12rem .45rem;border-radius:4px;font-weight:500;text-transform:uppercase;letter-spacing:.04em;}
.tag-lc{background:rgba(239,68,68,.15);color:#fca5a5;}
.tag-cn{background:rgba(245,158,11,.15);color:#fcd34d;}
.tag-mat{background:rgba(16,185,129,.15);color:#6ee7b7;}
.tag-soc{background:rgba(124,58,237,.15);color:#c4b5fd;}
.tag-ing{background:rgba(0,229,255,.15);color:#67e8f9;}

/* ── QUIZ ── */
.quiz-sel{display:grid;grid-template-columns:repeat(auto-fit,minmax(140px,1fr));gap:.7rem;margin-bottom:1.2rem;}
.qa-btn{background:var(--surface);border:1px solid var(--border);border-radius:12px;padding:.9rem;cursor:pointer;text-align:center;transition:all .2s;font-family:'DM Sans',sans-serif;}
.qa-btn:hover{border-color:var(--accent);background:var(--s2);}
.qa-btn.sel{border-color:var(--accent);background:rgba(0,229,255,.07);}
.qa-icon{font-size:1.4rem;margin-bottom:.3rem;}
.qa-name{font-size:.82rem;font-weight:600;}
.qa-count{font-size:.65rem;color:var(--muted);}
.start-btn{background:var(--accent);color:#000;border:none;font-family:'Syne',sans-serif;font-weight:700;font-size:.88rem;padding:.8rem 2rem;border-radius:10px;cursor:pointer;transition:all .2s;display:block;margin:0 auto 1.2rem;}
.start-btn:hover:not(:disabled){transform:translateY(-2px);box-shadow:0 8px 20px rgba(0,229,255,.3);}
.start-btn:disabled{opacity:.4;cursor:not-allowed;}
#quiz-container{display:none;}
.quiz-card{background:var(--surface);border:1px solid var(--border);border-radius:16px;padding:1.4rem;}
.qpbar{height:4px;background:var(--border);border-radius:2px;margin-bottom:1rem;overflow:hidden;}
.qpfill{height:100%;background:var(--accent);border-radius:2px;transition:width .4s ease;}
.qmeta{display:flex;justify-content:space-between;margin-bottom:.9rem;font-size:.72rem;color:var(--muted);}
.q-badge{font-size:.65rem;font-weight:600;padding:.18rem .55rem;border-radius:5px;text-transform:uppercase;}
.q-passage{background:var(--s2);border-left:3px solid var(--purple);padding:.9rem;border-radius:0 8px 8px 0;font-size:.82rem;line-height:1.75;color:#94a3b8;margin-bottom:1rem;font-style:italic;}
.q-question{font-size:.92rem;font-weight:500;line-height:1.55;margin-bottom:.9rem;}
.q-options{display:flex;flex-direction:column;gap:.55rem;}
.q-opt{background:var(--s2);border:1px solid var(--border);border-radius:10px;padding:.7rem .9rem;cursor:pointer;font-size:.85rem;transition:all .2s;text-align:left;font-family:'DM Sans',sans-serif;color:var(--text);display:flex;gap:.65rem;align-items:flex-start;}
.q-opt:hover:not(:disabled){border-color:var(--accent);background:rgba(0,229,255,.05);}
.q-opt.correct{border-color:var(--green);background:rgba(16,185,129,.1);color:#6ee7b7;}
.q-opt.incorrect{border-color:var(--red);background:rgba(239,68,68,.1);color:#fca5a5;}
.q-opt:disabled{cursor:default;}
.opt-letter{font-family:'Syne',sans-serif;font-weight:700;font-size:.72rem;min-width:18px;margin-top:.1rem;color:var(--muted);}
.q-opt.correct .opt-letter{color:var(--green);}
.q-opt.incorrect .opt-letter{color:var(--red);}
.q-feedback{margin-top:.9rem;padding:.8rem;border-radius:10px;font-size:.82rem;display:none;line-height:1.55;}
.q-feedback.correct{background:rgba(16,185,129,.08);border:1px solid rgba(16,185,129,.25);color:#6ee7b7;}
.q-feedback.incorrect{background:rgba(239,68,68,.08);border:1px solid rgba(239,68,68,.25);color:#fca5a5;}
.next-btn{background:var(--s2);border:1px solid var(--border);color:var(--text);font-family:'Syne',sans-serif;font-size:.82rem;font-weight:700;padding:.65rem 1.4rem;border-radius:8px;cursor:pointer;margin-top:.9rem;display:none;transition:all .2s;}
.next-btn:hover{border-color:var(--accent);color:var(--accent);}
.quiz-results{display:none;text-align:center;padding:2rem;}
.res-score{font-family:'Syne',sans-serif;font-size:4rem;font-weight:800;line-height:1;margin:1rem 0 .5rem;}
.res-label{color:var(--muted);font-size:.88rem;margin-bottom:1.5rem;}
.retry-btn{background:none;border:1px solid var(--accent);color:var(--accent);font-family:'Syne',sans-serif;font-size:.82rem;font-weight:700;padding:.65rem 1.4rem;border-radius:8px;cursor:pointer;transition:all .2s;}
.retry-btn:hover{background:rgba(0,229,255,.08);}

/* ── PROGRESS PANEL ── */
.prog-grid{display:flex;flex-direction:column;gap:.8rem;}
.prog-item{background:var(--surface);border:1px solid var(--border);border-radius:12px;padding:1rem 1.2rem;}
.prog-top{display:flex;justify-content:space-between;align-items:center;margin-bottom:.6rem;}
.prog-area{font-weight:600;font-size:.88rem;}
.prog-nums{font-size:.75rem;color:var(--muted);}
.prog-nums span{color:var(--accent);font-weight:700;}
.prog-wrap{height:10px;background:var(--border);border-radius:5px;overflow:hidden;}
.prog-fill{height:100%;border-radius:5px;transition:width 1s ease;}
.chart-section{margin-top:1.5rem;}
.chart-title{font-family:'Syne',sans-serif;font-size:.9rem;font-weight:700;margin-bottom:.8rem;}
.sim-list{display:flex;flex-direction:column;gap:.5rem;}
.sim-row{background:var(--surface);border:1px solid var(--border);border-radius:10px;padding:.7rem 1rem;display:flex;justify-content:space-between;align-items:center;}
.sim-row-date{font-size:.78rem;color:var(--muted);}
.sim-row-score{font-family:'Syne',sans-serif;font-weight:700;font-size:1rem;color:var(--accent);}
.sim-row-delta{font-size:.72rem;}
.add-sim-btn{background:none;border:1px dashed var(--border);color:var(--muted);font-family:'DM Sans',sans-serif;font-size:.82rem;padding:.65rem;border-radius:10px;cursor:pointer;width:100%;transition:all .2s;margin-top:.5rem;}
.add-sim-btn:hover{border-color:var(--accent);color:var(--accent);}

/* ── RESOURCES ── */
.res-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(240px,1fr));gap:.8rem;}
.res-card{background:var(--surface);border:1px solid var(--border);border-radius:12px;padding:1.1rem;transition:border-color .2s;}
.res-card:hover{border-color:rgba(0,229,255,.3);}
.res-icon{font-size:1.4rem;margin-bottom:.4rem;}
.res-title{font-weight:600;font-size:.88rem;margin-bottom:.25rem;}
.res-desc{font-size:.75rem;color:var(--muted);margin-bottom:.6rem;line-height:1.55;}
.res-link{color:var(--accent);font-size:.75rem;text-decoration:none;font-weight:500;}
.res-link:hover{text-decoration:underline;}

/* ── TOAST ── */
.toast{position:fixed;bottom:1.5rem;right:1.5rem;background:var(--green);color:#000;font-family:'Syne',sans-serif;font-weight:700;font-size:.82rem;padding:.7rem 1.2rem;border-radius:10px;opacity:0;transform:translateY(10px);transition:all .3s;z-index:200;pointer-events:none;}
.toast.show{opacity:1;transform:translateY(0);}

@media(max-width:600px){
  .score-grid{grid-template-columns:repeat(2,1fr);}
  .panel{padding:1rem;}
  .competencia-grid{grid-template-columns:1fr;}
}
</style>
</head>
<body>

<!-- HERO -->
<div class="hero">
  <div class="hero-tag">🎯 Plan ICFES Personalizado</div>
  <h1>Jordan García<br><span>Meta: 450+</span></h1>
  <p class="hero-sub">Colegio Colón · Barranquilla · Prueba oficial: 26 de julio de 2026</p>
  <div class="countdown-bar">
    <div class="cd-unit"><span class="cd-num" id="cd-d">-</span><span class="cd-label">Días</span></div>
    <div class="cd-unit"><span class="cd-num" id="cd-h">-</span><span class="cd-label">Horas</span></div>
    <div class="cd-unit"><span class="cd-num" id="cd-m">-</span><span class="cd-label">Minutos</span></div>
  </div>
</div>

<!-- SCORE DASHBOARD -->
<div class="score-dash">
  <div class="score-dash-title">
    <span>📊 Mis puntajes — toca una tarjeta para actualizar</span>
    <span style="font-size:.65rem;color:var(--green)" id="last-update-label"></span>
  </div>
  <div class="score-grid">
    <div class="score-card lc" onclick="openModal('lc')">
      <div class="edit-hint">✏️ editar</div>
      <div class="sc-label">Lectura Crítica</div>
      <div class="sc-current" id="sc-lc" style="color:var(--red)">68.3</div>
      <div class="sc-meta">Meta: 85+ · faltan <span id="gap-lc"></span></div>
      <div class="sc-bar"><div class="sc-bar-fill" id="bar-lc" style="background:var(--red)"></div></div>
    </div>
    <div class="score-card cn" onclick="openModal('cn')">
      <div class="edit-hint">✏️ editar</div>
      <div class="sc-label">Ciencias Naturales</div>
      <div class="sc-current" id="sc-cn" style="color:var(--yellow)">82.8</div>
      <div class="sc-meta">Meta: 93+ · faltan <span id="gap-cn"></span></div>
      <div class="sc-bar"><div class="sc-bar-fill" id="bar-cn" style="background:var(--yellow)"></div></div>
    </div>
    <div class="score-card mat" onclick="openModal('mat')">
      <div class="edit-hint">✏️ editar</div>
      <div class="sc-label">Matemáticas</div>
      <div class="sc-current" id="sc-mat" style="color:var(--green)">90.0</div>
      <div class="sc-meta">Meta: 95+ · faltan <span id="gap-mat"></span></div>
      <div class="sc-bar"><div class="sc-bar-fill" id="bar-mat" style="background:var(--green)"></div></div>
    </div>
    <div class="score-card soc" onclick="openModal('soc')">
      <div class="edit-hint">✏️ editar</div>
      <div class="sc-label">Sociales</div>
      <div class="sc-current" id="sc-soc" style="color:var(--purple)">76.0</div>
      <div class="sc-meta">Meta: 88+ · faltan <span id="gap-soc"></span></div>
      <div class="sc-bar"><div class="sc-bar-fill" id="bar-soc" style="background:var(--purple)"></div></div>
    </div>
    <div class="score-card ing" onclick="openModal('ing')">
      <div class="edit-hint">✏️ editar</div>
      <div class="sc-label">Inglés</div>
      <div class="sc-current" id="sc-ing" style="color:var(--accent)">89.1</div>
      <div class="sc-meta">Meta: 94+ · faltan <span id="gap-ing"></span></div>
      <div class="sc-bar"><div class="sc-bar-fill" id="bar-ing" style="background:var(--accent)"></div></div>
    </div>
    <div class="score-card total">
       <div class="edit-hint">✏️ editar</div>
      <div class="sc-label">Total</div>
      <div class="sc-current" id="sc-total" style="color:var(--accent)">403</div>
      <div class="sc-meta">Meta: 450 · faltan <span id="gap-total"></span> pts</div>
     <div class="sc-bar"><div class="sc-bar-fill" id="bar-ing" style="background:var(--accent)"></div></div></div></div>
    </div>
  </div>
</div>

<!-- MODAL EDITAR PUNTAJE -->
<div class="modal-overlay" id="modal">
  <div class="modal">
    <h3 id="modal-title">Actualizar puntaje</h3>
    <div class="modal-area-label" id="modal-area-label"></div>
    <input class="score-input" id="modal-input" type="number" min="0" max="100" step="0.1" placeholder="0.0">
    <div class="modal-hint">Ingresa tu último puntaje en esta área (0–100)</div>
    <div class="modal-btns">
      <button class="btn-cancel" onclick="closeModal()">Cancelar</button>
      <button class="btn-save" onclick="saveScore()">Guardar ✓</button>
    </div>
    <div class="sim-history" id="sim-history"></div>
  </div>
</div>

<!-- TABS -->
<div class="nav-tabs">
  <button class="tab-btn active" onclick="showTab('plan',this)">📅 Plan</button>
  <button class="tab-btn" onclick="showTab('clases',this)">🎓 Clases</button>
  <button class="tab-btn" onclick="showTab('quiz',this)">🧠 Quizzes</button>
  <button class="tab-btn" onclick="showTab('progreso',this)">📊 Progreso</button>
  <button class="tab-btn" onclick="showTab('recursos',this)">📚 Recursos</button>
</div>

<!-- ── PANEL PLAN ── -->
<div id="panel-plan" class="panel active">
  <div class="sec-title">Plan mes a mes</div>
  <div class="sec-sub">16 semanas desde hoy hasta el 26 de julio — haz clic en cualquier semana para ver el detalle</div>

  <div class="month-block">
    <div class="month-header"><span class="month-badge">Mes 1</span><span class="month-name">Abril 2026</span><span class="month-focus">— Diagnóstico y bases</span></div>
    <div class="week-grid">
      <div class="week-card p1"><div class="week-head"><span class="wk-num">Semana 1</span><span class="wk-dates">31 mar – 6 abr</span></div><div class="wk-title">🔍 Diagnóstico profundo</div><ul class="wk-tasks"><li>Revisar componentes débiles del simulacro Kappa (tu C2 de LC estaba en 68%)</li><li>Descargar cuadernillos ICFES oficiales de icfes.gov.co</li><li>Crear rutina diaria: 45 min LC + 30 min área débil</li></ul><div class="area-tags"><span class="area-tag tag-lc">Lectura Crítica</span><span class="area-tag tag-soc">Sociales</span></div></div>
      <div class="week-card p1"><div class="week-head"><span class="wk-num">Semana 2</span><span class="wk-dates">7 – 13 abr</span></div><div class="wk-title">📖 Comprensión local de textos (C1)</div><ul class="wk-tasks"><li>Identificar significado de palabras y conectores en contexto</li><li>Ejercicios: "sino", "sin embargo", "por tanto", "no obstante"</li><li>Leer 1 artículo de opinión diario (El Espectador)</li><li>5 preguntas tipo ICFES de LC al día</li></ul><div class="area-tags"><span class="area-tag tag-lc">Lectura Crítica</span></div></div>
      <div class="week-card p2"><div class="week-head"><span class="wk-num">Semana 3</span><span class="wk-dates">14 – 20 abr</span></div><div class="wk-title">🌍 Historia contemporánea — Sociales</div><ul class="wk-tasks"><li>Siglo XX: guerras mundiales, guerra fría, descolonización</li><li>Constitución colombiana: artículos clave (1, 2, 11–41, 86)</li><li>10 preguntas tipo ICFES de Sociales al día</li></ul><div class="area-tags"><span class="area-tag tag-soc">Sociales</span></div></div>
      <div class="week-card p2"><div class="week-head"><span class="wk-num">Semana 4</span><span class="wk-dates">21 – 27 abr</span></div><div class="wk-title">🧪 Química y Biología — Ciencias Naturales</div><ul class="wk-tasks"><li>Tabla periódica, enlaces químicos, reacciones básicas</li><li>Biología celular: ciclo celular, ADN, síntesis de proteínas</li><li>Minitest de 15 preguntas el domingo</li></ul><div class="area-tags"><span class="area-tag tag-cn">Ciencias Nat.</span></div></div>
    </div>
  </div>

  <div class="month-block">
    <div class="month-header"><span class="month-badge" style="background:#0891b2">Mes 2</span><span class="month-name">Mayo 2026</span><span class="month-focus">— Comprensión global y argumentación</span></div>
    <div class="week-grid">
      <div class="week-card p1"><div class="week-head"><span class="wk-num">Semana 5</span><span class="wk-dates">28 abr – 4 may</span></div><div class="wk-title">🧩 Sentido global del texto (C2)</div><ul class="wk-tasks"><li>Reconocer idea principal vs. ideas secundarias</li><li>Textos discontinuos: gráficas, caricaturas, infografías</li><li>Practica con cuadernillo oficial ICFES Saber 11 (LC)</li></ul><div class="area-tags"><span class="area-tag tag-lc">Lectura Crítica</span></div></div>
      <div class="week-card p1"><div class="week-head"><span class="wk-num">Semana 6</span><span class="wk-dates">5 – 11 may</span></div><div class="wk-title">🎤 Proyecto micromoléculas + repaso LC</div><ul class="wk-tasks"><li>Presentar proyecto de micromoléculas (refuerza Ciencias)</li><li>45 min diarios de LC — textos filosóficos tipo ICFES</li><li>Textos argumentativos: estructura tesis-argumento-conclusión</li></ul><div class="area-tags"><span class="area-tag tag-lc">Lectura Crítica</span><span class="area-tag tag-cn">Ciencias Nat.</span></div></div>
      <div class="week-card p2"><div class="week-head"><span class="wk-num">Semana 7</span><span class="wk-dates">12 – 18 may</span></div><div class="wk-title">📐 Geometría y estadística</div><ul class="wk-tasks"><li>Geometría analítica: distancias, pendientes, ecuaciones de recta</li><li>Probabilidad y estadística descriptiva</li><li>10 problemas matemáticos diarios</li></ul><div class="area-tags"><span class="area-tag tag-mat">Matemáticas</span></div></div>
      <div class="week-card p2"><div class="week-head"><span class="wk-num">Semana 8</span><span class="wk-dates">19 – 25 may</span></div><div class="wk-title">🌎 Geografía económica y globalización</div><ul class="wk-tasks"><li>Economía: oferta, demanda, sistemas económicos</li><li>Geografía: regiones naturales, problemáticas ambientales</li><li>Simulacro parcial de Sociales: 25 preguntas cronometradas</li></ul><div class="area-tags"><span class="area-tag tag-soc">Sociales</span></div></div>
    </div>
  </div>

  <div class="month-block">
    <div class="month-header"><span class="month-badge" style="background:#047857">Mes 3</span><span class="month-name">Junio 2026</span><span class="month-focus">— Evaluación crítica e intensificación</span></div>
    <div class="week-grid">
      <div class="week-card p1"><div class="week-head"><span class="wk-num">Semana 9</span><span class="wk-dates">26 may – 1 jun</span></div><div class="wk-title">🔬 Física y termodinámica</div><ul class="wk-tasks"><li>Leyes de Newton, trabajo, energía, potencia</li><li>Termodinámica: temperatura, calor, leyes</li><li>Práctica con textos científicos tipo ICFES (gráficas, experimentos)</li></ul><div class="area-tags"><span class="area-tag tag-cn">Ciencias Nat.</span></div></div>
      <div class="week-card p1"><div class="week-head"><span class="wk-num">Semana 10</span><span class="wk-dates">2 – 8 jun</span></div><div class="wk-title">💭 Evaluación crítica (C3)</div><ul class="wk-tasks"><li>Identificar falacias argumentativas en textos</li><li>Distinguir hechos de opiniones y supuestos implícitos</li><li>Textos filosóficos breves (Platón, Descartes, Kant)</li></ul><div class="area-tags"><span class="area-tag tag-lc">Lectura Crítica</span></div></div>
      <div class="week-card p2"><div class="week-head"><span class="wk-num">Semana 11</span><span class="wk-dates">9 – 15 jun</span></div><div class="wk-title">📝 Simulacro parcial completo</div><ul class="wk-tasks"><li>Simulacro de todas las áreas en condiciones reales (3 horas)</li><li>Analizar resultados y actualizar puntajes aquí ↑</li><li>Meta de este simulacro: 425+ puntos</li></ul><div class="area-tags"><span class="area-tag tag-lc">LC</span><span class="area-tag tag-cn">CN</span><span class="area-tag tag-mat">Mat</span><span class="area-tag tag-soc">Soc</span><span class="area-tag tag-ing">Ing</span></div></div>
      <div class="week-card p2"><div class="week-head"><span class="wk-num">Semana 12</span><span class="wk-dates">16 – 22 jun</span></div><div class="wk-title">🔁 Refuerzo de áreas débiles</div><ul class="wk-tasks"><li>Intensificar las 2 áreas más bajas del simulacro</li><li>Reading comprehension avanzado para Inglés</li><li>Álgebra avanzada: funciones, logaritmos, trigonometría</li></ul><div class="area-tags"><span class="area-tag tag-ing">Inglés</span><span class="area-tag tag-mat">Matemáticas</span></div></div>
    </div>
  </div>

  <div class="month-block">
    <div class="month-header"><span class="month-badge" style="background:#b45309">Mes 4</span><span class="month-name">Julio 2026</span><span class="month-focus">— Sprint final</span></div>
    <div class="week-grid">
      <div class="week-card p1"><div class="week-head"><span class="wk-num">Semana 13</span><span class="wk-dates">23 – 29 jun</span></div><div class="wk-title">🚀 Modo intensivo</div><ul class="wk-tasks"><li>2 horas de estudio diario mínimo</li><li>Rotar áreas: LC mañana, Ciencias/Sociales tarde</li><li>Repasar todos los errores de simulacros anteriores</li></ul><div class="area-tags"><span class="area-tag tag-lc">LC</span><span class="area-tag tag-cn">CN</span><span class="area-tag tag-soc">Soc</span></div></div>
      <div class="week-card p1"><div class="week-head"><span class="wk-num">Semana 14</span><span class="wk-dates">30 jun – 6 jul</span></div><div class="wk-title">📋 Simulacro final completo</div><ul class="wk-tasks"><li>Simulacro cronometrado en condiciones reales</li><li>Meta: 440–450 puntos</li><li>Revisión analítica de cada error</li></ul><div class="area-tags"><span class="area-tag tag-lc">LC</span><span class="area-tag tag-cn">CN</span><span class="area-tag tag-mat">Mat</span><span class="area-tag tag-soc">Soc</span><span class="area-tag tag-ing">Ing</span></div></div>
      <div class="week-card p2"><div class="week-head"><span class="wk-num">Semana 15</span><span class="wk-dates">7 – 13 jul</span></div><div class="wk-title">🎯 Consolidación y repaso selectivo</div><ul class="wk-tasks"><li>Solo repasar temas donde persistan errores</li><li>No aprender temas nuevos — afianzar lo visto</li><li>30 preguntas de práctica por área</li></ul><div class="area-tags"><span class="area-tag tag-lc">LC</span><span class="area-tag tag-soc">Soc</span></div></div>
      <div class="week-card p3"><div class="week-head"><span class="wk-num">Semana 16</span><span class="wk-dates">14 – 20 jul</span></div><div class="wk-title">😴 Descanso activo</div><ul class="wk-tasks"><li>Máximo 45 min diarios — solo repasar apuntes</li><li>Dormir bien, hidratarse, cuidar el estado físico</li><li>Preparar documentos para el día del examen</li></ul></div>
      <div class="week-card exam"><div class="week-head"><span class="wk-num" style="color:var(--accent)">🏆 DÍA D</span><span class="wk-dates" style="color:var(--accent)">26 julio 2026</span></div><div class="wk-title" style="color:var(--accent)">ICFES Saber 11 — Examen oficial</div><ul class="wk-tasks"><li>Dormir 8 horas la noche anterior</li><li>Desayuno completo, llegar 30 min antes</li><li>Documento de identidad + admisión</li><li>¡Confiar en la preparación! 💪</li></ul></div>
    </div>
  </div>
</div>

<!-- ── PANEL CLASES ── -->
<div id="panel-clases" class="panel">
  <div class="sec-title">🎓 Clases de repaso</div>
  <div class="sec-sub">Explicaciones como si estuvieras en clase — haz clic en cada tema para abrirlo</div>

  <!-- CLASE 1: LC -->
  <div class="class-block">
    <div class="class-header" onclick="toggleClass('lc1')">
      <div class="class-icon">📖</div>
      <div><div class="class-title">Lectura Crítica — Las 3 Competencias del ICFES</div><div class="class-subtitle">Tu área más débil · Puntaje actual: 68.3 → Meta: 85+</div></div>
      <div class="class-toggle" id="toggle-lc1">▼</div>
    </div>
    <div class="class-body" id="body-lc1">
      <p>Antes de entrar a practicar preguntas, necesitás entender <strong>qué te están evaluando exactamente</strong>. El ICFES no evalúa si leíste mucho o si tenés buena memoria — evalúa si sabés <em>pensar con un texto</em>. Para eso usa tres competencias:</p>
      <div class="competencia-grid">
        <div class="comp-box"><div class="comp-code">C1</div><div class="comp-name">Comprensión local</div><div class="comp-desc">Entender el significado de palabras, frases o fragmentos dentro del texto</div></div>
        <div class="comp-box"><div class="comp-code">C2</div><div class="comp-name">Comprensión global</div><div class="comp-desc">Captar la idea principal, el propósito y la estructura del texto completo</div></div>
        <div class="comp-box"><div class="comp-code">C3</div><div class="comp-name">Evaluación crítica</div><div class="comp-desc">Evaluar argumentos, detectar falacias, identificar perspectivas e intenciones</div></div>
      </div>
      <p>Tu simulacro Kappa mostró que tu C2 estuvo en <strong>68%</strong> — eso significa que puedes leer palabras pero te cuesta ver el texto como un todo. Hay que corregir eso.</p>
      <p><strong>¿Cómo mejorar C2?</strong> Cada vez que leas un texto, antes de ver las preguntas hazte esta pregunta: <em>"¿Cuál es la única idea que el autor NUNCA quitaría de este texto?"</em> Esa es la idea principal. Todo lo demás son detalles o ejemplos que la sostienen.</p>
      <div class="example">
        <strong>Ejemplo práctico:</strong><br><br>
        Texto: <em>"Los centros comerciales surgen en la medida en que hay desvalorización del centro de las ciudades y pérdida de funciones de sitios que antes convocaban a la ciudadanía. El centro comercial es escenografía, crea una ilusión de interacción ciudadana que en realidad no existe."</em><br><br>
        ❌ Respuesta incorrecta de C2: "El texto habla sobre centros comerciales."<br>
        ✅ Respuesta correcta de C2: "El autor critica que los centros comerciales simulan una vida ciudadana que en realidad han destruido."<br><br>
        La diferencia es enorme. La primera repite el tema. La segunda captura la <em>postura</em> del autor.
      </div>
      <p><strong>¿Cómo mejorar C3?</strong> La evaluación crítica requiere que preguntes: <em>"¿Por qué el autor dice esto? ¿Qué está asumiendo sin decirlo? ¿Podría estar equivocado?"</em></p>
      <div class="tip">💡 <strong>Truco de oro para LC:</strong> Lee el texto completo primero. Luego lee la pregunta. Luego vuelve al texto a buscar evidencia. Nunca respondas desde tu opinión personal — responde siempre desde lo que dice el texto.</div>
      <div class="warning">⚠️ <strong>Error más común:</strong> Eliminar opciones porque "suenan raras" o "no se escuchan bien". En LC, la respuesta correcta muchas veces es la que parece más difícil de leer — porque está siendo más precisa.</div>
    </div>
  </div>

  <!-- CLASE 2: CONECTORES -->
  <div class="class-block">
    <div class="class-header" onclick="toggleClass('con1')">
      <div class="class-icon">🔗</div>
      <div><div class="class-title">Conectores lógicos — La clave para no perder puntos fáciles</div><div class="class-subtitle">Lectura Crítica · Preguntas tipo C1 · Aparecen en TODOS los exámenes</div></div>
      <div class="class-toggle" id="toggle-con1">▼</div>
    </div>
    <div class="class-body" id="body-con1">
      <p>Las preguntas de conectores son de las más frecuentes en el ICFES. Te muestran un texto con una palabra subrayada como <strong>"sin embargo", "sino", "por tanto", "no obstante"</strong> y te preguntan qué función cumple.</p>
      <p>El secreto es que estas palabras siempre hacen <strong>UNA sola cosa</strong>. No hay ambigüedad. Aprende las categorías:</p>
      <div class="example">
        <strong>🔴 Adversativos</strong> — Introducen una idea que contrasta o contradice lo anterior<br>
        → sin embargo / no obstante / pero / aunque / a pesar de<br><br>
        <strong>🟡 Causales</strong> — Explican el por qué de algo<br>
        → porque / ya que / puesto que / dado que<br><br>
        <strong>🟢 Consecutivos</strong> — Presentan una consecuencia lógica<br>
        → por tanto / por lo tanto / en consecuencia / así que<br><br>
        <strong>🔵 Aditivos</strong> — Añaden información a lo dicho<br>
        → además / también / asimismo / incluso<br><br>
        <strong>🟣 Restrictivos</strong> — Limitan o condicionan lo dicho<br>
        → solo / únicamente / siempre que / a menos que<br><br>
        <strong>⚪ Explicativos</strong> — Aclaran o reformulan lo anterior<br>
        → es decir / o sea / esto es / en otras palabras
      </div>
      <div class="tip">💡 <strong>Estrategia para preguntas de conectores:</strong> Cubre la palabra con el dedo. Lee la oración sin ella. Luego identifica qué relación existe entre las dos ideas (¿contradicen? ¿una causa la otra?). Eso te dice qué tipo de conector va ahí.</div>
      <div class="example">
        <strong>Ejercicio rápido:</strong><br><br>
        "La medicina popular no tiene validez científica. _____, en algunos casos puede complementar a la medicina moderna."<br><br>
        ¿Qué conector va ahí? Hay contraste entre las dos ideas (una dice que no es válida, la otra dice que podría ser útil). → Adversativo: <strong>"Sin embargo"</strong>.
      </div>
    </div>
  </div>

  <!-- CLASE 3: SOCIALES -->
  <div class="class-block">
    <div class="class-header" onclick="toggleClass('soc1')">
      <div class="class-icon">🌍</div>
      <div><div class="class-title">Sociales — Constitución Política de Colombia</div><div class="class-subtitle">Sociales y Ciudadanas · Artículos clave · Alta frecuencia en ICFES</div></div>
      <div class="class-toggle" id="toggle-soc1">▼</div>
    </div>
    <div class="class-body" id="body-soc1">
      <p>El ICFES no te pide que memorices artículos de memoria. Te da casos prácticos y te pregunta cuál derecho se viola, cuál mecanismo aplica, o qué principio rige. Para eso necesitás entender la <strong>lógica</strong> de la Constitución, no memorizarla.</p>
      <p><strong>Los 4 pilares que más aparecen:</strong></p>
      <div class="example">
        <strong>1. Colombia como Estado Social de Derecho (Art. 1)</strong><br>
        "Social" significa que el Estado tiene obligación de garantizar condiciones de vida digna a todos, no solo de no meterse en la vida de la gente.<br><br>
        <strong>2. Derechos fundamentales (Art. 11–41)</strong><br>
        Los más frecuentes en ICFES: vida (11), igualdad (13), libertad de expresión (20), educación (67), trabajo (25), salud (49).<br><br>
        <strong>3. Mecanismos de participación ciudadana (Art. 103)</strong><br>
        → Tutela: protege derechos fundamentales (inmediata)<br>
        → Acción popular: protege derechos colectivos<br>
        → Revocatoria del mandato: destituir alcaldes/gobernadores<br>
        → Referendo / Plebiscito / Consulta popular: decisiones colectivas<br><br>
        <strong>4. Ramas del poder público</strong><br>
        Legislativa (Congreso) · Ejecutiva (Presidente) · Judicial (Cortes)<br>
        + Órganos de control: Fiscalía, Procuraduría, Contraloría, Defensoría
      </div>
      <div class="tip">💡 <strong>Truco para preguntas de mecanismos:</strong> Si el caso habla de un derecho individual violado → Tutela. Si habla de un espacio público dañado o un bien colectivo → Acción popular. Si habla de un alcalde que incumplió su programa → Revocatoria.</div>
      <div class="warning">⚠️ Error frecuente: confundir plebiscito y referendo. <strong>Referendo</strong> = pregunta sobre una norma ya escrita (¿aprobamos esta ley?). <strong>Plebiscito</strong> = el presidente consulta sobre una decisión política suya.</div>
    </div>
  </div>

  <!-- CLASE 4: CIENCIAS -->
  <div class="class-block">
    <div class="class-header" onclick="toggleClass('cn1')">
      <div class="class-icon">🧪</div>
      <div><div class="class-title">Ciencias Naturales — Cómo leer experimentos en el ICFES</div><div class="class-subtitle">Ciencias Naturales · Competencia de indagación · Tu punto más recuperable</div></div>
      <div class="class-toggle" id="toggle-cn1">▼</div>
    </div>
    <div class="class-body" id="body-cn1">
      <p>En Ciencias Naturales, el ICFES no te pregunta si memorizaste la fórmula de la fotosíntesis. Te da una gráfica, una tabla o la descripción de un experimento y te pregunta: <strong>¿qué concluyes? ¿qué variable se controló? ¿qué hipótesis se confirma?</strong></p>
      <p>Para responder bien, necesitás saber leer experimentos con esta estructura mental:</p>
      <div class="example">
        <strong>Anatomía de un experimento tipo ICFES:</strong><br><br>
        🔬 <strong>Variable independiente:</strong> Lo que el investigador cambia a propósito.<br>
        "Aumentamos la temperatura de 20°C a 40°C"<br><br>
        📊 <strong>Variable dependiente:</strong> Lo que se mide como resultado.<br>
        "Medimos la velocidad de reacción"<br><br>
        🔒 <strong>Variable controlada:</strong> Lo que se mantiene igual para que la comparación sea válida.<br>
        "La concentración de reactivos fue la misma en todos los casos"<br><br>
        ✅ <strong>Conclusión válida:</strong> Solo puedes concluir lo que el experimento midió directamente.<br>
        Si midieron velocidad de reacción con temperatura, NO puedes concluir nada sobre presión o concentración.
      </div>
      <p>Tu proyecto de <strong>micromoléculas para cáncer de páncreas</strong> te da una ventaja enorme aquí. Ya sabes pensar como científico — solo aplicá ese pensamiento a los textos del ICFES.</p>
      <div class="tip">💡 <strong>Regla de oro:</strong> En preguntas de experimentos, NUNCA elijas una respuesta que concluya más de lo que el experimento midió. Las opciones incorrectas siempre exageran o generalizan demasiado.</div>
    </div>
  </div>

  <!-- CLASE 5: MATH -->
  <div class="class-block">
    <div class="class-header" onclick="toggleClass('mat1')">
      <div class="class-icon">📐</div>
      <div><div class="class-title">Matemáticas — Estrategia para llegar a 95+</div><div class="class-subtitle">Ya estás en 90 · Solo necesitás +5 pts · Enfocate en errores tontos</div></div>
      <div class="class-toggle" id="toggle-mat1">▼</div>
    </div>
    <div class="class-body" id="body-mat1">
      <p>Matemáticas es tu área más fuerte. Con 90 puntos ya estás en desempeño avanzado. Para llegar a 95+ no necesitás aprender cosas nuevas — necesitás <strong>eliminar los errores que te están costando puntos fáciles</strong>.</p>
      <p>Los errores más comunes de estudiantes en tu nivel:</p>
      <div class="example">
        <strong>❌ Error 1: Calcular bien pero responder mal</strong><br>
        El problema pide "¿cuántos quedan?" y tú calculas "¿cuántos se fueron?". Lee la pregunta DOS veces antes de responder.<br><br>
        <strong>❌ Error 2: No verificar la respuesta</strong><br>
        Si el tiempo te lo permite, sustituye tu respuesta en la ecuación original para verificar. 30 segundos pueden salvarte de un error.<br><br>
        <strong>❌ Error 3: Rendirse ante problemas de contexto</strong><br>
        Los problemas de palabras se resuelven en 3 pasos: (1) identifica qué te piden, (2) traduce a lenguaje matemático, (3) resuelve. No te dejes intimidar por el texto largo.
      </div>
      <div class="example">
        <strong>Los temas que más aparecen en Matemáticas ICFES:</strong><br><br>
        📊 Estadística y probabilidad (siempre aparece)<br>
        📈 Funciones y gráficas (f(x), dominio, imagen)<br>
        📐 Geometría analítica (distancias, pendientes, ecuaciones)<br>
        🔢 Álgebra (ecuaciones, factorización, sistemas)<br>
        📏 Variación y proporcionalidad (regla de tres, porcentajes)
      </div>
      <div class="tip">💡 Para llegar de 90 a 95: haz 10 ejercicios diarios de los temas anteriores, pero cronometrado. La velocidad también importa — en el ICFES el tiempo es limitado.</div>
    </div>
  </div>

  <!-- CLASE 6: ENGLISH -->
  <div class="class-block">
    <div class="class-header" onclick="toggleClass('ing1')">
      <div class="class-icon">🇬🇧</div>
      <div><div class="class-title">Inglés — De 89 a 94: comprensión de lectura avanzada</div><div class="class-subtitle">También prepara para el TOEFL · Doble beneficio</div></div>
      <div class="class-toggle" id="toggle-ing1">▼</div>
    </div>
    <div class="class-body" id="body-ing1">
      <p>El ICFES de Inglés evalúa principalmente comprensión lectora. No es un examen de gramática pura — es un examen de <strong>entender textos en inglés</strong>. Igual que LC pero en inglés.</p>
      <p><strong>Tipos de preguntas que aparecen:</strong></p>
      <div class="example">
        <strong>1. Main idea questions</strong> → "What is the main topic of the passage?"<br>
        Estrategia: igual que C2 en LC. Busca la idea que el autor NUNCA quitaría.<br><br>
        <strong>2. Vocabulary in context</strong> → "The word X most likely means..."<br>
        Estrategia: No adivines. Lee las oraciones antes y después de la palabra. El contexto te dice el significado.<br><br>
        <strong>3. Inference questions</strong> → "What can be inferred from paragraph 2?"<br>
        Estrategia: La respuesta correcta es algo que el texto implica pero no dice literalmente. Elimina las que sean demasiado extremas o las que el texto no mencionó.<br><br>
        <strong>4. Grammar questions</strong> → Completa la oración con la forma correcta del verbo<br>
        Estrategia: Identifica el tiempo verbal del contexto (presente, pasado, condicional) y aplica la regla.
      </div>
      <div class="tip">💡 Bonus: prepararte para el ICFES de inglés y para el TOEFL son casi lo mismo. Cada texto que practicas aquí también sirve para tu meta del TOEFL 110+.</div>
    </div>
  </div>
</div>

<!-- ── PANEL QUIZ ── -->
<div id="panel-quiz" class="panel">
  <div class="sec-title">🧠 Quizzes de práctica</div>
  <div class="sec-sub">Preguntas tipo ICFES — selecciona un área y empieza</div>
  <div id="quiz-sel-section">
    <div class="quiz-sel">
      <div class="qa-btn" onclick="selArea('lc')" id="qbtn-lc"><div class="qa-icon">📖</div><div class="qa-name">Lectura Crítica</div><div class="qa-count">8 preguntas</div></div>
      <div class="qa-btn" onclick="selArea('cn')" id="qbtn-cn"><div class="qa-icon">🧪</div><div class="qa-name">Ciencias Naturales</div><div class="qa-count">6 preguntas</div></div>
      <div class="qa-btn" onclick="selArea('mat')" id="qbtn-mat"><div class="qa-icon">📐</div><div class="qa-name">Matemáticas</div><div class="qa-count">6 preguntas</div></div>
      <div class="qa-btn" onclick="selArea('soc')" id="qbtn-soc"><div class="qa-icon">🌍</div><div class="qa-name">Sociales</div><div class="qa-count">6 preguntas</div></div>
      <div class="qa-btn" onclick="selArea('ing')" id="qbtn-ing"><div class="qa-icon">🇬🇧</div><div class="qa-name">Inglés</div><div class="qa-count">5 preguntas</div></div>
    </div>
    <button class="start-btn" id="start-btn" onclick="startQuiz()" disabled>Selecciona un área para empezar</button>
  </div>
  <div id="quiz-container">
    <div class="quiz-card" id="quiz-card">
      <div class="qpbar"><div class="qpfill" id="qpfill"></div></div>
      <div class="qmeta"><span id="q-badge" class="q-badge"></span><span id="q-counter"></span></div>
      <div id="q-passage" class="q-passage" style="display:none"></div>
      <div id="q-question" class="q-question"></div>
      <div id="q-options" class="q-options"></div>
      <div id="q-feedback" class="q-feedback"></div>
      <button class="next-btn" id="next-btn" onclick="nextQ()">Siguiente →</button>
    </div>
    <div class="quiz-results" id="quiz-results">
      <div style="font-size:2rem">🎯</div>
      <div class="res-score" id="res-score"></div>
      <div class="res-label" id="res-label"></div>
      <button class="retry-btn" onclick="resetQuiz()">Intentar de nuevo</button>
    </div>
  </div>
</div>

<!-- ── PANEL PROGRESO ── -->
<div id="panel-progreso" class="panel">
  <div class="sec-title">📊 Mi progreso</div>
  <div class="sec-sub">Actualiza tus puntajes haciendo clic en las tarjetas de arriba</div>
  <div class="prog-grid" id="prog-grid"></div>
  <div class="chart-section">
    <div class="chart-title">📈 Historial de simulacros</div>
    <div class="sim-list" id="sim-list"></div>
    <button class="add-sim-btn" onclick="openAddSim()">+ Agregar resultado de simulacro</button>
  </div>
</div>

<!-- MODAL ADD SIM -->
<div class="modal-overlay" id="modal-sim">
  <div class="modal">
    <h3>Agregar simulacro</h3>
    <div style="display:grid;gap:.7rem;margin-top:.5rem">
      <div>
        <div class="modal-area-label">Nombre del simulacro</div>
        <input id="sim-name-input" class="score-input" style="font-size:1rem" type="text" placeholder="Ej: Sigma 11 Saber">
      </div>
      <div>
        <div class="modal-area-label">Puntaje total</div>
        <input id="sim-score-input" class="score-input" type="number" min="0" max="500" placeholder="400">
      </div>
      <div>
        <div class="modal-area-label">Fecha</div>
        <input id="sim-date-input" class="score-input" style="font-size:1rem" type="date">
      </div>
    </div>
    <div class="modal-btns" style="margin-top:1rem">
      <button class="btn-cancel" onclick="closeAddSim()">Cancelar</button>
      <button class="btn-save" onclick="saveSim()">Guardar ✓</button>
    </div>
  </div>
</div>

<!-- ── PANEL RECURSOS ── -->
<div id="panel-recursos" class="panel">
  <div class="sec-title">📚 Recursos de estudio</div>
  <div class="sec-sub">Materiales oficiales y gratuitos — los más útiles para tu preparación</div>
  <div class="res-grid">
    <div class="res-card"><div class="res-icon">🏛️</div><div class="res-title">ICFES Oficial — Practica</div><div class="res-desc">Cuadernillos con preguntas reales de exámenes anteriores. La fuente más confiable.</div><a class="res-link" href="https://www.icfes.gov.co/caja-de-herramientas-saber-11/practica/" target="_blank">→ icfes.gov.co/practica</a></div>
    <div class="res-card"><div class="res-icon">📄</div><div class="res-title">Cuadernillo LC — Saber 11</div><div class="res-desc">Cuadernillo oficial de Lectura Crítica con preguntas explicadas. Prioritario para tu área más débil.</div><a class="res-link" href="https://eduka.occidente.co/wp-content/uploads/2021/07/Cuadernillo-de-preguntas-Saber-11-lectura-critica.pdf" target="_blank">→ Descargar PDF</a></div>
    <div class="res-card"><div class="res-icon">🗂️</div><div class="res-title">Alto Puntaje — Banco de preguntas</div><div class="res-desc">Cuadernillos ICFES de múltiples años disponibles para descargar gratuitamente.</div><a class="res-link" href="https://altopuntaje.com/prueba-icfes-preguntas-saber-11-examenes/" target="_blank">→ altopuntaje.com</a></div>
    <div class="res-card"><div class="res-icon">🌐</div><div class="res-title">Khan Academy en Español</div><div class="res-desc">Matemáticas y Ciencias con ejercicios adaptativos y videos. Gratis y sin registro.</div><a class="res-link" href="https://es.khanacademy.org" target="_blank">→ khanacademy.org</a></div>
    <div class="res-card"><div class="res-icon">📰</div><div class="res-title">El Espectador</div><div class="res-desc">Leer artículos de opinión mejora LC y Sociales. 15 min diarios hacen diferencia.</div><a class="res-link" href="https://www.elespectador.com" target="_blank">→ elespectador.com</a></div>
    <div class="res-card"><div class="res-icon">🎯</div><div class="res-title">TOEFL — Preparación oficial</div><div class="res-desc">Recursos oficiales de ETS para preparar el TOEFL iBT. Tu meta: 110+/120.</div><a class="res-link" href="https://www.ets.org/toefl/test-takers/ibt/prepare.html" target="_blank">→ ets.org/toefl</a></div>
  </div>
</div>

<!-- TOAST -->
<div class="toast" id="toast">✓ Puntaje guardado</div>

<script>
// ── STORAGE ──
const STORE_KEY = 'jordan_icfes_v2';
function load(){try{return JSON.parse(localStorage.getItem(STORE_KEY))||null;}catch{return null;}}
function save(d){localStorage.setItem(STORE_KEY,JSON.stringify(d));}

const DEFAULTS = {
  scores:{lc:68.3,cn:82.8,mat:90.0,soc:76.0,ing:89.1},
  history:{lc:[],cn:[],mat:[],soc:[],ing:[]},
  sims:[
    {name:'Sigma 10 Saber',score:403,date:'2026-01-13'},
    {name:'Kappa Premium 11 Saber',score:400,date:'2026-02-12'}
  ],
  lastUpdate:null
};
const GOALS = {lc:85,cn:93,mat:95,soc:88,ing:94};
const COLORS = {lc:'#ef4444',cn:'#f59e0b',mat:'#10b981',soc:'#7c3aed',ing:'#00e5ff'};
const LABELS = {lc:'Lectura Crítica',cn:'Ciencias Naturales',mat:'Matemáticas',soc:'Sociales',ing:'Inglés'};

let state = load() || JSON.parse(JSON.stringify(DEFAULTS));

// ── COUNTDOWN ──
function tick(){
  const target=new Date('2026-07-26T08:00:00');
  const now=new Date();
  const diff=Math.max(0,target-now);
  const d=Math.floor(diff/864e5);
  const h=Math.floor((diff%864e5)/36e5);
  const m=Math.floor((diff%36e5)/6e4);
  document.getElementById('cd-d').textContent=d;
  document.getElementById('cd-h').textContent=h;
  document.getElementById('cd-m').textContent=m;
}
tick();setInterval(tick,60000);

// ── SCORES ──
function calcTotal(){
  const s=state.scores;
  return Math.round((s.lc+s.cn+s.mat+s.soc+s.ing)/5*10)/10;
}
function updateUI(){
  const areas=['lc','cn','mat','soc','ing'];
  areas.forEach(a=>{
    const cur=state.scores[a];
    const goal=GOALS[a];
    const gap=Math.max(0,(goal-cur).toFixed(1));
    document.getElementById('sc-'+a).textContent=cur.toFixed(1);
    document.getElementById('gap-'+a).textContent=gap>0?'+'+gap:' ✅';
    const pct=Math.min(100,(cur/goal)*100);
    document.getElementById('bar-'+a).style.width=pct+'%';
  });
  const tot=calcTotal();
  document.getElementById('sc-total').textContent=tot.toFixed(1);
  document.getElementById('gap-total').textContent=Math.max(0,(450-tot).toFixed(1));
  document.getElementById('bar-total').style.width=Math.min(100,(tot/450)*100)+'%';
  if(state.lastUpdate){
    const d=new Date(state.lastUpdate);
    document.getElementById('last-update-label').textContent='Actualizado: '+d.toLocaleDateString('es-CO',{day:'numeric',month:'short',hour:'2-digit',minute:'2-digit'});
  }
  renderProgress();
  renderSims();
}

// ── MODAL SCORE ──
let editingArea=null;
function openModal(area){
  editingArea=area;
  document.getElementById('modal-title').textContent='Actualizar — '+LABELS[area];
  document.getElementById('modal-area-label').textContent='Puntaje actual: '+state.scores[area].toFixed(1)+' · Meta: '+GOALS[area]+'+';
  document.getElementById('modal-input').value='';
  renderModalHistory(area);
  document.getElementById('modal').classList.add('open');
  setTimeout(()=>document.getElementById('modal-input').focus(),100);
}
function closeModal(){document.getElementById('modal').classList.remove('open');editingArea=null;}
function saveScore(){
  const val=parseFloat(document.getElementById('modal-input').value);
  if(isNaN(val)||val<0||val>100){alert('Ingresa un puntaje entre 0 y 100');return;}
  const prev=state.scores[editingArea];
  state.scores[editingArea]=Math.round(val*10)/10;
  state.history[editingArea].push({score:val,prev:prev,date:new Date().toISOString()});
  state.lastUpdate=new Date().toISOString();
  save(state);
  updateUI();
  closeModal();
  showToast('✓ '+LABELS[editingArea]+': '+val.toFixed(1)+' pts guardado');
}
function renderModalHistory(area){
  const h=state.history[area]||[];
  const el=document.getElementById('sim-history');
  if(!h.length){el.innerHTML='<div style="font-size:.75rem;color:var(--muted);padding-top:.5rem">Sin historial para esta área aún.</div>';return;}
  const last=[...h].reverse().slice(0,5);
  el.innerHTML='<div style="font-size:.72rem;color:var(--muted);margin-bottom:.4rem">Últimas actualizaciones:</div>'+
    last.map((e,i)=>{
      const d=new Date(e.date);
      const delta=e.score-e.prev;
      const dStr=(delta>=0?'+':'')+delta.toFixed(1);
      const dColor=delta>=0?'var(--green)':'var(--red)';
      return `<div class="sim-entry">
        <span class="sim-date">${d.toLocaleDateString('es-CO',{day:'numeric',month:'short'})}</span>
        <span class="sim-score">${e.score.toFixed(1)}</span>
        <span style="color:${dColor};font-size:.72rem">${dStr}</span>
        <button class="sim-del" onclick="delHistory('${area}',${h.length-1-i})">✕</button>
      </div>`;
    }).join('');
}
function delHistory(area,idx){
  state.history[area].splice(idx,1);
  save(state);
  renderModalHistory(area);
  showToast('Entrada eliminada');
}
document.getElementById('modal').addEventListener('click',function(e){if(e.target===this)closeModal();});
document.getElementById('modal-input').addEventListener('keydown',function(e){if(e.key==='Enter')saveScore();});

// ── PROGRESS PANEL ──
function renderProgress(){
  const areas=['lc','cn','mat','soc','ing'];
  const emojis={lc:'🔴',cn:'🟡',mat:'✅',soc:'🟣',ing:'🔵'};
  document.getElementById('prog-grid').innerHTML=areas.map(a=>{
    const cur=state.scores[a];
    const goal=GOALS[a];
    const pct=Math.min(100,(cur/goal)*100);
    const gap=Math.max(0,goal-cur);
    return `<div class="prog-item">
      <div class="prog-top">
        <span class="prog-area">${emojis[a]} ${LABELS[a]}</span>
        <span class="prog-nums">${cur.toFixed(1)} → <span>${goal}+</span>${gap>0?' (faltan +'+gap.toFixed(1)+')':" ✅"}</span>
      </div>
      <div class="prog-wrap"><div class="prog-fill" style="width:${pct}%;background:${COLORS[a]}"></div></div>
    </div>`;
  }).join('')+`<div class="prog-item" style="border-color:rgba(0,229,255,.3)">
    <div class="prog-top">
      <span class="prog-area" style="color:var(--accent)">🎯 Total</span>
      <span class="prog-nums">${calcTotal().toFixed(1)} → <span>450+</span></span>
    </div>
    <div class="prog-wrap"><div class="prog-fill" style="width:${Math.min(100,(calcTotal()/450)*100)}%;background:linear-gradient(90deg,var(--accent),var(--purple))"></div></div>
  </div>`;
}

// ── SIMS ──
function renderSims(){
  const sims=state.sims||[];
  const el=document.getElementById('sim-list');
  if(!sims.length){el.innerHTML='<div style="font-size:.8rem;color:var(--muted);padding:.5rem">Sin simulacros registrados aún.</div>';return;}
  const sorted=[...sims].sort((a,b)=>new Date(a.date)-new Date(b.date));
  el.innerHTML=sorted.map((s,i)=>{
    const prev=i>0?sorted[i-1].score:null;
    const delta=prev!==null?s.score-prev:null;
    const dStr=delta!==null?(delta>=0?'<span style="color:var(--green)">+'+delta+'</span>':'<span style="color:var(--red)">'+delta+'</span>'):'';
    const d=new Date(s.date+'T12:00:00');
    return `<div class="sim-row">
      <div>
        <div style="font-size:.85rem;font-weight:600">${s.name}</div>
        <div class="sim-row-date">${d.toLocaleDateString('es-CO',{day:'numeric',month:'long',year:'numeric'})}</div>
      </div>
      <div style="display:flex;align-items:center;gap:.7rem">
        ${dStr}
        <div class="sim-row-score">${s.score}</div>
        <button style="background:none;border:none;color:var(--red);cursor:pointer;opacity:.5;font-size:.75rem" onclick="delSim(${i})">✕</button>
      </div>
    </div>`;
  }).join('');
}
function openAddSim(){
  document.getElementById('sim-date-input').value=new Date().toISOString().split('T')[0];
  document.getElementById('modal-sim').classList.add('open');
}
function closeAddSim(){document.getElementById('modal-sim').classList.remove('open');}
function saveSim(){
  const name=document.getElementById('sim-name-input').value.trim();
  const score=parseInt(document.getElementById('sim-score-input').value);
  const date=document.getElementById('sim-date-input').value;
  if(!name||isNaN(score)||!date){alert('Completa todos los campos');return;}
  if(!state.sims)state.sims=[];
  state.sims.push({name,score,date});
  save(state);
  renderSims();
  closeAddSim();
  showToast('✓ Simulacro guardado');
}
function delSim(i){
  state.sims.splice(i,1);
  save(state);
  renderSims();
}
document.getElementById('modal-sim').addEventListener('click',function(e){if(e.target===this)closeAddSim();});

// ── TABS ──
function showTab(name,btn){
  document.querySelectorAll('.panel').forEach(p=>p.classList.remove('active'));
  document.querySelectorAll('.tab-btn').forEach(b=>b.classList.remove('active'));
  document.getElementById('panel-'+name).classList.add('active');
  btn.classList.add('active');
}

// ── CLASSES ──
function toggleClass(id){
  const body=document.getElementById('body-'+id);
  const toggle=document.getElementById('toggle-'+id);
  body.classList.toggle('open');
  toggle.classList.toggle('open');
}

// ── TOAST ──
function showToast(msg){
  const t=document.getElementById('toast');
  t.textContent=msg;
  t.classList.add('show');
  setTimeout(()=>t.classList.remove('show'),2500);
}

// ── QUIZ DATA ──
const QD={
  lc:{name:'Lectura Crítica',color:'#ef4444',qs:[
    {p:'Los centros comerciales surgen en la medida en que hay desvalorización del centro de las ciudades y una pérdida de funciones de los sitios que en otras épocas convocaban allí a la ciudadanía: la plaza pública, los grandes teatros y las instancias gubernamentales. "Descuidamos tanto la calle que la simulación de la calle triunfa". El centro comercial es escenografía, y crea una ilusión de interacción ciudadana que en realidad no existe.',q:'La función del conector "y" en "la plaza pública, los grandes teatros y las instancias gubernamentales" es:',opts:['Contrastar los tres lugares mencionados entre sí','Enumerar ejemplos de lo que antes convocaba a la ciudadanía','Señalar que esos tres lugares desaparecieron','Introducir una consecuencia de la desvalorización'],ans:1,exp:'El conector "y" en este contexto tiene función aditiva: une elementos de una lista de ejemplos. Los tres lugares son ejemplos de espacios que antes cumplían funciones sociales. Opción B correcta.'},
    {p:'Por consiguiente, si hubiesen dos anillos como el de Giges y se diera uno a un hombre justo y otro a uno injusto, ninguno perseveraría en la justicia ni soportaría abstenerse de bienes ajenos. E incluso se diría que esto es una importante prueba de que nadie es justo si no es forzado a serlo.',q:'La tesis central del fragmento anterior es que:',opts:['La justicia es un valor innato en todos los seres humanos','Nadie actúa justamente sin la presión de consecuencias externas','El poder corrompe inevitablemente a quienes lo poseen','Los anillos mágicos revelan la naturaleza injusta del ser humano'],ans:1,exp:'El texto afirma que "nadie es justo si no es forzado a serlo". Esto implica que la justicia es externa, no interna — nadie la practica voluntariamente si puede escapar de consecuencias. Opción B correcta.'},
    {p:'La medicina popular no representa un conocimiento válido porque no se fundamenta en pruebas científicas. Sin embargo, ambas medicinas pueden llegar a ser complementarias si se determinan cuáles prácticas son perjudiciales y cuáles brindan alternativas de salud.',q:'¿Qué función cumple el conector "Sin embargo" en el texto?',opts:['Introduce una conclusión lógica de lo dicho antes','Presenta una contraposición a la idea planteada','Agrega detalles sobre lo dicho anteriormente','Introduce una alternativa que matiza pero no niega lo anterior'],ans:3,exp:'"Sin embargo" introduce una idea que no invalida completamente lo anterior, sino que lo matiza: la medicina popular podría ser útil aunque no sea "válida" científicamente. La opción D describe mejor esta función adversativa-matizadora.'},
    {p:null,q:'En una caricatura, un político habla ante un micrófono con la nariz alargada mientras dice "Todo lo que prometí está cumplido". ¿Cuál es la intención comunicativa de la caricatura?',opts:['Celebrar los logros del político','Criticar la deshonestidad del discurso político','Invitar a la ciudadanía a participar más en política','Mostrar el orgullo del político por sus resultados'],ans:1,exp:'La nariz alargada es referencia directa a Pinocho, símbolo universal de la mentira. La caricatura usa la ironía para criticar el discurso falso del político. Opción B correcta.'},
    {p:'Un informe señala que el 68% de los colombianos no lee ningún libro al año fuera de obligaciones escolares. Los defensores del libro impreso argumentan que la digitalización es la causa. Sin embargo, países con alta digitalización como Finlandia presentan los índices de lectura más altos del mundo.',q:'La mención de Finlandia en el texto tiene como función principal:',opts:['Proponer un modelo que Colombia debería adoptar','Demostrar que la tecnología siempre mejora la lectura','Contradecir el argumento que atribuye la no-lectura a la digitalización','Comparar los sistemas educativos de ambos países'],ans:2,exp:'Finlandia funciona como contraejemplo: si la digitalización causara no-lectura, los países muy digitalizados leerían poco — pero ocurre lo contrario. Esto refuta el argumento de los defensores del libro impreso. Opción C correcta.'},
    {p:'La inteligencia artificial puede detectar ciertos tipos de cáncer con mayor precisión que los radiólogos en condiciones controladas. Sin embargo, estos sistemas fallan cuando se enfrentan a casos atípicos o imágenes de baja calidad, situaciones frecuentes en hospitales con recursos limitados.',q:'El autor adopta frente a la IA médica una postura:',opts:['Completamente favorable sin reservas','Completamente contraria advirtiendo sus riesgos','Matizada: reconoce ventajas pero señala limitaciones','Neutral: solo describe hechos sin emitir juicios'],ans:2,exp:'El texto primero destaca la ventaja (mayor precisión) y luego introduce una limitación con "sin embargo". Esto revela una postura equilibrada — ni totalmente a favor ni en contra. Opción C correcta.'},
    {p:'El arte no tiene por función reproducir lo ya visto. Su valor está en revelar lo que la mirada ordinaria no alcanza. Por eso la obra que simplemente agrada es inferior a aquella que incomoda, que desestabiliza, que obliga al espectador a preguntarse.',q:'Según el texto, una obra de arte valiosa es aquella que:',opts:['Reproduce fielmente la realidad visible','Genera placer estético en el espectador','Perturba al espectador y lo lleva a cuestionarse','Se distingue por su técnica y dominio formal'],ans:2,exp:'El texto dice explícitamente que la obra que "incomoda, desestabiliza, obliga a preguntarse" es superior a la que "simplemente agrada". Opción C recoge exactamente esa idea. Opción correcta C.'},
    {p:null,q:'¿Cuál de las siguientes opciones es un ejemplo de evaluación crítica (C3) en Lectura Crítica?',opts:['Identificar qué significa la palabra "ominoso" en el tercer párrafo','Reconocer que el texto tiene una estructura de tesis y argumentos','Determinar si los argumentos del autor son suficientes para apoyar su conclusión','Resumir en una frase la idea principal del texto'],ans:2,exp:'C3 implica evaluar la validez de los argumentos, detectar falacias o posiciones implícitas — no solo comprender. Las opciones A y D son C1. La opción B es C2. Solo la C implica evaluación crítica. Opción C correcta.'}
  ]},
  cn:{name:'Ciencias Naturales',color:'#f59e0b',qs:[
    {p:null,q:'Una célula somática humana tiene 46 cromosomas. ¿Cuántos cromosomas tendrá cada célula resultante tras completar la meiosis?',opts:['46 cromosomas','23 cromosomas','92 cromosomas','12 cromosomas'],ans:1,exp:'La meiosis reduce el número de cromosomas a la mitad para producir gametos. De una célula con 46 cromosomas resultan 4 células con 23 cromosomas cada una. Opción B correcta.'},
    {p:'Un estudiante mezcla HCl con NaOH en cantidades equimolares. La mezcla produce un compuesto cristalino blanco y agua.',q:'El compuesto cristalino blanco producido es:',opts:['Dióxido de cloro (ClO₂)','Cloruro de sodio (NaCl)','Hipoclorito de sodio (NaClO)','Óxido de sodio (Na₂O)'],ans:1,exp:'HCl + NaOH → NaCl + H₂O es una reacción de neutralización ácido-base clásica. El producto es cloruro de sodio (sal de mesa) y agua. Opción B correcta.'},
    {p:'En un experimento, al aumentar 10°C la temperatura, la velocidad de reacción se duplica.',q:'Si a 20°C la velocidad es 4 mol/s, ¿cuál será a 40°C?',opts:['8 mol/s','12 mol/s','16 mol/s','32 mol/s'],ans:2,exp:'Cada 10°C la velocidad se duplica. De 20°C a 40°C hay 2 incrementos. Entonces: 4 × 2 × 2 = 16 mol/s. Opción C correcta.'},
    {p:null,q:'¿En qué fase de la fotosíntesis se producen el ATP y el NADPH que luego se usan en el ciclo de Calvin?',opts:['En las reacciones oscuras usando CO₂','En las reacciones luminosas usando energía solar','En la respiración celular usando glucosa','En la fase de elongación del ciclo de Calvin'],ans:1,exp:'Las reacciones luminosas capturan energía solar en los tilacoides para producir ATP y NADPH. Estas moléculas luego impulsan el ciclo de Calvin (fase oscura) donde se fija el CO₂. Opción B correcta.'},
    {p:'Una gráfica muestra que al aumentar la concentración de sustrato, la velocidad de una reacción enzimática aumenta hasta un punto máximo donde se estabiliza.',q:'El punto de estabilización de la velocidad indica que:',opts:['La enzima se ha desnaturalizado por exceso de sustrato','Todos los sitios activos de la enzima están ocupados (saturación)','El producto empieza a inhibir la reacción','La temperatura óptima de la enzima fue superada'],ans:1,exp:'Cuando todos los sitios activos de la enzima están ocupados, agregar más sustrato no aumenta la velocidad — la enzima está saturada. Esto se llama velocidad máxima (Vmax). Opción B correcta.'},
    {p:null,q:'Un objeto de 5 kg se eleva 3 metros verticalmente. ¿Cuánto trabajo realizó la fuerza aplicada? (g = 10 m/s²)',opts:['15 J','50 J','150 J','500 J'],ans:2,exp:'Trabajo = Fuerza × distancia. Fuerza = masa × g = 5 × 10 = 50 N. Trabajo = 50 N × 3 m = 150 J. Opción C correcta.'}
  ]},
  mat:{name:'Matemáticas',color:'#10b981',qs:[
    {p:null,q:'Si f(x) = 2x² - 3x + 1, ¿cuál es el valor de f(3)?',opts:['8','10','12','16'],ans:1,exp:'f(3) = 2(9) - 3(3) + 1 = 18 - 9 + 1 = 10. Opción B correcta.'},
    {p:null,q:'En una bolsa hay 5 bolas rojas, 3 azules y 2 verdes. ¿Cuál es la probabilidad de sacar una azul?',opts:['1/5','3/10','1/3','3/5'],ans:1,exp:'Total = 10 bolas. P(azul) = 3/10. Opción B correcta.'},
    {p:null,q:'La ecuación de la recta que pasa por (0, 3) y (2, 7) es:',opts:['y = x + 3','y = 2x + 3','y = 3x + 2','y = 2x + 1'],ans:1,exp:'Pendiente = (7−3)/(2−0) = 2. Con punto (0,3): y = 2x + 3. Opción B correcta.'},
    {p:'Una empresa produce 480 unidades en 8 horas con 6 trabajadores.',q:'¿Cuántas unidades producirán 9 trabajadores en 6 horas al mismo ritmo?',opts:['480 unidades','540 unidades','600 unidades','720 unidades'],ans:1,exp:'Ritmo: 480/(8×6)=10 unid/trabajador/hora. Con 9 trabajadores × 6 horas × 10 = 540 unidades. Opción B correcta.'},
    {p:null,q:'Si log₂(x) = 5, ¿cuál es el valor de x?',opts:['10','25','32','64'],ans:2,exp:'log₂(x)=5 significa 2⁵=x. 2⁵=32. Opción C correcta.'},
    {p:null,q:'¿Cuánto es el 30% de 250?',opts:['55','65','75','85'],ans:2,exp:'30% de 250 = 0.30 × 250 = 75. Opción C correcta.'}
  ]},
  soc:{name:'Sociales y Ciudadanas',color:'#7c3aed',qs:[
    {p:null,q:'Según el artículo 1 de la Constitución de 1991, Colombia es:',opts:['Una monarquía constitucional pluralista','Un Estado social de derecho, democrático, participativo y pluralista','Una república federal con autonomía plena de sus departamentos','Un Estado laico y centralista con economía de libre mercado'],ans:1,exp:'El artículo 1 define a Colombia como "un Estado social de derecho, organizado en forma de república unitaria, descentralizada, con autonomía de sus entidades territoriales, democrática, participativa y pluralista." Opción B correcta.'},
    {p:null,q:'El mecanismo que permite a los ciudadanos destituir a un alcalde o gobernador antes de terminar su período es:',opts:['El referendo','El plebiscito','La revocatoria del mandato','La iniciativa legislativa popular'],ans:2,exp:'La revocatoria del mandato (Art. 103) permite a los ciudadanos destituir alcaldes o gobernadores cuando han incumplido su programa de gobierno. Opción C correcta.'},
    {p:'Una multinacional instala una fábrica en un país en desarrollo, genera empleos locales pero repatría el 90% de sus ganancias y usa materias primas locales a precios bajos.',q:'Esta situación ilustra principalmente:',opts:['Los beneficios del libre mercado global','La dependencia del capital extranjero como crítica a la globalización asimétrica','Las ventajas del proteccionismo económico','Los principios del desarrollo sostenible'],ans:1,exp:'El país receptor recibe empleo pero no retiene la riqueza generada. Esto describe la dependencia económica y las críticas a la globalización asimétrica. Opción B correcta.'},
    {p:null,q:'La "División de poderes" de Montesquieu buscaba principalmente:',opts:['Concentrar el poder en un monarca ilustrado','Dividir el territorio en unidades iguales','Evitar la concentración del poder y garantizar la libertad ciudadana','Crear tres partidos políticos representando cada poder'],ans:2,exp:'Montesquieu propuso separar el poder en legislativo, ejecutivo y judicial para que ninguno tenga poder absoluto y se proteja la libertad individual frente a la tiranía. Opción C correcta.'},
    {p:null,q:'¿Cuál fue el principal factor estructural de la Primera Guerra Mundial?',opts:['El asesinato del archiduque Francisco Fernando en Sarajevo','La rivalidad imperialista entre potencias europeas por colonias y mercados','La crisis del mercado de valores de Nueva York en 1913','El bloqueo comercial de Estados Unidos a Europa'],ans:1,exp:'El asesinato del archiduque fue el detonante inmediato, pero las causas profundas fueron la rivalidad imperialista, la carrera armamentista y el sistema de alianzas entre potencias que competían por recursos y territorios. Opción B correcta.'},
    {p:null,q:'La "gentrificación" en ciudades latinoamericanas se refiere a:',opts:['El crecimiento de zonas rurales cercanas a ciudades','La renovación urbana de barrios populares que eleva costos y desplaza a sus residentes originales','La migración masiva de ciudadanos hacia países desarrollados','La creación de zonas francas industriales en periferias urbanas'],ans:1,exp:'La gentrificación ocurre cuando la renovación de un barrio popular atrae residentes de mayor poder adquisitivo, sube los precios y desplaza a quienes vivían históricamente allí. Opción B correcta.'}
  ]},
  ing:{name:'Inglés',color:'#00e5ff',qs:[
    {p:'Scientists have discovered that trees communicate through an underground network of fungi called the "wood wide web." This allows trees to share nutrients and warning signals. Older trees, called "mother trees," support younger seedlings with carbon and water.',q:'What is the main idea of this passage?',opts:['Trees compete for underground nutrients','Fungi destroy tree roots in forests','Trees communicate and cooperate through fungal networks','Only mother trees benefit from the wood wide web'],ans:2,exp:'The passage describes how trees communicate and share resources through fungal networks. The central idea is cooperation — not competition or destruction. Option C is correct.'},
    {p:null,q:'Choose the correct sentence:',opts:["She don't know the answer","She doesn't knows the answer","She doesn't know the answer","She not know the answer"],ans:2,exp:'With third person singular (she/he/it): "doesn\'t" + base verb. "She doesn\'t know" is grammatically correct. Options A and D lack proper auxiliary; B incorrectly adds -s after doesn\'t. Option C is correct.'},
    {p:'Despite the heavy rain, the match continued. Players were exhausted, but neither team wanted to give up. In the final minute, the home team scored an unexpected goal, causing the crowd to erupt in celebration.',q:'Why did the crowd celebrate?',opts:['Because the rain finally stopped','Because the visiting team scored a brilliant goal','Because the home team scored at the last minute','Because both teams agreed to draw'],ans:2,exp:'The text states "the home team scored an unexpected goal" in the final minute, causing the celebration. Option C directly matches this information.'},
    {p:null,q:'Select the option that correctly completes: "By the time she arrived, her friends _____ for two hours."',opts:['were waiting','had been waiting','have waited','will have waited'],ans:1,exp:'"By the time + past simple" requires Past Perfect Continuous to show an ongoing action that preceded another past event. "Had been waiting" is correct. Option B is correct.'},
    {p:'Climate change is one of the most pressing challenges of our time. Rising temperatures are melting polar ice caps, causing sea levels to rise. Experts argue that immediate action is needed before the damage becomes irreversible.',q:'What does "irreversible" most likely mean?',opts:['Easily fixed with technology','Impossible to undo or reverse','Happening gradually over centuries','Affecting only certain regions'],ans:1,exp:'"Irreversible" = impossible to undo. In context, it refers to climate damage that would be permanent if not addressed. Option B is correct.'}
  ]}
};

let currentArea=null,curQs=[],curIdx=0,qScore=0,qAnswered=false;
function selArea(a){
  currentArea=a;
  document.querySelectorAll('.qa-btn').forEach(b=>b.classList.remove('sel'));
  document.getElementById('qbtn-'+a).classList.add('sel');
  const btn=document.getElementById('start-btn');
  btn.disabled=false;
  btn.textContent='Iniciar quiz de '+QD[a].name;
}
function startQuiz(){
  if(!currentArea)return;
  curQs=[...QD[currentArea].qs];
  curIdx=0;qScore=0;qAnswered=false;
  document.getElementById('quiz-sel-section').style.display='none';
  document.getElementById('quiz-container').style.display='block';
  document.getElementById('quiz-results').style.display='none';
  document.getElementById('quiz-card').style.display='block';
  loadQ();
}
function loadQ(){
  qAnswered=false;
  const q=curQs[curIdx];
  const tot=curQs.length;
  document.getElementById('qpfill').style.width=((curIdx/tot)*100)+'%';
  document.getElementById('q-counter').textContent=(curIdx+1)+' / '+tot;
  const badge=document.getElementById('q-badge');
  badge.textContent=QD[currentArea].name;
  badge.style.background=QD[currentArea].color+'22';
  badge.style.color=QD[currentArea].color;
  badge.style.border='1px solid '+QD[currentArea].color+'44';
  const pe=document.getElementById('q-passage');
  if(q.p){pe.style.display='block';pe.textContent=q.p;}else{pe.style.display='none';}
  document.getElementById('q-question').textContent=q.q;
  const oe=document.getElementById('q-options');
  oe.innerHTML='';
  ['A','B','C','D'].forEach((l,i)=>{
    if(i>=q.opts.length)return;
    const btn=document.createElement('button');
    btn.className='q-opt';
    btn.innerHTML=`<span class="opt-letter">${l}</span><span>${q.opts[i]}</span>`;
    btn.onclick=()=>answerQ(i,q.ans,q.exp);
    oe.appendChild(btn);
  });
  document.getElementById('q-feedback').style.display='none';
  document.getElementById('next-btn').style.display='none';
}
function answerQ(chosen,correct,exp){
  if(qAnswered)return;
  qAnswered=true;
  const opts=document.querySelectorAll('.q-opt');
  opts.forEach(b=>b.disabled=true);
  if(chosen===correct){opts[chosen].classList.add('correct');qScore++;const fb=document.getElementById('q-feedback');fb.className='q-feedback correct';fb.textContent='✅ ¡Correcto! '+exp;fb.style.display='block';}
  else{opts[chosen].classList.add('incorrect');opts[correct].classList.add('correct');const fb=document.getElementById('q-feedback');fb.className='q-feedback incorrect';fb.textContent='❌ Incorrecto. '+exp;fb.style.display='block';}
  const nb=document.getElementById('next-btn');
  nb.style.display='inline-block';
  nb.textContent=curIdx+1<curQs.length?'Siguiente →':'Ver resultados →';
}
function nextQ(){
  curIdx++;
  if(curIdx<curQs.length)loadQ();
  else showResults();
}
function showResults(){
  document.getElementById('quiz-card').style.display='none';
  const re=document.getElementById('quiz-results');
  re.style.display='block';
  const pct=Math.round((qScore/curQs.length)*100);
  const se=document.getElementById('res-score');
  se.textContent=pct+'%';
  se.style.color=pct>=80?'var(--green)':pct>=60?'var(--yellow)':'var(--red)';
  let label=pct>=80?`🏆 Excelente — ${qScore}/${curQs.length} correctas. ¡Sigue así!`:pct>=60?`💪 Bien — ${qScore}/${curQs.length} correctas. Repasa los temas del plan.`:`📚 A reforzar — ${qScore}/${curQs.length} correctas. Revisa la clase de este área.`;
  document.getElementById('res-label').textContent=label;
}
function resetQuiz(){
  document.getElementById('quiz-container').style.display='none';
  document.getElementById('quiz-sel-section').style.display='block';
  document.querySelectorAll('.qa-btn').forEach(b=>b.classList.remove('sel'));
  document.getElementById('start-btn').disabled=true;
  document.getElementById('start-btn').textContent='Selecciona un área para empezar';
  currentArea=null;
  document.getElementById('quiz-card').style.display='block';
}

// ── INIT ──
updateUI();
</script>
</body>
</html>
