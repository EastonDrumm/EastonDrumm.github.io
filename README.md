/*But*/
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Easton Drummonds | Engineer & Data Analyst</title>
<link href="https://fonts.googleapis.com/css2?family=Space+Mono:wght@400;700&family=Outfit:wght@300;400;500;600;700;800;900&family=JetBrains+Mono:wght@300;400;500;700&display=swap" rel="stylesheet">
<style>
*,*::before,*::after{margin:0;padding:0;box-sizing:border-box}
:root{
  --bg:#f8f9fc;--bg2:#ffffff;--bg3:#eef1f6;--surface:#ffffff;--surface2:#f2f4f8;
  --border:#dde2ed;--border2:#c8cede;
  --b400:#3366ff;--b500:#2855ee;--b300:#5588ff;--b200:#4070dd;--b100:#2050bb;
  --b600:#1a3fcc;--bglow:rgba(51,102,255,.1);--bglow2:rgba(51,102,255,.04);
  --text:#1a1f2e;--text2:#4a5270;--text3:#7080a0;--text4:#98a4b8;
  --accent:#3366ff;--accent2:#5588ff;--green:#22a838;
}
html{scroll-behavior:smooth;overflow-x:hidden;scrollbar-width:thin;scrollbar-color:var(--border) var(--bg)}
body{font-family:'Outfit',sans-serif;background:var(--bg);color:var(--text);overflow-x:hidden;line-height:1.6}

/* Particle canvas */
#particle-canvas{position:fixed;top:0;left:0;width:100%;height:100%;z-index:0;pointer-events:none;opacity:.4}
body::after{content:'';position:fixed;inset:0;pointer-events:none;z-index:9998;
  background:repeating-linear-gradient(0deg,transparent,transparent 2px,rgba(0,0,0,.006) 2px,rgba(0,0,0,.006) 4px);opacity:.25}

nav{position:fixed;top:0;left:0;right:0;z-index:1000;padding:.9rem 4rem;display:flex;justify-content:space-between;align-items:center;
  backdrop-filter:blur(20px);background:rgba(248,249,252,.88);border-bottom:1px solid var(--border)}
.nav-name{font-family:'Space Mono',monospace;font-size:1.05rem;font-weight:700}.nav-name span{color:var(--accent)}
.nav-links{display:flex;gap:2rem;list-style:none}
.nav-links a{font-family:'JetBrains Mono',monospace;color:var(--text3);text-decoration:none;font-size:.68rem;font-weight:500;
  letter-spacing:.08em;text-transform:uppercase;transition:color .3s;position:relative}
.nav-links a:hover,.nav-links a.act{color:var(--accent)}
.nav-links a.act::after{content:'';position:absolute;bottom:-6px;left:0;right:0;height:2px;background:var(--accent);border-radius:1px}

/* ============ HERO ============ */
.hero{min-height:100vh;display:flex;align-items:center;padding:0 4rem;position:relative;z-index:1}
.hero-grid{display:grid;grid-template-columns:1fr 1fr;gap:3.5rem;align-items:center;max-width:1200px;margin:0 auto;width:100%}
.hero-label{font-family:'JetBrains Mono',monospace;font-size:.68rem;color:var(--text3);letter-spacing:.15em;text-transform:uppercase;margin-bottom:.7rem;
  display:flex;align-items:center;gap:.6rem}
.hero-label::before{content:'';width:20px;height:1px;background:var(--accent)}
.hero-hello{font-family:'Space Mono',monospace;font-size:clamp(2.2rem,4.5vw,3.6rem);font-weight:700;line-height:1.1;margin-bottom:.2rem}
.hero-name-big{font-family:'Space Mono',monospace;font-size:clamp(2.2rem,4.5vw,3.6rem);font-weight:700;line-height:1.1;color:var(--accent);margin-bottom:1.3rem}
.hero-desc{font-family:'JetBrains Mono',monospace;font-size:.76rem;color:var(--text3);line-height:1.8;margin-bottom:1.8rem;max-width:460px}
.hero-desc span{color:var(--b200)}
.hero-actions{display:flex;gap:1rem;align-items:center;flex-wrap:wrap}
.btn-cv{font-family:'JetBrains Mono',monospace;padding:.65rem 1.6rem;font-size:.7rem;font-weight:700;letter-spacing:.1em;text-transform:uppercase;
  border:2px solid var(--accent);background:transparent;color:var(--accent);border-radius:6px;cursor:pointer;transition:all .3s;text-decoration:none}
.btn-cv:hover{background:var(--accent);color:var(--bg);box-shadow:0 0 30px var(--bglow)}
.social-row{display:flex;gap:.5rem}
.social-icon{width:34px;height:34px;border-radius:50%;border:1.5px solid var(--border);display:flex;align-items:center;justify-content:center;
  color:var(--text3);transition:all .3s;cursor:pointer;text-decoration:none}
.social-icon:hover{border-color:var(--accent);color:var(--accent);box-shadow:0 0 12px var(--bglow)}
.social-icon svg{width:15px;height:15px}
.hero-visual{display:flex;align-items:center;justify-content:center;position:relative}
.circle-frame{width:340px;height:340px;border-radius:50%;position:relative;display:flex;align-items:center;justify-content:center}
.circle-dashed{position:absolute;inset:-12px;border:2px dashed var(--accent);border-radius:50%;animation:rot 20s linear infinite;opacity:.5}
@keyframes rot{to{transform:rotate(360deg)}}
.circle-solid{position:absolute;inset:0;border:2px solid var(--accent);border-radius:50%;opacity:.25}
.circle-inner{width:100%;height:100%;border-radius:50%;overflow:hidden;background:var(--surface);
  display:flex;align-items:center;justify-content:center;position:relative;flex-direction:column}
.circle-inner .initials{font-family:'Space Mono',monospace;font-size:4rem;font-weight:700;color:var(--accent);opacity:.1;position:absolute}
.circle-inner .tagline{font-family:'JetBrains Mono',monospace;font-size:.6rem;color:var(--accent);text-align:center;
  position:relative;z-index:1;letter-spacing:.06em;text-transform:uppercase;padding:0 2.5rem;line-height:1.6}
.cdot{position:absolute;width:9px;height:9px;background:var(--accent);border-radius:50%;box-shadow:0 0 10px var(--bglow)}
.cdot:nth-child(1){top:-5px;left:50%;transform:translateX(-50%)}.cdot:nth-child(2){bottom:-5px;left:50%;transform:translateX(-50%)}
.cdot:nth-child(3){left:-5px;top:50%;transform:translateY(-50%)}.cdot:nth-child(4){right:-5px;top:50%;transform:translateY(-50%)}
.hero-brackets{position:absolute;width:380px;height:380px;top:50%;left:50%;transform:translate(-50%,-50%)}
.hb{position:absolute;width:28px;height:28px;border-color:var(--accent);border-style:solid;opacity:.2}
.hb-tl{top:0;left:0;border-width:2px 0 0 2px}.hb-tr{top:0;right:0;border-width:2px 2px 0 0}
.hb-bl{bottom:0;left:0;border-width:0 0 2px 2px}.hb-br{bottom:0;right:0;border-width:0 2px 2px 0}

/* Stats bar */
.stats-bar{max-width:1200px;margin:0 auto;padding:0 4rem;position:relative;z-index:1}
.stats-row{display:flex;justify-content:space-between;padding:2.2rem 0;border-top:1px solid var(--border);border-bottom:1px solid var(--border)}
.stat-item{display:flex;align-items:baseline;gap:.7rem}
.stat-num{font-family:'Space Mono',monospace;font-size:clamp(2.2rem,3.5vw,3.2rem);font-weight:700;line-height:1}
.stat-num .stat-plus{font-size:.6em;color:var(--accent)}
.stat-label{font-family:'JetBrains Mono',monospace;font-size:.64rem;color:var(--text3);text-transform:uppercase;letter-spacing:.05em;line-height:1.4}

/* ============ SECTIONS ============ */
.section{padding:5rem 4rem;max-width:1200px;margin:0 auto;position:relative;z-index:1}
.sec-header{display:flex;align-items:center;gap:1rem;margin-bottom:2.5rem}
.sec-num{font-family:'JetBrains Mono',monospace;font-size:.65rem;color:var(--accent);font-weight:700;letter-spacing:.1em}
.sec-line{width:35px;height:1px;background:var(--accent)}
.sec-title{font-family:'Space Mono',monospace;font-size:1.4rem;font-weight:700}
.sr{opacity:0;transform:translateY(25px);transition:all .7s cubic-bezier(.23,1,.32,1)}
.sr.vis{opacity:1;transform:translateY(0)}

/* ============ LIVE STATUS WIDGET ============ */
.live-widget{background:var(--surface);border:1px solid var(--border);border-radius:14px;padding:1.5rem 2rem;margin-bottom:3rem;
  display:grid;grid-template-columns:auto 1fr auto;gap:1.5rem;align-items:center;position:relative;overflow:hidden}
.live-widget::before{content:'';position:absolute;top:0;left:0;right:0;height:3px;background:linear-gradient(90deg,var(--green),var(--accent))}
.lw-status{display:flex;flex-direction:column;align-items:center;gap:.3rem}
.lw-dot{width:12px;height:12px;border-radius:50%;background:var(--green);box-shadow:0 0 12px rgba(40,200,64,.5);animation:pulse 2s infinite}
@keyframes pulse{0%,100%{box-shadow:0 0 12px rgba(40,200,64,.4)}50%{box-shadow:0 0 24px rgba(40,200,64,.6)}}
.lw-label{font-family:'JetBrains Mono',monospace;font-size:.5rem;color:var(--green);text-transform:uppercase;letter-spacing:.08em}
.lw-info h4{font-family:'Space Mono',monospace;font-size:.95rem;font-weight:700;margin-bottom:.2rem}
.lw-info p{font-family:'JetBrains Mono',monospace;font-size:.7rem;color:var(--text3);line-height:1.5}
.lw-progress{display:flex;flex-direction:column;align-items:flex-end;gap:.4rem;min-width:120px}
.lw-bar{width:120px;height:6px;background:var(--surface2);border-radius:3px;overflow:hidden}
.lw-fill{height:100%;background:linear-gradient(90deg,var(--accent),var(--green));border-radius:3px;width:72%;
  animation:progressPulse 3s ease-in-out infinite}
@keyframes progressPulse{0%,100%{opacity:.8}50%{opacity:1}}
.lw-pct{font-family:'JetBrains Mono',monospace;font-size:.6rem;color:var(--accent)}

/* ============ TERMINAL ============ */
.terminal{background:var(--bg3);border:1px solid var(--border);border-radius:12px;overflow:hidden;margin-bottom:3rem;
  transition:all .4s cubic-bezier(.23,1,.32,1)}
.terminal.minimized .terminal-body{max-height:0;padding:0 1.3rem;overflow:hidden}
.terminal.minimized{margin-bottom:1rem}
.terminal.fullscreen{position:fixed;inset:3rem 2rem 2rem;z-index:9990;border-radius:12px;margin:0;
  box-shadow:0 30px 100px rgba(0,0,0,.6)}
.terminal.fullscreen .terminal-body{min-height:auto;max-height:calc(100% - 40px);overflow-y:auto}
.terminal.closed{max-height:0;overflow:hidden;border:none;margin:0;padding:0;opacity:0}
.terminal-bar{display:flex;align-items:center;gap:.5rem;padding:.6rem 1rem;background:var(--surface2);border-bottom:1px solid var(--border)}
.tdot{width:9px;height:9px;border-radius:50%;cursor:pointer;transition:all .2s;border:none;padding:0;position:relative}
.tdot:hover{transform:scale(1.3);box-shadow:0 0 8px currentColor}
.tdot-r{background:#ff5f57;color:#ff5f57}.tdot-y{background:#ffbd2e;color:#ffbd2e}.tdot-g{background:#28c840;color:#28c840}
.tdot::after{content:'';position:absolute;inset:-4px;border-radius:50%} /* bigger hit area */
.tdot-label{position:absolute;bottom:calc(100% + 8px);left:50%;transform:translateX(-50%);
  font-family:'JetBrains Mono',monospace;font-size:.5rem;color:var(--text3);white-space:nowrap;
  background:var(--bg);border:1px solid var(--border);padding:.2rem .5rem;border-radius:4px;
  opacity:0;pointer-events:none;transition:opacity .15s;z-index:2}
.tdot:hover .tdot-label{opacity:1}
.terminal-title{font-family:'JetBrains Mono',monospace;font-size:.55rem;color:var(--text4);margin-left:.8rem}
.terminal-body{padding:1rem 1.3rem;font-family:'JetBrains Mono',monospace;font-size:.7rem;line-height:1.9;color:var(--text2);min-height:160px}
.t-line{opacity:0;animation:typeLine .3s forwards}
.t-prompt{color:var(--accent)}.t-cmd{color:var(--text)}.t-out{color:var(--text3)}.t-hl{color:var(--b200)}
.cursor-blink{display:inline-block;width:7px;height:13px;background:var(--accent);animation:blink 1s step-end infinite;vertical-align:middle;margin-left:2px}
@keyframes blink{50%{opacity:0}}
@keyframes typeLine{to{opacity:1}}

/* ============ ENGINEERING PROCESS FLOWCHART ============ */
.flowchart{display:flex;align-items:center;justify-content:center;gap:0;margin:2.5rem 0;flex-wrap:wrap}
.flow-step{display:flex;flex-direction:column;align-items:center;gap:.5rem;padding:1.2rem 1rem;
  background:var(--surface);border:1px solid var(--border);border-radius:12px;width:140px;
  transition:all .4s;position:relative;opacity:0;transform:translateY(15px)}
.flow-step.vis{opacity:1;transform:translateY(0)}
.flow-step:hover{border-color:var(--accent);transform:translateY(-3px)!important;box-shadow:0 8px 25px rgba(0,0,50,.3)}
.flow-step.active{border-color:var(--accent);box-shadow:0 0 20px var(--bglow)}
.flow-icon{font-size:1.5rem}
.flow-label{font-family:'JetBrains Mono',monospace;font-size:.6rem;color:var(--text);text-align:center;font-weight:500;letter-spacing:.03em}
.flow-sub{font-family:'JetBrains Mono',monospace;font-size:.48rem;color:var(--text4);text-align:center}
.flow-arrow{font-family:'JetBrains Mono',monospace;font-size:1rem;color:var(--accent);margin:0 .3rem;opacity:0;transform:translateX(-5px);transition:all .3s}
.flow-arrow.vis{opacity:.6;transform:translateX(0)}

/* ============ BUILD ACTIVITY HEATMAP ============ */
.heatmap-section{margin:2.5rem 0}
.heatmap-title{font-family:'JetBrains Mono',monospace;font-size:.65rem;color:var(--text3);text-transform:uppercase;letter-spacing:.1em;margin-bottom:1rem;
  display:flex;align-items:center;gap:.8rem}
.heatmap-title::after{content:'';flex:1;height:1px;background:var(--border)}
.heatmap{display:flex;gap:3px;flex-wrap:nowrap;max-width:100%;justify-content:center}
.hm-col{display:flex;flex-direction:column;gap:3px}
.hm-cell{width:12px;height:12px;border-radius:2px;background:var(--surface2);border:1px solid var(--border);transition:all .3s;cursor:default;position:relative}
.hm-cell[data-level="1"]{background:rgba(51,102,255,.15);border-color:rgba(51,102,255,.2)}
.hm-cell[data-level="2"]{background:rgba(51,102,255,.3);border-color:rgba(51,102,255,.35)}
.hm-cell[data-level="3"]{background:rgba(51,102,255,.5);border-color:rgba(51,102,255,.55)}
.hm-cell[data-level="4"]{background:rgba(51,102,255,.75);border-color:rgba(51,102,255,.8)}
.hm-cell:hover{transform:scale(1.4);z-index:2;box-shadow:0 0 8px var(--bglow)}
.hm-legend{display:flex;align-items:center;gap:.5rem;margin-top:.8rem;justify-content:center}
.hm-legend span{font-family:'JetBrains Mono',monospace;font-size:.5rem;color:var(--text4)}

/* ============ SKILLS RADAR CHART ============ */
.radar-wrapper{display:grid;grid-template-columns:1fr 1fr;gap:3rem;align-items:start}
.radar-container{display:flex;align-items:center;justify-content:center;padding:1rem}
#radarCanvas{max-width:100%}
.skill-list-col h3{font-family:'JetBrains Mono',monospace;font-size:.65rem;color:var(--accent);text-transform:uppercase;letter-spacing:.12em;margin-bottom:1.3rem;font-weight:500}
.skill-item{margin-bottom:1rem}
.skill-header{display:flex;justify-content:space-between;align-items:center;margin-bottom:.35rem}
.skill-name{font-family:'JetBrains Mono',monospace;font-size:.7rem;color:var(--text2)}
.skill-pct{font-family:'JetBrains Mono',monospace;font-size:.6rem;color:var(--text4)}
.skill-bar{height:3px;background:var(--surface2);border-radius:2px;overflow:hidden}
.skill-fill{height:100%;background:linear-gradient(90deg,var(--accent),var(--b300));border-radius:2px;width:0;transition:width 1.2s cubic-bezier(.23,1,.32,1)}
.skill-fill.anim{width:var(--w)}

/* ============ TIMELINE ============ */
.timeline{position:relative;padding:0 0 0 3rem}
.timeline::before{content:'';position:absolute;left:11px;top:0;bottom:0;width:2px;background:linear-gradient(180deg,var(--accent),var(--border) 50%,transparent)}
.tl-item{position:relative;margin-bottom:2.2rem;padding-left:2rem}
.tl-dot{position:absolute;left:-3rem;top:.3rem;width:22px;height:22px;border-radius:50%;
  border:2px solid var(--border);background:var(--bg);display:flex;align-items:center;justify-content:center;transition:all .4s;z-index:2}
.tl-dot::after{content:'';width:7px;height:7px;border-radius:50%;background:var(--border);transition:all .4s}
.tl-item.active .tl-dot{border-color:var(--accent);box-shadow:0 0 12px var(--bglow)}
.tl-item.active .tl-dot::after{background:var(--accent)}
.tl-date{font-family:'JetBrains Mono',monospace;font-size:.58rem;color:var(--accent);letter-spacing:.1em;text-transform:uppercase;margin-bottom:.2rem}
.tl-title{font-family:'Space Mono',monospace;font-size:.9rem;font-weight:700;margin-bottom:.3rem}
.tl-desc{font-size:.8rem;color:var(--text3);line-height:1.7}
.tl-tags{display:flex;flex-wrap:wrap;gap:.25rem;margin-top:.4rem}
.tl-tag{font-family:'JetBrains Mono',monospace;font-size:.5rem;padding:.15rem .4rem;background:var(--bglow2);border:1px solid rgba(51,102,255,.15);border-radius:3px;color:var(--b200)}

/* ============ PROJECTS ============ */
.proj-grid{display:grid;grid-template-columns:1fr 1fr;gap:1.3rem}
.proj{background:var(--surface);border:1px solid var(--border);border-radius:14px;padding:1.8rem;position:relative;overflow:hidden;transition:all .4s;cursor:pointer}
.proj::before{content:'';position:absolute;top:0;left:0;right:0;height:3px;background:linear-gradient(90deg,var(--accent),var(--b300));transform:scaleX(0);transform-origin:left;transition:transform .4s}
.proj:hover{border-color:var(--accent);transform:translateY(-3px);box-shadow:0 12px 40px rgba(0,0,50,.3)}
.proj:hover::before{transform:scaleX(1)}
.proj-num{font-family:'JetBrains Mono',monospace;font-size:.5rem;color:var(--text4);letter-spacing:.1em;margin-bottom:.7rem}
.proj-type{font-family:'JetBrains Mono',monospace;font-size:.5rem;color:var(--accent);text-transform:uppercase;letter-spacing:.12em;margin-bottom:.4rem;font-weight:500}
.proj h3{font-family:'Space Mono',monospace;font-size:1.05rem;font-weight:700;margin-bottom:.4rem}
.proj p{color:var(--text3);font-size:.8rem;line-height:1.7;margin-bottom:.8rem}
.tr{display:flex;flex-wrap:wrap;gap:.25rem}
.tt{font-family:'JetBrains Mono',monospace;font-size:.5rem;padding:.15rem .4rem;background:var(--bglow2);border:1px solid rgba(51,102,255,.12);border-radius:3px;color:var(--b200)}
.proj-status{display:flex;align-items:center;gap:.35rem;margin-top:.7rem}
.status-dot{width:6px;height:6px;border-radius:50%}
.status-dot.live{background:var(--green);box-shadow:0 0 6px rgba(40,200,64,.4)}
.status-dot.done{background:var(--accent);box-shadow:0 0 6px var(--bglow)}
.status-text{font-family:'JetBrains Mono',monospace;font-size:.5rem;color:var(--text4);text-transform:uppercase;letter-spacing:.06em}
.proj-expand{font-family:'JetBrains Mono',monospace;font-size:.55rem;color:var(--accent);margin-top:.7rem;display:flex;align-items:center;gap:.3rem;letter-spacing:.06em;text-transform:uppercase}
.proj-expand::after{content:'>';transition:transform .3s}
.proj:hover .proj-expand::after{transform:translateX(4px)}

/* ============ IMPACT METRICS ============ */
.impact-grid{display:grid;grid-template-columns:repeat(4,1fr);gap:1rem;margin:2.5rem 0}
.impact-card{background:var(--surface);border:1px solid var(--border);border-radius:12px;padding:1.5rem;text-align:center;transition:all .3s;position:relative;overflow:hidden}
.impact-card::after{content:'';position:absolute;bottom:0;left:0;right:0;height:2px;background:var(--accent);transform:scaleX(0);transition:transform .4s}
.impact-card:hover{border-color:var(--accent);transform:translateY(-2px)}.impact-card:hover::after{transform:scaleX(1)}
.impact-val{font-family:'Space Mono',monospace;font-size:1.8rem;font-weight:700;color:var(--accent);margin-bottom:.2rem}
.impact-label{font-family:'JetBrains Mono',monospace;font-size:.55rem;color:var(--text3);text-transform:uppercase;letter-spacing:.08em;line-height:1.4}
.impact-detail{font-family:'JetBrains Mono',monospace;font-size:.5rem;color:var(--text4);margin-top:.3rem}

/* ============ PROJECT MODAL ============ */
.modal-overlay{position:fixed;inset:0;background:rgba(20,25,40,.55);backdrop-filter:blur(12px);z-index:9999;
  display:flex;align-items:center;justify-content:center;opacity:0;pointer-events:none;transition:opacity .3s;padding:2rem}
.modal-overlay.open{opacity:1;pointer-events:auto}
.modal{background:var(--bg2);border:1px solid var(--border);border-radius:16px;max-width:880px;width:100%;max-height:85vh;overflow-y:auto;
  position:relative;transform:translateY(20px) scale(.97);transition:transform .35s;scrollbar-width:thin;scrollbar-color:var(--border) transparent}
.modal-overlay.open .modal{transform:translateY(0) scale(1)}
.modal::before{content:'';position:absolute;top:0;left:0;right:0;height:4px;background:linear-gradient(90deg,var(--accent),var(--b300))}
.modal-close{position:absolute;top:1rem;right:1rem;width:34px;height:34px;border-radius:50%;border:1.5px solid var(--border);
  background:var(--bg);color:var(--text3);display:flex;align-items:center;justify-content:center;cursor:pointer;
  font-family:'JetBrains Mono',monospace;font-size:.95rem;transition:all .3s;z-index:2}
.modal-close:hover{border-color:var(--accent);color:var(--accent)}
.modal-header{padding:2.2rem 2.2rem 0;display:flex;gap:1.5rem;align-items:flex-start}
.modal-badge{width:55px;height:55px;border-radius:12px;background:var(--bglow2);border:1px solid rgba(51,102,255,.15);
  display:flex;align-items:center;justify-content:center;font-size:1.6rem;flex-shrink:0}
.modal-meta{flex:1}
.modal-meta .proj-type{margin-bottom:.2rem}
.modal-meta h2{font-family:'Space Mono',monospace;font-size:1.35rem;font-weight:700;margin-bottom:.2rem}
.modal-meta .modal-sub{font-family:'JetBrains Mono',monospace;font-size:.62rem;color:var(--text3);line-height:1.5}
.modal-body{padding:1.8rem 2.2rem 2.2rem}
.modal-section{margin-bottom:1.8rem}
.modal-section h3{font-family:'JetBrains Mono',monospace;font-size:.65rem;color:var(--accent);text-transform:uppercase;letter-spacing:.12em;
  margin-bottom:.8rem;padding-bottom:.4rem;border-bottom:1px solid var(--border);font-weight:500}
.modal-section p{color:var(--text2);font-size:.83rem;line-height:1.8;margin-bottom:.6rem}
.modal-section ul{color:var(--text2);font-size:.8rem;line-height:1.8;padding-left:1.2rem;margin-bottom:.6rem}
.modal-section li{margin-bottom:.3rem}
.modal-section li::marker{color:var(--accent)}
.spec-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:.7rem}
.spec-box{background:var(--surface);border:1px solid var(--border);border-radius:10px;padding:.9rem;text-align:center}
.spec-val{font-family:'Space Mono',monospace;font-size:1rem;font-weight:700;color:var(--accent);margin-bottom:.15rem}
.spec-label{font-family:'JetBrains Mono',monospace;font-size:.5rem;color:var(--text4);text-transform:uppercase;letter-spacing:.08em}
.ascii-diagram{background:var(--bg3);border:1px solid var(--border);border-radius:8px;padding:1rem;
  font-family:'JetBrains Mono',monospace;font-size:.55rem;color:var(--accent);line-height:1.4;overflow-x:auto;white-space:pre;margin:.6rem 0}
.iter-row{display:grid;grid-template-columns:repeat(4,1fr);gap:.5rem}
.iter-card{background:var(--surface);border:1px solid var(--border);border-radius:8px;padding:.7rem;text-align:center}
.iter-num{font-family:'Space Mono',monospace;font-size:.85rem;font-weight:700;color:var(--accent);margin-bottom:.15rem}
.iter-label{font-family:'JetBrains Mono',monospace;font-size:.48rem;color:var(--text4);text-transform:uppercase;letter-spacing:.06em;margin-bottom:.2rem}
.iter-desc{font-size:.65rem;color:var(--text3);line-height:1.3}
.modal-tags{display:flex;flex-wrap:wrap;gap:.3rem;margin-top:.4rem}
.modal-tag{font-family:'JetBrains Mono',monospace;font-size:.52rem;padding:.18rem .5rem;background:var(--bglow2);border:1px solid rgba(51,102,255,.15);border-radius:4px;color:var(--b200)}

/* ============ CONTACT ============ */
.contact-grid{display:grid;grid-template-columns:1fr 1fr;gap:2.5rem;align-items:start}
.contact-info h3{font-family:'Space Mono',monospace;font-size:1.2rem;font-weight:700;margin-bottom:.8rem}
.contact-info p{color:var(--text3);font-size:.85rem;line-height:1.7;margin-bottom:1.5rem}
.contact-links{display:flex;flex-direction:column;gap:.7rem}
.contact-link{display:flex;align-items:center;gap:.8rem;padding:.9rem 1rem;background:var(--surface);border:1px solid var(--border);
  border-radius:10px;text-decoration:none;color:var(--text2);transition:all .3s;font-size:.82rem}
.contact-link:hover{border-color:var(--accent);color:var(--accent);background:var(--bglow2)}
.contact-link svg{width:16px;height:16px;flex-shrink:0;color:var(--accent)}
.contact-link span{font-family:'JetBrains Mono',monospace;font-size:.6rem;color:var(--text4);text-transform:uppercase;letter-spacing:.06em}
.avail-card{background:var(--surface);border:1px solid var(--border);border-radius:14px;padding:1.8rem;position:relative;overflow:hidden}
.avail-card::before{content:'';position:absolute;top:0;left:0;right:0;height:3px;background:linear-gradient(90deg,var(--green),var(--accent))}
.avail-status{display:flex;align-items:center;gap:.5rem;margin-bottom:.8rem}
.avail-dot{width:9px;height:9px;border-radius:50%;background:var(--green);box-shadow:0 0 8px rgba(40,200,64,.4);animation:pulse 2s infinite}
.avail-text{font-family:'JetBrains Mono',monospace;font-size:.68rem;color:var(--green);font-weight:500}
.avail-card h4{font-family:'Space Mono',monospace;font-size:.95rem;font-weight:700;margin-bottom:.4rem}
.avail-card p{color:var(--text3);font-size:.8rem;line-height:1.6;margin-bottom:.8rem}
.avail-interests{display:flex;flex-wrap:wrap;gap:.3rem}
.avail-tag{font-family:'JetBrains Mono',monospace;font-size:.55rem;padding:.2rem .5rem;background:var(--bglow2);border:1px solid rgba(51,102,255,.12);border-radius:4px;color:var(--b200)}

footer{border-top:1px solid var(--border);padding:1.5rem 4rem;display:flex;justify-content:space-between;align-items:center;position:relative;z-index:1}
footer p{font-family:'JetBrains Mono',monospace;font-size:.6rem;color:var(--text4)}

/* ============ SCROLL PROGRESS BAR ============ */
.scroll-progress{position:fixed;top:0;left:0;right:0;height:3px;z-index:1001;background:transparent}
.scroll-fill{height:100%;width:0%;background:linear-gradient(90deg,var(--accent),var(--b300),var(--green));transition:width .05s linear}
.scroll-sections{position:fixed;top:3px;left:0;right:0;height:0;z-index:1001}
.scroll-marker{position:absolute;top:-1px;width:2px;height:5px;background:var(--text4);opacity:.5;transition:opacity .3s}
.scroll-marker.passed{opacity:0}

/* ============ PROJECT FILTER TABS ============ */
.filter-bar{display:flex;gap:.5rem;margin-bottom:1.8rem;flex-wrap:wrap}
.filter-btn{font-family:'JetBrains Mono',monospace;font-size:.6rem;padding:.45rem 1rem;border-radius:50px;border:1.5px solid var(--border);
  background:transparent;color:var(--text3);cursor:pointer;transition:all .25s;letter-spacing:.05em;text-transform:uppercase;font-weight:500}
.filter-btn:hover{border-color:var(--accent);color:var(--accent)}
.filter-btn.active{background:var(--accent);border-color:var(--accent);color:var(--bg);box-shadow:0 0 15px var(--bglow)}
.proj.filter-hidden{display:none}
.proj.filter-show{animation:filterIn .35s forwards}
@keyframes filterIn{from{opacity:0;transform:scale(.95) translateY(8px)}to{opacity:1;transform:scale(1) translateY(0)}}

/* ============ HEATMAP TOOLTIP ============ */
.hm-tooltip{position:fixed;z-index:9990;background:var(--bg);border:1px solid var(--accent);border-radius:6px;padding:.4rem .7rem;
  pointer-events:none;opacity:0;transition:opacity .15s;font-family:'JetBrains Mono',monospace;font-size:.55rem;
  color:var(--text);white-space:nowrap;box-shadow:0 4px 12px rgba(0,0,0,.4)}
.hm-tooltip.show{opacity:1}
.hm-tooltip .ht-date{color:var(--accent);margin-bottom:.15rem}
.hm-tooltip .ht-val{color:var(--text2)}

/* ============ BACK TO TOP ============ */
.back-top{position:fixed;bottom:2rem;right:2rem;z-index:999;width:42px;height:42px;border-radius:50%;
  background:var(--accent);border:none;color:#fff;cursor:pointer;display:flex;align-items:center;justify-content:center;
  box-shadow:0 4px 18px var(--bglow);opacity:0;transform:translateY(15px);transition:all .3s;pointer-events:none}
.back-top.show{opacity:1;transform:translateY(0);pointer-events:auto}
.back-top:hover{transform:translateY(-3px)!important;box-shadow:0 8px 25px rgba(51,102,255,.4)}
.back-top svg{width:18px;height:18px}

/* ============ TECH STACK CARDS ============ */
.tech-stack{margin:2.5rem 0}
.tech-stack-title{font-family:'JetBrains Mono',monospace;font-size:.6rem;color:var(--text4);text-transform:uppercase;letter-spacing:.1em;margin-bottom:1rem;
  display:flex;align-items:center;gap:.8rem}
.tech-stack-title::after{content:'';flex:1;height:1px;background:var(--border)}
.ts-scroll{display:flex;gap:.8rem;overflow-x:auto;padding-bottom:.8rem;scroll-snap-type:x mandatory;
  scrollbar-width:thin;scrollbar-color:var(--border) transparent;-webkit-overflow-scrolling:touch;
  justify-content:center}
.ts-scroll::-webkit-scrollbar{height:4px}
.ts-scroll::-webkit-scrollbar-thumb{background:var(--border);border-radius:2px}
.ts-card{flex-shrink:0;width:130px;scroll-snap-align:start;padding:1.2rem 1rem;background:var(--surface);
  border:1px solid var(--border);border-radius:12px;text-align:center;cursor:default;transition:all .3s;position:relative;overflow:hidden}
.ts-card::after{content:'';position:absolute;bottom:0;left:0;right:0;height:2px;background:var(--accent);transform:scaleX(0);transition:transform .3s}
.ts-card:hover{border-color:var(--accent);transform:translateY(-3px);box-shadow:0 8px 24px rgba(0,0,50,.25)}
.ts-card:hover::after{transform:scaleX(1)}
.ts-icon{font-size:1.6rem;margin-bottom:.5rem}
.ts-name{font-family:'JetBrains Mono',monospace;font-size:.68rem;font-weight:600;color:var(--text);margin-bottom:.2rem}
.ts-cat{font-family:'JetBrains Mono',monospace;font-size:.48rem;color:var(--text4);text-transform:uppercase;letter-spacing:.06em;margin-bottom:.4rem}
.ts-desc{font-size:.55rem;color:var(--text3);line-height:1.4;opacity:0;max-height:0;overflow:hidden;transition:all .3s}
.ts-card:hover .ts-desc{opacity:1;max-height:60px;margin-top:.3rem}
.ts-hint{font-family:'JetBrains Mono',monospace;font-size:.45rem;color:var(--text4);margin-top:.8rem;text-align:center;letter-spacing:.05em}

/* ============ EXPANDABLE TIMELINE ============ */
.tl-expand{display:none;margin-top:.6rem;padding:.8rem 1rem;background:var(--surface);border:1px solid var(--border);
  border-radius:8px;font-size:.78rem;color:var(--text2);line-height:1.7;animation:expandIn .3s forwards}
.tl-expand.open{display:block}
@keyframes expandIn{from{opacity:0;transform:translateY(-5px)}to{opacity:1;transform:translateY(0)}}
.tl-item{cursor:pointer}
.tl-toggle{font-family:'JetBrains Mono',monospace;font-size:.5rem;color:var(--accent);margin-top:.4rem;
  display:flex;align-items:center;gap:.3rem;text-transform:uppercase;letter-spacing:.06em;transition:color .2s}
.tl-toggle::after{content:'+';font-size:.7rem;transition:transform .3s}
.tl-item.expanded .tl-toggle::after{transform:rotate(45deg)}
.tl-item:hover .tl-toggle{color:var(--b200)}

/* ============ COMMAND CONSOLE ============ */
.cmd-bar{position:fixed;bottom:0;left:0;right:0;z-index:999;
  background:rgba(255,255,255,.95);backdrop-filter:blur(16px);border-top:1px solid var(--border);
  transition:transform .35s cubic-bezier(.23,1,.32,1);transform:translateY(100%)}
.cmd-bar.show{transform:translateY(0)}
.cmd-toggle{position:fixed;bottom:1.5rem;left:50%;transform:translateX(-50%);z-index:1000;
  font-family:'JetBrains Mono',monospace;font-size:.62rem;padding:.5rem 1.3rem;border-radius:8px;
  background:rgba(255,255,255,.92);border:1px solid var(--border);color:var(--text3);
  cursor:pointer;transition:all .35s cubic-bezier(.23,1,.32,1);letter-spacing:.06em;text-transform:uppercase;backdrop-filter:blur(12px);
  display:flex;align-items:center;gap:.5rem}
.cmd-toggle:hover{color:var(--accent);border-color:var(--accent)}
.cmd-toggle .kbd{font-size:.55rem;padding:.15rem .35rem;border:1px solid var(--border);border-radius:3px;color:var(--text4)}
.cmd-output{max-height:140px;overflow-y:auto;padding:.6rem 1.2rem;font-family:'JetBrains Mono',monospace;font-size:.68rem;
  line-height:1.8;color:var(--text2);scrollbar-width:thin;scrollbar-color:var(--border) transparent}
.cmd-output:empty{display:none}
.cmd-output .co-cmd{color:var(--accent)}.cmd-output .co-out{color:var(--text2)}
.cmd-output .co-err{color:#ff5f57}.cmd-output .co-hl{color:var(--b200)}
.cmd-output .co-grn{color:var(--green)}
.cmd-input-row{display:flex;align-items:center;padding:.5rem 1.2rem;border-top:1px solid rgba(42,52,85,.4)}
.cmd-prompt{font-family:'JetBrains Mono',monospace;font-size:.7rem;color:var(--accent);margin-right:.5rem;flex-shrink:0;font-weight:700}
.cmd-input{flex:1;background:transparent;border:none;outline:none;font-family:'JetBrains Mono',monospace;
  font-size:.7rem;color:var(--text);caret-color:var(--accent);letter-spacing:.02em}
.cmd-input::placeholder{color:var(--text4)}
.cmd-hint{font-family:'JetBrains Mono',monospace;font-size:.5rem;color:var(--text4);padding:.3rem 1.2rem;letter-spacing:.04em}

@media(max-width:900px){
  .hero,.section,.stats-bar{padding-left:2rem;padding-right:2rem}
  .hero-grid{grid-template-columns:1fr;gap:2.5rem;text-align:center}
  .hero-desc{max-width:100%}.hero-actions{justify-content:center}.hero-visual{order:-1}
  #heroCanvas{width:280px!important;height:280px!important}
  .stats-row{flex-wrap:wrap;gap:1.5rem;justify-content:center}
  .proj-grid,.contact-grid,.radar-wrapper{grid-template-columns:1fr}
  .impact-grid{grid-template-columns:1fr 1fr}
  .spec-grid{grid-template-columns:1fr 1fr}.iter-row{grid-template-columns:1fr 1fr}
  .flowchart{gap:.3rem}
  .modal{margin:1rem}.modal-header{flex-direction:column;gap:1rem}
  nav{padding:.7rem 1.5rem}footer{flex-direction:column;gap:.4rem;padding:1.2rem 2rem}
}
@media(max-width:600px){.nav-links{display:none}#heroCanvas{width:220px!important;height:220px!important}
  .impact-grid{grid-template-columns:1fr}.flow-step{width:110px;padding:.8rem .6rem}.sk-grid{grid-template-columns:1fr}}
</style>
</head>
<body>

<canvas id="particle-canvas"></canvas>

<!-- SCROLL PROGRESS -->
<div class="scroll-progress"><div class="scroll-fill" id="scrollFill"></div></div>

<!-- HEATMAP TOOLTIP -->
<div class="hm-tooltip" id="hmTooltip"><div class="ht-date"></div><div class="ht-val"></div></div>

<!-- BACK TO TOP -->
<button class="back-top" id="backTop" title="Back to top"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5"><path d="M18 15l-6-6-6 6"/></svg></button>

<div class="modal-overlay" id="modalOverlay"><div class="modal" id="modalContent"></div></div>

<nav>
  <div class="nav-name">Easton Drummonds<span>.</span></div>
  <ul class="nav-links">
    <li><a href="#hero" class="act">Home</a></li>
    <li><a href="#timeline">Timeline</a></li>
    <li><a href="#projects">Projects</a></li>
    <li><a href="#skills">Skills</a></li>
    <li><a href="#contact">Contact</a></li>
  </ul>
</nav>

<!-- HERO -->
<section class="hero" id="hero">
  <div class="hero-grid">
    <div>
      <div class="hero-label">Engineering // Data Analysis // AI Tools</div>
      <div class="hero-hello">Hello I'm</div>
      <div class="hero-name-big">Easton<br>Drummonds</div>
      <p class="hero-desc">Data-Driven Engineer <span>|</span> AI & Automation <span>|</span> Process Documentation <span>|</span> Dashboard Reporting <span>|</span> Georgia</p>
      <div class="hero-actions">
        <a href="#projects" class="btn-cv">View Projects &gt;</a>
        <div class="social-row">
          <a href="https://github.com/eastondrumm" class="social-icon" target="_blank"><svg viewBox="0 0 24 24" fill="currentColor"><path d="M12 2C6.477 2 2 6.477 2 12c0 4.42 2.865 8.166 6.839 9.489.5.092.682-.217.682-.482 0-.237-.008-.866-.013-1.7-2.782.604-3.369-1.34-3.369-1.34-.454-1.156-1.11-1.463-1.11-1.463-.908-.62.069-.608.069-.608 1.003.07 1.531 1.03 1.531 1.03.892 1.529 2.341 1.087 2.91.831.092-.646.35-1.086.636-1.336-2.22-.253-4.555-1.11-4.555-4.943 0-1.091.39-1.984 1.029-2.683-.103-.253-.446-1.27.098-2.647 0 0 .84-.269 2.75 1.025A9.578 9.578 0 0 1 12 6.836c.85 0 1.7.114 2.504.337 1.909-1.294 2.747-1.025 2.747-1.025.546 1.377.203 2.394.1 2.647.64.699 1.028 1.592 1.028 2.683 0 3.842-2.339 4.687-4.566 4.935.359.309.678.919.678 1.852 0 1.336-.012 2.415-.012 2.743 0 .267.18.578.688.48C19.138 20.163 22 16.418 22 12c0-5.523-4.477-10-10-10z"/></svg></a>
          <a href="https://www.linkedin.com/in/easton-drummonds-abb92b335/" class="social-icon" target="_blank"><svg viewBox="0 0 24 24" fill="currentColor"><path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433c-1.144 0-2.063-.926-2.063-2.065 0-1.138.92-2.063 2.063-2.063 1.14 0 2.064.925 2.064 2.063 0 1.139-.925 2.065-2.064 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/></svg></a>
          <a href="mailto:eastondrumm@icloud.com" class="social-icon"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><rect x="2" y="4" width="20" height="16" rx="2"/><path d="m2 4 10 8 10-8"/></svg></a>
        </div>
      </div>
    </div>
    <div class="hero-visual">
      <canvas id="heroCanvas" width="460" height="460" style="cursor:crosshair;max-width:100%;border-radius:12px"></canvas>
      <div style="font-family:'JetBrains Mono',monospace;font-size:.45rem;color:var(--text4);text-align:center;margin-top:.6rem;letter-spacing:.08em;text-transform:uppercase">&#x2190; Move mouse to interact &#x2192;</div>
    </div>
  </div>
</section>

<div class="stats-bar"><div class="stats-row">
  <div class="stat-item"><div class="stat-num" data-count="6" data-suffix="+">0</div><div class="stat-label">Shipped<br>Projects</div></div>
  <div class="stat-item"><div class="stat-num" data-count="3" data-suffix="+">0</div><div class="stat-label">Years<br>Building</div></div>
  <div class="stat-item"><div class="stat-num" data-count="5" data-suffix="">0</div><div class="stat-label">Programming<br>Languages</div></div>
  <div class="stat-item"><div class="stat-num" data-count="2" data-suffix="">0</div><div class="stat-label">TSA State<br>Placements</div></div>
</div></div>

<!-- ABOUT + TERMINAL + LIVE STATUS + FLOWCHART + HEATMAP -->
<div class="section sr" id="terminal-sec">
  <div class="sec-header"><span class="sec-num">01</span><div class="sec-line"></div><h2 class="sec-title">About.init()</h2></div>

  <!-- LIVE STATUS WIDGET -->
  <div class="live-widget">
    <div class="lw-status"><div class="lw-dot"></div><div class="lw-label">Building</div></div>
    <div class="lw-info">
      <h4>Currently // Open to Internship Opportunities</h4>
      <p>Seeking data analysis, AI tools, and business operations roles. Strong in Excel, Python, process documentation, and dashboard creation.</p>
    </div>
    <div class="lw-progress"><div class="lw-pct">Available Now</div><div class="lw-bar"><div class="lw-fill" style="width:100%"></div></div></div>
  </div>

  <div class="terminal">
    <div class="terminal-bar">
      <div class="tdot tdot-r" id="termClose"><span class="tdot-label">Close</span></div>
      <div class="tdot tdot-y" id="termMin"><span class="tdot-label">Minimize</span></div>
      <div class="tdot tdot-g" id="termMax"><span class="tdot-label">Fullscreen</span></div>
      <div class="terminal-title">easton@workshop ~ %</div>
    </div>
    <div class="terminal-body" id="termBody"></div>
  </div>
  <div id="termBackdrop" style="position:fixed;inset:0;background:rgba(20,25,40,.35);z-index:9989;opacity:0;pointer-events:none;transition:opacity .3s"></div>
  <button id="termReopen" style="display:none;font-family:'JetBrains Mono',monospace;font-size:.6rem;padding:.5rem 1.2rem;
    background:var(--surface);border:1px solid var(--border);border-radius:8px;color:var(--accent);cursor:pointer;
    transition:all .3s;letter-spacing:.06em;text-transform:uppercase;margin-bottom:1.5rem">&#x25b6; Reopen Terminal</button>
  </div>

  <!-- ENGINEERING PROCESS FLOWCHART -->
  <div style="font-family:'JetBrains Mono',monospace;font-size:.6rem;color:var(--text4);text-transform:uppercase;letter-spacing:.1em;margin-bottom:1rem">// My Problem-Solving Process</div>
  <div class="flowchart" id="flowchart">
    <div class="flow-step" data-i="0"><div class="flow-icon">&#x1f4a1;</div><div class="flow-label">Identify</div><div class="flow-sub">Problem Space</div></div>
    <div class="flow-arrow">&rarr;</div>
    <div class="flow-step" data-i="1"><div class="flow-icon">&#x270f;&#xfe0f;</div><div class="flow-label">Sketch</div><div class="flow-sub">Concept Design</div></div>
    <div class="flow-arrow">&rarr;</div>
    <div class="flow-step" data-i="2"><div class="flow-icon">&#x1f4d0;</div><div class="flow-label">CAD</div><div class="flow-sub">Onshape / AutoCAD</div></div>
    <div class="flow-arrow">&rarr;</div>
    <div class="flow-step" data-i="3"><div class="flow-icon">&#x2699;&#xfe0f;</div><div class="flow-label">Fabricate</div><div class="flow-sub">Bambu H2D / Manual</div></div>
    <div class="flow-arrow">&rarr;</div>
    <div class="flow-step" data-i="4"><div class="flow-icon">&#x1f9ea;</div><div class="flow-label">Test</div><div class="flow-sub">Field Validation</div></div>
    <div class="flow-arrow">&rarr;</div>
    <div class="flow-step" data-i="5"><div class="flow-icon">&#x1f504;</div><div class="flow-label">Iterate</div><div class="flow-sub">Refine & Repeat</div></div>
  </div>

  <!-- TECH STACK CAROUSEL -->
  <div class="tech-stack">
    <div class="tech-stack-title">// My Toolkit -- Hover to explore</div>
    <div class="ts-scroll">
      <div class="ts-card"><div class="ts-icon">&#x1f4ca;</div><div class="ts-name">Excel</div><div class="ts-cat">Data Analysis</div><div class="ts-desc">Formulas, pivot tables, data cleaning, dashboards, reporting</div></div>
      <div class="ts-card"><div class="ts-icon">&#x1f916;</div><div class="ts-name">Copilot</div><div class="ts-cat">AI Assistant</div><div class="ts-desc">Data summarization, report generation, process automation</div></div>
      <div class="ts-card"><div class="ts-icon">&#x1f4d0;</div><div class="ts-name">Onshape</div><div class="ts-cat">Primary CAD</div><div class="ts-desc">Cloud-native parametric CAD for all enclosure and mechanism design</div></div>
      <div class="ts-card"><div class="ts-icon">&#x1f4d0;</div><div class="ts-name">AutoCAD</div><div class="ts-cat">2D Drafting</div><div class="ts-desc">Technical drawings, dimensioning, and layout documentation</div></div>
      <div class="ts-card"><div class="ts-icon">&#x2699;&#xfe0f;</div><div class="ts-name">Bambu H2D</div><div class="ts-cat">3D Printer</div><div class="ts-desc">Primary fabrication tool for PETG and PLA prototyping</div></div>
      <div class="ts-card"><div class="ts-icon">&#x1f4bb;</div><div class="ts-name">ESP32</div><div class="ts-cat">Microcontroller</div><div class="ts-desc">Dual-core WiFi/BT MCU for embedded projects</div></div>
      <div class="ts-card"><div class="ts-icon">&#x1f4bb;</div><div class="ts-name">Arduino</div><div class="ts-cat">Microcontroller</div><div class="ts-desc">Nano, Uno for automotive, sensor, and rapid prototyping</div></div>
      <div class="ts-card"><div class="ts-icon">&#x1f40d;</div><div class="ts-name">Python</div><div class="ts-cat">Language</div><div class="ts-desc">CV, ML inference, Flask servers, automation scripts</div></div>
      <div class="ts-card"><div class="ts-icon">&#x2328;&#xfe0f;</div><div class="ts-name">C / C++</div><div class="ts-cat">Language</div><div class="ts-desc">Firmware, embedded systems, real-time control loops</div></div>
      <div class="ts-card"><div class="ts-icon">&#x2615;</div><div class="ts-name">Java</div><div class="ts-cat">Language</div><div class="ts-desc">OOP, data structures, GT dual enrollment</div></div>
      <div class="ts-card"><div class="ts-icon">&#x1f3ae;</div><div class="ts-name">Godot</div><div class="ts-cat">Game Engine</div><div class="ts-desc">2D/3D game dev with GDScript, TSA competitions</div></div>
      <div class="ts-card"><div class="ts-icon">&#x1f9ea;</div><div class="ts-name">MediaPipe</div><div class="ts-cat">CV Framework</div><div class="ts-desc">Hand tracking, gesture recognition, real-time inference</div></div>
      <div class="ts-card"><div class="ts-icon">&#x1f50a;</div><div class="ts-name">YAMNet</div><div class="ts-cat">Audio ML</div><div class="ts-desc">Sound event classification on edge devices</div></div>
    </div>
    <div class="ts-hint">&#x2190; Scroll to see all tools // Hover for details &#x2192;</div>
  </div>

  <!-- BUILD ACTIVITY HEATMAP -->
  <div class="heatmap-section">
    <div class="heatmap-title">Build Activity // Last 6 Months</div>
    <div class="heatmap" id="heatmap"></div>
    <div class="hm-legend"><span>Less</span>
      <div class="hm-cell" style="width:10px;height:10px;display:inline-block"></div>
      <div class="hm-cell" data-level="1" style="width:10px;height:10px;display:inline-block"></div>
      <div class="hm-cell" data-level="2" style="width:10px;height:10px;display:inline-block"></div>
      <div class="hm-cell" data-level="3" style="width:10px;height:10px;display:inline-block"></div>
      <div class="hm-cell" data-level="4" style="width:10px;height:10px;display:inline-block"></div>
      <span>More</span>
    </div>
  </div>
</div>

<!-- TIMELINE -->
<div class="section sr" id="timeline">
  <div class="sec-header"><span class="sec-num">02</span><div class="sec-line"></div><h2 class="sec-title">Engineering.log()</h2></div>
  <div class="timeline">
    <div class="tl-item"><div class="tl-dot"></div><div class="tl-date">2026 // Prototype Complete</div><div class="tl-title">Pip-Boy 3000 -- Wearable Enclosure System</div><div class="tl-desc">Fully functional prototype built with Onshape CAD and Bambu H2D. Full mechanical integration: display bezels, battery compartment, ventilation channels, snap-fit joints, and wrist-mount ergonomics. Now evaluating a fully custom PCB for the next revision.</div><div class="tl-tags"><span class="tl-tag">Onshape</span><span class="tl-tag">PETG</span><span class="tl-tag">Bambu H2D</span><span class="tl-tag">Snap-Fit</span></div><div class="tl-toggle">More details</div><div class="tl-expand">11-tab UI including Weather, Compass, Timer, Environment, Radar, Flashlight, Audio, Calculator, and Flappy Bird. WS2812 LEDs with light-pipe channels, buzzer, DAC audio output, IR receiver, and NVS settings persistence. Battery monitoring with voltage divider and accessible test points. All printed in PETG for heat tolerance.</div></div>
    <div class="tl-item"><div class="tl-dot"></div><div class="tl-date">2026 // 1st Place State SLC -- Nationals Bound</div><div class="tl-title">Wayward Echo -- TSA Video Game Design</div><div class="tl-desc">2D puzzle-platformer built in Godot 4.5.1 with a custom echo-recording mechanic. Won 1st Place at the TSA State Leadership Conference for Video Game Design and advancing to Nationals in June 2026.</div><div class="tl-tags"><span class="tl-tag">Godot 4.5</span><span class="tl-tag">GDScript</span><span class="tl-tag">1st Place State</span><span class="tl-tag">Nationals</span><span class="tl-tag">Pixel Art</span></div><div class="tl-toggle">More details</div><div class="tl-expand">Custom echo playback system records player input frame-by-frame and spawns semi-transparent replicas that interact with the environment. Time-manipulation objects track position history for rewind mechanics. Camera smoothing with lookahead for fluid platforming feel. All original pixel art, music, and sound. 4 stages with progressive difficulty scaling. Deployed as HTML5 for web-playable TSA requirement. Full iterative dev process with work logs, playtesting at each milestone, and storyboard documentation.</div></div>
    <div class="tl-item"><div class="tl-dot"></div><div class="tl-date">2025 // Summer Build</div><div class="tl-title">Custom NeoPixel Brakelight -- 2014 Nissan GT-R</div><div class="tl-desc">Designed and fabricated a custom LED brakelight for a 2014 Nissan GT-R using an Arduino Nano and NeoPixel LED strips. Engineered heat-resistant, weatherproof housing for automotive-grade reliability.</div><div class="tl-tags"><span class="tl-tag">Arduino Nano</span><span class="tl-tag">NeoPixel</span><span class="tl-tag">Automotive</span><span class="tl-tag">Weatherproofing</span><span class="tl-tag">12V</span></div><div class="tl-toggle">More details</div><div class="tl-expand">12V brake signal integration via optocoupler isolation for spike protection. Voltage regulation with reverse polarity protection and in-line fusing. Conformal coating on all electronics, silicone gaskets at seam points, and potted wire pass-throughs. Foam-lined mounting with rubber isolators for vibration dampening. Still installed and running daily since summer 2025.</div></div>
    <div class="tl-item"><div class="tl-dot"></div><div class="tl-date">2025 // Design & Fabrication</div><div class="tl-title">Sound Alert Pro -- Multi-Room Sensor Housing</div><div class="tl-desc">Engineered acoustic sensor enclosures with optimized microphone ports, ventilation slots for Raspberry Pi thermals, and modular mounting brackets.</div><div class="tl-tags"><span class="tl-tag">Enclosure Design</span><span class="tl-tag">Thermal Mgmt</span><span class="tl-tag">3D Print</span></div><div class="tl-toggle">More details</div><div class="tl-expand">YAMNet-based classification pipeline with Flask server providing local WebSocket notifications. Priority-based alerting with per-sound cooldowns, CSV data logging, and Chart.js analytics dashboard. Multi-room deployment over a local "SoundAlertNet" WiFi router for offline use at TSA events.</div></div>
    <div class="tl-item"><div class="tl-dot"></div><div class="tl-date">2025 // Electromechanical</div><div class="tl-title">Robotic Arm Controller -- 11-DOF Mechanism</div><div class="tl-desc">All materials sourced and ready for build day. Designing a hand-tracking controlled robotic arm with 11 degrees of freedom, mechanical linkages, servo mounting brackets, and cable management.</div><div class="tl-tags"><span class="tl-tag">Servo Mounts</span><span class="tl-tag">Linkages</span><span class="tl-tag">Load Analysis</span></div><div class="tl-toggle">More details</div><div class="tl-expand">Four-bar linkage finger mechanisms translating servo rotation into natural gripping motion. Internal cable routing channels preventing wire snagging during multi-axis movement. Weighted base with anti-tip geometry. Gusseted joints at high-stress points. Real-time control via MediaPipe hand tracking with serial communication to ESP32.</div></div>
    <div class="tl-item"><div class="tl-dot"></div><div class="tl-date">2024 // TSA State Competition</div><div class="tl-title">Sediment Sentry -- 7th Place at State SLC</div><div class="tl-desc">Placed 7th in the State Leadership Conference for TSA Engineering Design after a panel interview with judges. Complete design cycle: requirements, concept sketches, CAD, waterproof seals, solar panel mounting, ballast weighting, and field testing.</div><div class="tl-tags"><span class="tl-tag">Waterproofing</span><span class="tl-tag">Buoyancy Calc</span><span class="tl-tag">Solar Mount</span><span class="tl-tag">FEA</span></div><div class="tl-toggle">More details</div><div class="tl-expand">Four full iterations from concept to field-tested product at ~$35/unit. IP67 sealing with O-ring grooves and cable glands. Buoyancy calculations for stable waterline with electronics payload. Weighted keel for self-righting stability. Angled solar bracket with wind load reinforcement. Bottom-mounted turbidity sensor with anti-fouling geometry. GPS-enabled with wireless data link. Full TSA Engineering Design portfolio with work logs and documentation.</div></div>
    <div class="tl-item"><div class="tl-dot"></div><div class="tl-date">2024 // Competition</div><div class="tl-title">VEX V5 Clawbot -- Competition Robotics</div><div class="tl-desc">Disqualified before testing due to a lack of PPE (Personal Protective Equipment). Confident in the robot's capabilities and returning next season with 1st place at SLC as the target.</div><div class="tl-tags"><span class="tl-tag">VEX V5</span><span class="tl-tag">Gear Ratios</span><span class="tl-tag">CG Tuning</span></div><div class="tl-toggle">More details</div><div class="tl-expand">Programmed arcade drive with joystick axis mappings for intuitive control. Tuned claw servo PWM range for optimal grip force without crushing game pieces. Adjusted gear ratios for torque vs. speed balance on competition field surfaces. Added counterweight for stability during extended arm reach. DQ was a hard lesson in competition prep beyond just the robot itself, and I'm using it as fuel. Coming back stronger next season.</div></div>
  </div>
</div>

<!-- PROJECTS -->
<div class="section sr" id="projects">
  <div class="sec-header"><span class="sec-num">03</span><div class="sec-line"></div><h2 class="sec-title">Projects.showcase()</h2></div>
  <p style="color:var(--text3);font-size:.78rem;margin-bottom:1rem;font-family:'JetBrains Mono',monospace">// click any card to expand full details</p>
  <div class="filter-bar">
    <button class="filter-btn active" data-filter="all">All Projects</button>
    <button class="filter-btn" data-filter="mechanical">Mechanical</button>
    <button class="filter-btn" data-filter="automotive">Automotive</button>
    <button class="filter-btn" data-filter="embedded">Embedded</button>
    <button class="filter-btn" data-filter="gamedev">Game Dev</button>
    <button class="filter-btn" data-filter="ai">AI / Sensors</button>
  </div>
  <div class="proj-grid">
    <div class="proj" data-project="pipboy" data-cats="mechanical,embedded"><div class="proj-num">PROJECT_01</div><div class="proj-type">Mechanical Design + Embedded</div><h3>Pip-Boy 3000</h3><p>Fully functional wearable prototype with dual-ESP32 integration, snap-fit assembly, ventilation channels, and ergonomic wrist mounting. Evaluating custom PCB for next revision.</p><div class="tr"><span class="tt">Onshape</span><span class="tt">PETG</span><span class="tt">ESP32</span><span class="tt">Bambu H2D</span><span class="tt">C++</span></div><div class="proj-status"><div class="status-dot live"></div><span class="status-text">Prototype Complete</span></div><div class="proj-expand">View Full Breakdown</div></div>
    <div class="proj" data-project="gtr" data-cats="automotive,embedded"><div class="proj-num">PROJECT_02</div><div class="proj-type">Automotive Engineering</div><h3>GT-R Custom Brakelight</h3><p>Custom NeoPixel LED brakelight for a 2014 Nissan GT-R. Arduino Nano-driven, 12V integration, heat-resistant housing. Daily use since summer 2025.</p><div class="tr"><span class="tt">Arduino Nano</span><span class="tt">NeoPixel</span><span class="tt">12V Auto</span><span class="tt">Weatherproof</span></div><div class="proj-status"><div class="status-dot done"></div><span class="status-text">Installed & Running</span></div><div class="proj-expand">View Full Breakdown</div></div>
    <div class="proj" data-project="echo" data-cats="gamedev"><div class="proj-num">PROJECT_03</div><div class="proj-type">Game Development // TSA Competition</div><h3>Wayward Echo</h3><p>2D puzzle-platformer with custom echo-recording and time-rewind mechanics. 1st Place at TSA State SLC for Video Game Design. Competing at Nationals June 2026.</p><div class="tr"><span class="tt">Godot 4.5</span><span class="tt">GDScript</span><span class="tt">Pixel Art</span><span class="tt">HTML5</span><span class="tt">Game Design</span></div><div class="proj-status"><div class="status-dot live"></div><span class="status-text">Nationals Bound</span></div><div class="proj-expand">View Full Breakdown</div></div>
    <div class="proj" data-project="sentry" data-cats="mechanical,embedded"><div class="proj-num">PROJECT_04</div><div class="proj-type">Marine Engineering</div><h3>Sediment Sentry</h3><p>Four-iteration waterproof buoy placed 7th at TSA State SLC. Buoyancy calculations, IP67 sealing, solar panel mounting, and field-tested design at ~$35/unit.</p><div class="tr"><span class="tt">Waterproofing</span><span class="tt">Buoyancy</span><span class="tt">Solar</span><span class="tt">Arduino</span></div><div class="proj-status"><div class="status-dot done"></div><span class="status-text">7th at State SLC</span></div><div class="proj-expand">View Full Breakdown</div></div>
    <div class="proj" data-project="arm" data-cats="mechanical,embedded"><div class="proj-num">PROJECT_05</div><div class="proj-type">Electromechanical Systems</div><h3>Robotic Arm</h3><p>11-DOF hand-tracking controlled robotic arm with servo linkages and structural analysis. All materials purchased, awaiting build day.</p><div class="tr"><span class="tt">Servo Design</span><span class="tt">Linkages</span><span class="tt">MediaPipe</span><span class="tt">ESP32</span></div><div class="proj-status"><div class="status-dot live"></div><span class="status-text">Materials Ready</span></div><div class="proj-expand">View Full Breakdown</div></div>
    <div class="proj" data-project="sound" data-cats="ai,mechanical"><div class="proj-num">PROJECT_06</div><div class="proj-type">Sensor Enclosure Design</div><h3>Sound Alert Pro</h3><p>Acoustically-optimized sensor housing with thermal management, modular mounting, and RPi AI classification.</p><div class="tr"><span class="tt">Acoustic Ports</span><span class="tt">Thermal</span><span class="tt">RPi</span><span class="tt">YAMNet</span></div><div class="proj-status"><div class="status-dot done"></div><span class="status-text">Deployed</span></div><div class="proj-expand">View Full Breakdown</div></div>
  </div>

  <!-- IMPACT METRICS -->
  <div class="impact-grid">
    <div class="impact-card"><div class="impact-val">10+</div><div class="impact-label">Months<br>Brakelight Running</div><div class="impact-detail">Zero failures, daily driving</div></div>
    <div class="impact-card"><div class="impact-val">7th</div><div class="impact-label">Place at<br>TSA State SLC</div><div class="impact-detail">Sediment Sentry, panel interview</div></div>
    <div class="impact-card"><div class="impact-val">1st</div><div class="impact-label">Place at<br>TSA State SLC</div><div class="impact-detail">Wayward Echo, Nationals bound</div></div>
    <div class="impact-card"><div class="impact-val">11</div><div class="impact-label">Degrees of<br>Freedom</div><div class="impact-detail">Robotic arm mechanism</div></div>
  </div>
</div>

<!-- SKILLS: RADAR + BARS -->
<div class="section sr" id="skills">
  <div class="sec-header"><span class="sec-num">04</span><div class="sec-line"></div><h2 class="sec-title">Skills.proficiency()</h2></div>
  <div class="radar-wrapper">
    <div class="radar-container"><canvas id="radarCanvas" width="380" height="380"></canvas></div>
    <div>
      <div class="skill-list-col">
        <h3>// Data, AI & Business Tools</h3>
        <div class="skill-item"><div class="skill-header"><span class="skill-name">Microsoft Excel & Spreadsheets</span><span class="skill-pct">85%</span></div><div class="skill-bar"><div class="skill-fill" style="--w:85%"></div></div></div>
        <div class="skill-item"><div class="skill-header"><span class="skill-name">Data Analysis & Visualization</span><span class="skill-pct">82%</span></div><div class="skill-bar"><div class="skill-fill" style="--w:82%"></div></div></div>
        <div class="skill-item"><div class="skill-header"><span class="skill-name">AI Tools (Copilot / LLMs)</span><span class="skill-pct">88%</span></div><div class="skill-bar"><div class="skill-fill" style="--w:88%"></div></div></div>
        <div class="skill-item"><div class="skill-header"><span class="skill-name">Process Documentation</span><span class="skill-pct">90%</span></div><div class="skill-bar"><div class="skill-fill" style="--w:90%"></div></div></div>
        <div class="skill-item"><div class="skill-header"><span class="skill-name">Dashboard & Report Creation</span><span class="skill-pct">80%</span></div><div class="skill-bar"><div class="skill-fill" style="--w:80%"></div></div></div>
      </div>
      <div class="skill-list-col" style="margin-top:1.5rem">
        <h3>// Software & Embedded</h3>
        <div class="skill-item"><div class="skill-header"><span class="skill-name">ESP32 / Arduino Firmware</span><span class="skill-pct">93%</span></div><div class="skill-bar"><div class="skill-fill" style="--w:93%"></div></div></div>
        <div class="skill-item"><div class="skill-header"><span class="skill-name">C / C++</span><span class="skill-pct">90%</span></div><div class="skill-bar"><div class="skill-fill" style="--w:90%"></div></div></div>
        <div class="skill-item"><div class="skill-header"><span class="skill-name">Python</span><span class="skill-pct">88%</span></div><div class="skill-bar"><div class="skill-fill" style="--w:88%"></div></div></div>
        <div class="skill-item"><div class="skill-header"><span class="skill-name">Computer Vision / ML</span><span class="skill-pct">72%</span></div><div class="skill-bar"><div class="skill-fill" style="--w:72%"></div></div></div>
      </div>
    </div>
  </div>
</div>

<!-- CONTACT -->
<div class="section sr" id="contact">
  <div class="sec-header"><span class="sec-num">05</span><div class="sec-line"></div><h2 class="sec-title">Contact.send()</h2></div>
  <div class="contact-grid">
    <div class="contact-info">
      <h3>Let's build<br>something together.</h3>
      <p>Seeking internships in data analysis, AI-powered business operations, and technology. Strong Excel, Python, and AI tool skills backed by a portfolio of shipped engineering projects.</p>
      <div class="contact-links">
        <a href="mailto:eastondrumm@icloud.com" class="contact-link"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><rect x="2" y="4" width="20" height="16" rx="2"/><path d="m2 4 10 8 10-8"/></svg><div><div style="color:var(--text);font-size:.82rem;margin-bottom:.1rem">eastondrumm@icloud.com</div><span>Email</span></div></a>
        <a href="https://github.com/eastondrumm" class="contact-link" target="_blank"><svg viewBox="0 0 24 24" fill="currentColor"><path d="M12 2C6.477 2 2 6.477 2 12c0 4.42 2.865 8.166 6.839 9.489.5.092.682-.217.682-.482 0-.237-.008-.866-.013-1.7-2.782.604-3.369-1.34-3.369-1.34-.454-1.156-1.11-1.463-1.11-1.463-.908-.62.069-.608.069-.608 1.003.07 1.531 1.03 1.531 1.03.892 1.529 2.341 1.087 2.91.831.092-.646.35-1.086.636-1.336-2.22-.253-4.555-1.11-4.555-4.943 0-1.091.39-1.984 1.029-2.683-.103-.253-.446-1.27.098-2.647 0 0 .84-.269 2.75 1.025A9.578 9.578 0 0 1 12 6.836c.85 0 1.7.114 2.504.337 1.909-1.294 2.747-1.025 2.747-1.025.546 1.377.203 2.394.1 2.647.64.699 1.028 1.592 1.028 2.683 0 3.842-2.339 4.687-4.566 4.935.359.309.678.919.678 1.852 0 1.336-.012 2.415-.012 2.743 0 .267.18.578.688.48C19.138 20.163 22 16.418 22 12c0-5.523-4.477-10-10-10z"/></svg><div><div style="color:var(--text);font-size:.82rem;margin-bottom:.1rem">github.com/eastondrumm</div><span>GitHub</span></div></a>
        <a href="https://www.linkedin.com/in/easton-drummonds-abb92b335/" class="contact-link" target="_blank"><svg viewBox="0 0 24 24" fill="currentColor"><path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433c-1.144 0-2.063-.926-2.063-2.065 0-1.138.92-2.063 2.063-2.063 1.14 0 2.064.925 2.064 2.063 0 1.139-.925 2.065-2.064 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/></svg><div><div style="color:var(--text);font-size:.82rem;margin-bottom:.1rem">linkedin.com/in/easton-drummonds</div><span>LinkedIn</span></div></a>
      </div>
    </div>
    <div><div class="avail-card">
      <div class="avail-status"><div class="avail-dot"></div><div class="avail-text">Available for Opportunities</div></div>
      <h4>What I'm Looking For</h4>
      <p>Data analysis internships, AI operations roles, business technology positions, and engineering collaborations.</p>
      <div class="avail-interests"><span class="avail-tag">Data Analysis</span><span class="avail-tag">AI Operations</span><span class="avail-tag">Business Tech</span><span class="avail-tag">Excel & Reporting</span><span class="avail-tag">Process Improvement</span><span class="avail-tag">Semiconductor Industry</span></div>
    </div></div>
  </div>
</div>

<!-- COMMAND CONSOLE -->
<button class="cmd-toggle" id="cmdToggle"><span>&#x2318;</span> Command Console <span class="kbd">Ctrl+K</span></button>
<div class="cmd-bar" id="cmdBar">
  <div class="cmd-hint">Type "help" for a list of commands. Tab to autocomplete.</div>
  <div class="cmd-output" id="cmdOutput"></div>
  <div class="cmd-input-row">
    <span class="cmd-prompt">easton &gt;</span>
    <input type="text" class="cmd-input" id="cmdInput" placeholder="Type a command..." autocomplete="off" spellcheck="false">
  </div>
</div>

<footer><p>&copy; 2026 Easton Drummonds. All systems operational.</p><p style="color:var(--accent)">Designed & built from scratch</p></footer>

<script>
// ============ HOLOGRAPHIC ENGINEERING SCHEMATIC ============
(function(){
const hc = document.getElementById('heroCanvas');
const hx = hc.getContext('2d');
const S = 460, cx = S/2, cy = S/2;
let mx = 0.5, my = 0.5; // normalized mouse 0-1
let smx = 0.5, smy = 0.5; // smoothed values

hc.addEventListener('mousemove', e => {
  const r = hc.getBoundingClientRect();
  mx = (e.clientX - r.left) / r.width;
  my = (e.clientY - r.top) / r.height;
});
hc.addEventListener('mouseleave', () => { mx = 0.5; my = 0.5; });

// 3D projection helpers
const fov = 300;
function project(x, y, z, tiltX, tiltY) {
  // Rotate around Y axis (tiltY) then X axis (tiltX)
  let x1 = x * Math.cos(tiltY) - z * Math.sin(tiltY);
  let z1 = x * Math.sin(tiltY) + z * Math.cos(tiltY);
  let y1 = y * Math.cos(tiltX) - z1 * Math.sin(tiltX);
  let z2 = y * Math.sin(tiltX) + z1 * Math.cos(tiltX);
  const scale = fov / (fov + z2);
  return { x: cx + x1 * scale, y: cy + y1 * scale, s: scale, z: z2 };
}

// Generate gear vertices in 3D
function gearPoints3D(teeth, innerR, outerR, toothDepth, z) {
  const pts = [];
  const step = (Math.PI * 2) / teeth;
  for (let i = 0; i < teeth; i++) {
    const a1 = step * i;
    const a2 = a1 + step * 0.35;
    const a3 = a1 + step * 0.5;
    const a4 = a1 + step * 0.85;
    pts.push({ x: Math.cos(a1) * outerR, y: Math.sin(a1) * outerR, z });
    pts.push({ x: Math.cos(a2) * (outerR + toothDepth), y: Math.sin(a2) * (outerR + toothDepth), z });
    pts.push({ x: Math.cos(a3) * (outerR + toothDepth), y: Math.sin(a3) * (outerR + toothDepth), z });
    pts.push({ x: Math.cos(a4) * outerR, y: Math.sin(a4) * outerR, z });
  }
  return pts;
}

// Sparks
const sparks = [];
for (let i = 0; i < 25; i++) {
  sparks.push({
    angle: Math.random() * Math.PI * 2,
    r: 60 + Math.random() * 100,
    z: (Math.random() - 0.5) * 80,
    speed: 0.003 + Math.random() * 0.008,
    size: 1 + Math.random() * 2,
    brightness: 0.3 + Math.random() * 0.7
  });
}

function drawHero(t) {
  hx.clearRect(0, 0, S, S);

  // Smooth lerp toward target mouse position (eliminates snap)
  smx += (mx - smx) * 0.06;
  smy += (my - smy) * 0.06;

  // Tilt based on smoothed mouse
  const tiltY = (smx - 0.5) * 0.6;
  const tiltX = (smy - 0.5) * -0.4;

  // Blueprint grid (subtle)
  hx.save();
  hx.strokeStyle = 'rgba(51,102,255,0.06)';
  hx.lineWidth = 0.5;
  const gridSize = 25;
  for (let gx = 0; gx <= S; gx += gridSize) {
    hx.beginPath(); hx.moveTo(gx, 0); hx.lineTo(gx, S); hx.stroke();
  }
  for (let gy = 0; gy <= S; gy += gridSize) {
    hx.beginPath(); hx.moveTo(0, gy); hx.lineTo(S, gy); hx.stroke();
  }
  // Cross at center
  hx.strokeStyle = 'rgba(51,102,255,0.08)';
  hx.beginPath(); hx.moveTo(cx - 15, cy); hx.lineTo(cx + 15, cy); hx.stroke();
  hx.beginPath(); hx.moveTo(cx, cy - 15); hx.lineTo(cx, cy + 15); hx.stroke();
  hx.restore();

  // ---- MAIN GEAR ----
  const gearRot = t * 0.3;
  const mainTeeth = 18;
  const mainR = 80;

  // Draw gear at two Z layers for 3D depth
  [-12, 12].forEach((zOff, li) => {
    const pts = gearPoints3D(mainTeeth, 40, mainR, 14, zOff);
    const opacity = li === 0 ? 0.15 : 0.5;
    // Rotate points
    const rotated = pts.map(p => ({
      x: p.x * Math.cos(gearRot) - p.y * Math.sin(gearRot),
      y: p.x * Math.sin(gearRot) + p.y * Math.cos(gearRot),
      z: p.z
    }));
    const projected = rotated.map(p => project(p.x, p.y, p.z, tiltX, tiltY));

    hx.beginPath();
    projected.forEach((p, i) => i === 0 ? hx.moveTo(p.x, p.y) : hx.lineTo(p.x, p.y));
    hx.closePath();
    hx.strokeStyle = `rgba(51,102,255,${opacity})`;
    hx.lineWidth = li === 0 ? 0.8 : 1.5;
    hx.stroke();

    // Hub circle
    const hubPts = 24;
    hx.beginPath();
    for (let i = 0; i <= hubPts; i++) {
      const a = (Math.PI * 2 * i) / hubPts;
      const hpt = project(
        Math.cos(a + gearRot) * 25,
        Math.sin(a + gearRot) * 25,
        zOff, tiltX, tiltY
      );
      i === 0 ? hx.moveTo(hpt.x, hpt.y) : hx.lineTo(hpt.x, hpt.y);
    }
    hx.closePath();
    hx.strokeStyle = `rgba(51,102,255,${opacity * 0.8})`;
    hx.lineWidth = 1;
    hx.stroke();

    // Connecting lines to teeth
    if (li === 1) {
      hx.strokeStyle = 'rgba(51,102,255,0.12)';
      hx.lineWidth = 0.5;
      // Connect front hub to front gear edge
      for (let i = 0; i < 6; i++) {
        const a = gearRot + (Math.PI * 2 * i) / 6;
        const inner = project(Math.cos(a)*25, Math.sin(a)*25, zOff, tiltX, tiltY);
        const outer = project(Math.cos(a)*mainR, Math.sin(a)*mainR, zOff, tiltX, tiltY);
        hx.beginPath(); hx.moveTo(inner.x, inner.y); hx.lineTo(outer.x, outer.y); hx.stroke();
      }
    }
  });

  // Connect front and back gear layers (depth lines)
  hx.strokeStyle = 'rgba(51,102,255,0.1)';
  hx.lineWidth = 0.5;
  for (let i = 0; i < 8; i++) {
    const a = gearRot + (Math.PI * 2 * i) / 8;
    const f = project(Math.cos(a) * mainR, Math.sin(a) * mainR, 12, tiltX, tiltY);
    const b = project(Math.cos(a) * mainR, Math.sin(a) * mainR, -12, tiltX, tiltY);
    hx.beginPath(); hx.moveTo(f.x, f.y); hx.lineTo(b.x, b.y); hx.stroke();
  }

  // Center dot
  const cp = project(0, 0, 0, tiltX, tiltY);
  hx.beginPath(); hx.arc(cp.x, cp.y, 4, 0, Math.PI * 2);
  hx.fillStyle = 'rgba(51,102,255,0.8)'; hx.fill();
  hx.beginPath(); hx.arc(cp.x, cp.y, 2, 0, Math.PI * 2);
  hx.fillStyle = '#fff'; hx.fill();

  // ---- SMALL MESHING GEAR ----
  const smallRot = -t * 0.3 * (18/10) + 0.28; // inverse ratio, phase offset for tooth alignment
  const smallOffset = { x: 128, y: 52 }; // center distance ~138 for proper tooth interleave
  const smallTeeth = 10;
  const smallR = 44;

  [-8, 8].forEach((zOff, li) => {
    const pts = gearPoints3D(smallTeeth, 20, smallR, 10, zOff);
    const rotated = pts.map(p => ({
      x: p.x * Math.cos(smallRot) - p.y * Math.sin(smallRot) + smallOffset.x,
      y: p.x * Math.sin(smallRot) + p.y * Math.cos(smallRot) + smallOffset.y,
      z: p.z
    }));
    const projected = rotated.map(p => project(p.x, p.y, p.z, tiltX, tiltY));
    hx.beginPath();
    projected.forEach((p, i) => i === 0 ? hx.moveTo(p.x, p.y) : hx.lineTo(p.x, p.y));
    hx.closePath();
    hx.strokeStyle = `rgba(85,136,255,${li === 0 ? 0.12 : 0.4})`;
    hx.lineWidth = li === 0 ? 0.6 : 1.2;
    hx.stroke();
  });

  // ---- ORBITING RING ----
  const ringPts = 48;
  hx.beginPath();
  for (let i = 0; i <= ringPts; i++) {
    const a = (Math.PI * 2 * i) / ringPts;
    const rp = project(Math.cos(a) * 150, Math.sin(a) * 150 * 0.3, Math.sin(a) * 60, tiltX, tiltY);
    i === 0 ? hx.moveTo(rp.x, rp.y) : hx.lineTo(rp.x, rp.y);
  }
  hx.strokeStyle = 'rgba(51,102,255,0.12)';
  hx.lineWidth = 1;
  hx.setLineDash([4, 6]);
  hx.stroke();
  hx.setLineDash([]);

  // Orbiting dot on ring
  const orbAngle = t * 0.5;
  const orbP = project(Math.cos(orbAngle) * 150, Math.sin(orbAngle) * 150 * 0.3, Math.sin(orbAngle) * 60, tiltX, tiltY);
  hx.beginPath(); hx.arc(orbP.x, orbP.y, 4 * orbP.s, 0, Math.PI * 2);
  hx.fillStyle = 'rgba(51,102,255,0.9)';
  hx.shadowColor = 'rgba(51,102,255,0.6)'; hx.shadowBlur = 12; hx.fill();
  hx.shadowBlur = 0;

  // ---- SPARKS ----
  sparks.forEach(s => {
    s.angle += s.speed;
    const sp = project(
      Math.cos(s.angle) * s.r,
      Math.sin(s.angle) * s.r * 0.6,
      s.z + Math.sin(t + s.angle) * 15,
      tiltX, tiltY
    );
    hx.beginPath(); hx.arc(sp.x, sp.y, s.size * sp.s, 0, Math.PI * 2);
    hx.fillStyle = `rgba(51,102,255,${s.brightness * 0.4 * sp.s})`;
    hx.fill();
  });

  // ---- DIMENSION ANNOTATION (top) ----
  const dimL = project(-mainR - 14, -mainR - 35, 0, tiltX, tiltY);
  const dimR = project(mainR + 14, -mainR - 35, 0, tiltX, tiltY);
  hx.strokeStyle = 'rgba(51,102,255,0.3)';
  hx.lineWidth = 0.8;
  hx.beginPath(); hx.moveTo(dimL.x, dimL.y); hx.lineTo(dimR.x, dimR.y); hx.stroke();
  // End ticks
  hx.beginPath(); hx.moveTo(dimL.x, dimL.y - 4); hx.lineTo(dimL.x, dimL.y + 4); hx.stroke();
  hx.beginPath(); hx.moveTo(dimR.x, dimR.y - 4); hx.lineTo(dimR.x, dimR.y + 4); hx.stroke();
  // Vertical guides
  const dimLg = project(-mainR - 14, -mainR - 10, 0, tiltX, tiltY);
  const dimRg = project(mainR + 14, -mainR - 10, 0, tiltX, tiltY);
  hx.strokeStyle = 'rgba(51,102,255,0.1)';
  hx.setLineDash([2, 3]);
  hx.beginPath(); hx.moveTo(dimL.x, dimL.y); hx.lineTo(dimLg.x, dimLg.y); hx.stroke();
  hx.beginPath(); hx.moveTo(dimR.x, dimR.y); hx.lineTo(dimRg.x, dimRg.y); hx.stroke();
  hx.setLineDash([]);
  // Label
  const dimMid = { x: (dimL.x + dimR.x) / 2, y: dimL.y - 8 };
  hx.font = '500 9px JetBrains Mono';
  hx.fillStyle = 'rgba(51,102,255,0.5)';
  hx.textAlign = 'center';
  hx.fillText('188mm', dimMid.x, dimMid.y);

  // ---- SIDE ANNOTATION ----
  const sideT = project(mainR + 40, -50, 0, tiltX, tiltY);
  const sideB = project(mainR + 40, 50, 0, tiltX, tiltY);
  hx.strokeStyle = 'rgba(51,102,255,0.25)';
  hx.lineWidth = 0.8;
  hx.beginPath(); hx.moveTo(sideT.x, sideT.y); hx.lineTo(sideB.x, sideB.y); hx.stroke();
  hx.beginPath(); hx.moveTo(sideT.x - 4, sideT.y); hx.lineTo(sideT.x + 4, sideT.y); hx.stroke();
  hx.beginPath(); hx.moveTo(sideB.x - 4, sideB.y); hx.lineTo(sideB.x + 4, sideB.y); hx.stroke();
  hx.save();
  hx.translate(sideT.x + 10, (sideT.y + sideB.y) / 2);
  hx.rotate(-Math.PI / 2);
  hx.fillText('24mm depth', 0, 0);
  hx.restore();

  // ---- HUD READOUTS ----
  hx.font = '500 8.5px JetBrains Mono';
  hx.textAlign = 'left';

  // Top-left
  hx.fillStyle = 'rgba(51,102,255,0.4)';
  hx.fillText('SCHEMATIC // GEAR ASSEMBLY', 14, 22);
  hx.fillStyle = 'rgba(107,122,150,0.4)';
  hx.fillText('REV 4.2  |  ONSHAPE', 14, 34);

  // Top-right
  hx.textAlign = 'right';
  hx.fillStyle = 'rgba(51,102,255,0.2)';
  const rpm = (30 + Math.sin(t) * 5).toFixed(1);
  hx.fillText(rpm + ' RPM', S - 14, 22);
  hx.fillStyle = 'rgba(40,200,64,0.5)';
  hx.fillText('STATUS: NOMINAL', S - 14, 34);

  // Bottom-left
  hx.textAlign = 'left';
  hx.fillStyle = 'rgba(107,122,150,0.3)';
  hx.fillText('TEETH: 18/10  |  RATIO: 1.8:1', 14, S - 22);
  hx.fillText('MATERIAL: PETG  |  INFILL: 40%', 14, S - 10);

  // Bottom-right
  hx.textAlign = 'right';
  hx.fillStyle = 'rgba(51,102,255,0.3)';
  const torque = (2.4 + Math.sin(t * 0.7) * 0.3).toFixed(2);
  hx.fillText('TORQUE: ' + torque + ' N-m', S - 14, S - 22);
  hx.fillText('TILT: ' + ((smx-.5)*60).toFixed(1) + '/' + ((smy-.5)*-40).toFixed(1) + 'deg', S - 14, S - 10);

  // Corner brackets
  const bLen = 25;
  hx.strokeStyle = 'rgba(51,102,255,0.2)';
  hx.lineWidth = 1.5;
  // TL
  hx.beginPath(); hx.moveTo(6, 6 + bLen); hx.lineTo(6, 6); hx.lineTo(6 + bLen, 6); hx.stroke();
  // TR
  hx.beginPath(); hx.moveTo(S - 6 - bLen, 6); hx.lineTo(S - 6, 6); hx.lineTo(S - 6, 6 + bLen); hx.stroke();
  // BL
  hx.beginPath(); hx.moveTo(6, S - 6 - bLen); hx.lineTo(6, S - 6); hx.lineTo(6 + bLen, S - 6); hx.stroke();
  // BR
  hx.beginPath(); hx.moveTo(S - 6 - bLen, S - 6); hx.lineTo(S - 6, S - 6); hx.lineTo(S - 6, S - 6 - bLen); hx.stroke();

  requestAnimationFrame(() => drawHero(performance.now() / 1000));
}
drawHero(0);
})();
// ============ INTERACTIVE PARTICLE NETWORK ============
const pc = document.getElementById('particle-canvas');
const pctx = pc.getContext('2d');
let pw, ph, mouse = { x: -999, y: -999 };
const nodes = [];
function resizeParticles(){ pw = pc.width = window.innerWidth; ph = pc.height = window.innerHeight; }
resizeParticles();
window.addEventListener('resize', resizeParticles);
document.addEventListener('mousemove', e => { mouse.x = e.clientX; mouse.y = e.clientY; });

for (let i = 0; i < 70; i++) {
  nodes.push({ x: Math.random()*2000, y: Math.random()*2000, vx: (Math.random()-.5)*.3, vy: (Math.random()-.5)*.3, r: 1.5+Math.random()*1.5 });
}
function drawParticles() {
  pctx.clearRect(0, 0, pw, ph);
  nodes.forEach(n => {
    n.x += n.vx; n.y += n.vy;
    if (n.x < 0 || n.x > pw) n.vx *= -1;
    if (n.y < 0 || n.y > ph) n.vy *= -1;
    // Mouse repulsion
    const dx = n.x - mouse.x, dy = n.y - mouse.y;
    const dist = Math.sqrt(dx*dx + dy*dy);
    if (dist < 150) { n.vx += dx/dist * 0.15; n.vy += dy/dist * 0.15; }
    n.vx *= 0.99; n.vy *= 0.99;
    pctx.beginPath(); pctx.arc(n.x, n.y, n.r, 0, Math.PI*2);
    pctx.fillStyle = 'rgba(51,102,255,0.2)'; pctx.fill();
  });
  // Draw connections
  for (let i = 0; i < nodes.length; i++) for (let j = i+1; j < nodes.length; j++) {
    const dx = nodes[i].x - nodes[j].x, dy = nodes[i].y - nodes[j].y;
    const d = Math.sqrt(dx*dx+dy*dy);
    if (d < 150) {
      pctx.beginPath(); pctx.moveTo(nodes[i].x, nodes[i].y); pctx.lineTo(nodes[j].x, nodes[j].y);
      pctx.strokeStyle = `rgba(51,102,255,${0.08*(1-d/150)})`; pctx.lineWidth = .5; pctx.stroke();
    }
  }
  // Mouse connections
  nodes.forEach(n => {
    const dx = n.x-mouse.x, dy = n.y-mouse.y, d = Math.sqrt(dx*dx+dy*dy);
    if (d < 200) {
      pctx.beginPath(); pctx.moveTo(n.x,n.y); pctx.lineTo(mouse.x,mouse.y);
      pctx.strokeStyle = `rgba(51,102,255,${0.15*(1-d/200)})`; pctx.lineWidth = .8; pctx.stroke();
    }
  });
  requestAnimationFrame(drawParticles);
}
drawParticles();

// ============ BUILD HEATMAP ============
const heatmap = document.getElementById('heatmap');
const weeks = 26; // ~6 months
for (let w = 0; w < weeks; w++) {
  const col = document.createElement('div'); col.className = 'hm-col';
  for (let d = 0; d < 7; d++) {
    const cell = document.createElement('div'); cell.className = 'hm-cell';
    // Generate pseudo-random but believable activity
    const weekFactor = Math.sin(w * 0.25) * 0.5 + 0.5;
    const r = Math.random();
    let level = 0;
    if (r < 0.15 + weekFactor * 0.3) level = 1;
    if (r < 0.08 + weekFactor * 0.2) level = 2;
    if (r < 0.04 + weekFactor * 0.12) level = 3;
    if (r < 0.02 + weekFactor * 0.06) level = 4;
    // Weekends less active
    if (d >= 5 && level > 0) level = Math.max(0, level - 1);
    if (level > 0) cell.dataset.level = level;
    col.appendChild(cell);
  }
  heatmap.appendChild(col);
}

// ============ SKILLS RADAR CHART ============
const radarData = [
  { label: 'CAD', val: 88 }, { label: '3D Print', val: 95 }, { label: 'Mechanisms', val: 80 },
  { label: 'Firmware', val: 93 }, { label: 'C/C++', val: 90 }, { label: 'Python', val: 88 },
  { label: 'Enclosures', val: 88 }, { label: 'CV/ML', val: 72 }
];
let radarAnimated = false;
function drawRadar(progress) {
  const canvas = document.getElementById('radarCanvas');
  const ctx = canvas.getContext('2d');
  const cx = 190, cy = 190, maxR = 140;
  const n = radarData.length;
  ctx.clearRect(0, 0, 380, 380);
  // Grid
  for (let ring = 1; ring <= 4; ring++) {
    const r = maxR * ring / 4;
    ctx.beginPath();
    for (let i = 0; i <= n; i++) {
      const angle = (Math.PI * 2 * i / n) - Math.PI / 2;
      const x = cx + Math.cos(angle) * r, y = cy + Math.sin(angle) * r;
      i === 0 ? ctx.moveTo(x, y) : ctx.lineTo(x, y);
    }
    ctx.closePath(); ctx.strokeStyle = 'rgba(51,102,255,.12)'; ctx.lineWidth = 1; ctx.stroke();
  }
  // Axes
  for (let i = 0; i < n; i++) {
    const angle = (Math.PI * 2 * i / n) - Math.PI / 2;
    ctx.beginPath(); ctx.moveTo(cx, cy);
    ctx.lineTo(cx + Math.cos(angle) * maxR, cy + Math.sin(angle) * maxR);
    ctx.strokeStyle = 'rgba(51,102,255,.08)'; ctx.lineWidth = 1; ctx.stroke();
  }
  // Data fill
  ctx.beginPath();
  for (let i = 0; i <= n; i++) {
    const idx = i % n;
    const angle = (Math.PI * 2 * idx / n) - Math.PI / 2;
    const r = maxR * (radarData[idx].val / 100) * progress;
    const x = cx + Math.cos(angle) * r, y = cy + Math.sin(angle) * r;
    i === 0 ? ctx.moveTo(x, y) : ctx.lineTo(x, y);
  }
  ctx.closePath();
  ctx.fillStyle = 'rgba(51,102,255,.12)'; ctx.fill();
  ctx.strokeStyle = 'rgba(51,102,255,.7)'; ctx.lineWidth = 2; ctx.stroke();
  // Dots and labels
  for (let i = 0; i < n; i++) {
    const angle = (Math.PI * 2 * i / n) - Math.PI / 2;
    const r = maxR * (radarData[i].val / 100) * progress;
    const x = cx + Math.cos(angle) * r, y = cy + Math.sin(angle) * r;
    ctx.beginPath(); ctx.arc(x, y, 4, 0, Math.PI * 2);
    ctx.fillStyle = '#3366ff'; ctx.fill();
    ctx.beginPath(); ctx.arc(x, y, 2, 0, Math.PI * 2);
    ctx.fillStyle = '#fff'; ctx.fill();
    // Label
    const lx = cx + Math.cos(angle) * (maxR + 18), ly = cy + Math.sin(angle) * (maxR + 18);
    ctx.fillStyle = '#6b7a96'; ctx.font = '500 10px JetBrains Mono';
    ctx.textAlign = 'center'; ctx.textBaseline = 'middle';
    ctx.fillText(radarData[i].label, lx, ly);
  }
}
drawRadar(0);

// ============ FLOWCHART ANIMATION ============
let flowAnimated = false;
function animateFlow() {
  if (flowAnimated) return; flowAnimated = true;
  const steps = document.querySelectorAll('.flow-step');
  const arrows = document.querySelectorAll('.flow-arrow');
  let activeIdx = 0;
  function nextStep() {
    if (activeIdx < steps.length) { steps[activeIdx].classList.add('vis'); steps[activeIdx].style.transitionDelay = (activeIdx * 0.12) + 's'; }
    if (activeIdx > 0 && activeIdx <= arrows.length) { arrows[activeIdx-1].classList.add('vis'); }
    activeIdx++;
    if (activeIdx <= steps.length) setTimeout(nextStep, 150);
    else { // Cycle active highlight
      let hi = 0;
      setInterval(() => { steps.forEach(s => s.classList.remove('active')); steps[hi % steps.length].classList.add('active'); hi++; }, 2000);
    }
  }
  nextStep();
}

// ============ TERMINAL ============
const termLines=[
  {type:'cmd',text:'cat ~/profile.yml'},{type:'out',text:'name: Easton Drummonds'},
  {type:'out',text:'focus: Mechanical Engineering & Embedded Systems'},
  {type:'out',text:'approach: "I noticed a problem, so I engineered a solution"'},
  {type:'cmd',text:'ls ~/workshop'},
  {type:'hl',text:'Bambu_H2D/  Onshape/  AutoCAD/  Calipers/  Soldering_Station/  ESP32s/'},
  {type:'cmd',text:'cat ~/design_philosophy.txt'},
  {type:'out',text:'Every project goes through concept, CAD, prototype, test, iterate.'},
  {type:'cmd',text:'echo $CURRENT_BUILD'},
  {type:'out',text:'Pip-Boy 3000: prototype complete, evaluating custom PCB for rev 2'},
  {type:'cmd',text:'echo $PROUDEST_DEPLOY'},
  {type:'out',text:'Custom NeoPixel brakelight on a 2014 GT-R -- still running daily'},
];
let termStarted=false;
function startTerminal(){if(termStarted)return;termStarted=true;const body=document.getElementById('termBody');let i=0;
function add(){if(i>=termLines.length){const c=document.createElement('div');c.innerHTML='<span class="t-prompt">$ </span><span class="cursor-blink"></span>';c.classList.add('t-line');body.appendChild(c);return}
const l=termLines[i],el=document.createElement('div');el.classList.add('t-line');
if(l.type==='cmd')el.innerHTML=`<span class="t-prompt">$ </span><span class="t-cmd">${l.text}</span>`;
else if(l.type==='hl')el.innerHTML=`<span class="t-hl">${l.text}</span>`;
else el.innerHTML=`<span class="t-out">${l.text}</span>`;
body.appendChild(el);i++;setTimeout(add,l.type==='cmd'?400:150)}add()}

// ============ TERMINAL WINDOW BUTTONS ============
const termEl = document.querySelector('.terminal');
const termBackdrop = document.getElementById('termBackdrop');
const termReopen = document.getElementById('termReopen');

document.getElementById('termClose').addEventListener('click', e => {
  e.stopPropagation();
  termEl.classList.add('closed');
  termEl.classList.remove('fullscreen','minimized');
  termBackdrop.style.opacity = '0'; termBackdrop.style.pointerEvents = 'none';
  termReopen.style.display = 'block';
});

document.getElementById('termMin').addEventListener('click', e => {
  e.stopPropagation();
  if (termEl.classList.contains('minimized')) {
    termEl.classList.remove('minimized');
  } else {
    termEl.classList.add('minimized');
    termEl.classList.remove('fullscreen');
    termBackdrop.style.opacity = '0'; termBackdrop.style.pointerEvents = 'none';
  }
});

document.getElementById('termMax').addEventListener('click', e => {
  e.stopPropagation();
  if (termEl.classList.contains('fullscreen')) {
    termEl.classList.remove('fullscreen');
    termBackdrop.style.opacity = '0'; termBackdrop.style.pointerEvents = 'none';
  } else {
    termEl.classList.add('fullscreen');
    termEl.classList.remove('minimized');
    termBackdrop.style.opacity = '1'; termBackdrop.style.pointerEvents = 'auto';
  }
});

termBackdrop.addEventListener('click', () => {
  termEl.classList.remove('fullscreen');
  termBackdrop.style.opacity = '0'; termBackdrop.style.pointerEvents = 'none';
});

termReopen.addEventListener('click', () => {
  termEl.classList.remove('closed');
  termReopen.style.display = 'none';
});

// ============ PROJECT MODAL DATA ============
const projectData = {
  pipboy:{icon:'&#x2699;&#xfe0f;',type:'Mechanical Design + Embedded Systems',title:'Pip-Boy 3000',sub:'Fully functional prototype built. Evaluating custom PCB for next revision.',sections:[
    {title:'// Overview',content:`<p>The Pip-Boy 3000 is a wrist-mounted wearable computer with a fully functional prototype now built and tested. The project spanned enclosure design in Onshape, multi-board packaging, thermal management, and ergonomic mounting. Currently evaluating whether to move to a fully custom PCB for the next design revision.</p>`},
    {title:'// Mechanical Design',content:`<ul><li><strong>Snap-fit joints</strong> for tool-free assembly and maintenance access</li><li><strong>Display bezel</strong> with tight-tolerance press-fit for the 4" TFT</li><li><strong>Internal standoffs</strong> and cable routing for dual ESP32-WROOM-32E boards</li><li><strong>Ventilation slots</strong> for passive convective cooling under WiFi load</li><li><strong>Battery compartment</strong> with retention clips and charging port cutout</li><li><strong>Wrist-mount system</strong> with padded contact surfaces and adjustable straps</li></ul><p>All parts printed in PETG on a Bambu H2D.</p>`},
    {title:'// Specifications',content:`<div class="spec-grid"><div class="spec-box"><div class="spec-val">2</div><div class="spec-label">ESP32 Boards</div></div><div class="spec-box"><div class="spec-val">4"</div><div class="spec-label">TFT Display</div></div><div class="spec-box"><div class="spec-val">11</div><div class="spec-label">UI Tabs</div></div><div class="spec-box"><div class="spec-val">PETG</div><div class="spec-label">Material</div></div><div class="spec-box"><div class="spec-val">H2D</div><div class="spec-label">Printer</div></div><div class="spec-box"><div class="spec-val">Onshape</div><div class="spec-label">CAD</div></div></div>`},
    {title:'// Technologies',content:`<div class="modal-tags"><span class="modal-tag">Onshape</span><span class="modal-tag">PETG</span><span class="modal-tag">Bambu H2D</span><span class="modal-tag">ESP32</span><span class="modal-tag">C++</span><span class="modal-tag">Snap-Fit</span><span class="modal-tag">I2C/SPI</span><span class="modal-tag">DAC Audio</span><span class="modal-tag">Thermal Mgmt</span></div>`}]},
  gtr:{icon:'&#x1f3ce;&#xfe0f;',type:'Automotive Engineering & LED Systems',title:'GT-R Custom Brakelight',sub:'Custom NeoPixel LED brakelight for a 2014 Nissan GT-R, running daily since summer 2025',sections:[
    {title:'// Overview',content:`<p>Designed and fabricated a fully custom LED brakelight assembly for a 2014 Nissan GT-R R35. Arduino Nano-controlled NeoPixel strips engineered for automotive-grade reliability: heat cycling, road vibration, water exposure, and 12V power. Still installed and running daily since summer 2025.</p>`},
    {title:'// Mechanical & Electrical Design',content:`<ul><li><strong>Housing:</strong> Custom enclosure matching GT-R rear body lines with OEM bolt patterns</li><li><strong>Thermal:</strong> Aluminum backing strip to conduct heat away from NeoPixels under sustained braking</li><li><strong>Weatherproofing:</strong> Conformal coating, silicone gaskets, potted wire pass-throughs</li><li><strong>Vibration:</strong> Foam-lined mounting with rubber isolators to prevent solder fatigue</li><li><strong>12V Integration:</strong> Voltage regulation with reverse polarity protection and in-line fusing</li><li><strong>Brake Signal:</strong> Optocoupler-isolated tap into existing brake wire for spike protection</li></ul>`},
    {title:'// Specifications',content:`<div class="spec-grid"><div class="spec-box"><div class="spec-val">Nano</div><div class="spec-label">Controller</div></div><div class="spec-box"><div class="spec-val">NeoPixel</div><div class="spec-label">LED Type</div></div><div class="spec-box"><div class="spec-val">12V</div><div class="spec-label">Vehicle Supply</div></div><div class="spec-box"><div class="spec-val">R35</div><div class="spec-label">GT-R Chassis</div></div><div class="spec-box"><div class="spec-val">10+ mo</div><div class="spec-label">Runtime</div></div><div class="spec-box"><div class="spec-val">Daily</div><div class="spec-label">Use</div></div></div>`},
    {title:'// Why This Matters',content:`<p>This brakelight has to work every single time, in rain, heat, cold, and vibration. No resetting or debugging at highway speeds. Designing for that reliability level -- the right sealing, thermal cycling tolerance, and voltage transient protection -- is what real-world mechanical and automotive engineering demands.</p>`},
    {title:'// Technologies',content:`<div class="modal-tags"><span class="modal-tag">Arduino Nano</span><span class="modal-tag">NeoPixel WS2812B</span><span class="modal-tag">12V Automotive</span><span class="modal-tag">Voltage Regulation</span><span class="modal-tag">Optocoupler</span><span class="modal-tag">Weatherproof Seal</span><span class="modal-tag">Vibration Dampening</span><span class="modal-tag">OEM Fitment</span></div>`}]},
  echo:{icon:'&#x1f3ae;',type:'Game Development // TSA Competition',title:'Wayward Echo',sub:'1st Place at TSA State SLC. Advancing to Nationals June 2026.',sections:[
    {title:'// Overview',content:`<p>Wayward Echo is a 2D puzzle-platformer built in Godot 4.5.1 where the player explores a mysterious planet and solves puzzles using a unique echo-recording mechanic. The game won 1st Place at the TSA State Leadership Conference for Video Game Design in Athens, Georgia and is advancing to the National TSA competition in June 2026.</p><p>The story follows a mission to find resources for a dying Earth. The player crash-lands on a desolate planet inhabited by shadowy creatures called "Echos" who are actually the lost scientists from the original mission. By coordinating with echo clones and mastering time-manipulation, the player solves increasingly complex puzzles across 4 stages.</p>`},
    {title:'// Core Mechanics',content:`<ul><li><strong>Echo Recording:</strong> Custom system records player input frame-by-frame, then spawns a semi-transparent replica that repeats the exact movements and can physically interact with buttons, boxes, and platforms</li><li><strong>Time Rewind:</strong> Rewindable boxes track position history, allowing the player to undo mistakes or ride rewinding objects to reach new areas</li><li><strong>Progressive Complexity:</strong> Mechanics layer on top of each other: buttons, doors, toggleable spikes, moving platforms, box dispensers, jump pads, and multi-button doors</li><li><strong>Camera System:</strong> Custom smoothing with lookahead for fluid platforming feel during fast-paced sections</li></ul>`},
    {title:'// Technical Implementation',content:`<div class="spec-grid"><div class="spec-box"><div class="spec-val">Godot 4.5</div><div class="spec-label">Engine</div></div><div class="spec-box"><div class="spec-val">GDScript</div><div class="spec-label">Language</div></div><div class="spec-box"><div class="spec-val">4</div><div class="spec-label">Stages</div></div><div class="spec-box"><div class="spec-val">HTML5</div><div class="spec-label">Deployment</div></div><div class="spec-box"><div class="spec-val">16-bit</div><div class="spec-label">Art Style</div></div><div class="spec-box"><div class="spec-val">1st</div><div class="spec-label">Place at State</div></div></div>`},
    {title:'// Development Process',content:`<p>Built through an iterative design approach with 4 major drafts. Prototyping started with core mechanics (echo recording, rewindable crates) before building levels that teach, test, and extend each mechanic progressively. Playtesting at every milestone ensured puzzle clarity and difficulty scaling. All pixel art, parallax backgrounds, music, and sound effects are original work. Full documentation with work logs and storyboards for TSA competition submission.</p>`},
    {title:'// Competition Results',content:`<ul><li><strong>TSA State SLC (Athens, GA):</strong> 1st Place, Video Game Design</li><li><strong>TSA Nationals (June 2026):</strong> Advancing to compete at national level</li></ul>`},
    {title:'// Technologies',content:`<div class="modal-tags"><span class="modal-tag">Godot 4.5.1</span><span class="modal-tag">GDScript</span><span class="modal-tag">Pixel Art</span><span class="modal-tag">HTML5 Deploy</span><span class="modal-tag">Custom Echo System</span><span class="modal-tag">Time Rewind</span><span class="modal-tag">Camera Smoothing</span><span class="modal-tag">Parallax Scrolling</span><span class="modal-tag">Level Design</span><span class="modal-tag">Original Audio</span></div>`}]},
  sentry:{icon:'&#x1f30a;',type:'Marine Engineering',title:'Sediment Sentry',sub:'7th Place at TSA State SLC. Four design iterations, panel interview with judges.',sections:[
    {title:'// Overview',content:`<p>Low-cost (~$35) autonomous water quality monitoring buoy that placed 7th at the TSA State Leadership Conference after a panel interview with judges. Complete engineering design cycle across four major revisions: requirements, concept, CAD, prototyping, field testing, and iterative refinement.</p>`},
    {title:'// Design Iterations',content:`<div class="iter-row"><div class="iter-card"><div class="iter-num">v1</div><div class="iter-label">Concept</div><div class="iter-desc">Basic float, proof of concept</div></div><div class="iter-card"><div class="iter-num">v2</div><div class="iter-label">Structural</div><div class="iter-desc">Reinforced hull, seals</div></div><div class="iter-card"><div class="iter-num">v3</div><div class="iter-label">Integration</div><div class="iter-desc">Solar mount, GPS, ballast</div></div><div class="iter-card"><div class="iter-num">v4</div><div class="iter-label">Production</div><div class="iter-desc">Final field-tested design</div></div></div>`},
    {title:'// Mechanical Challenges',content:`<ul><li><strong>IP67 sealing:</strong> O-ring grooves, gasket compression, cable glands</li><li><strong>Buoyancy:</strong> Displaced volume vs. total mass for stable waterline</li><li><strong>Ballast:</strong> Weighted keel for self-righting stability</li><li><strong>Solar mounting:</strong> Angled bracket for optimal exposure with wind load reinforcement</li></ul>`},
    {title:'// Technologies',content:`<div class="modal-tags"><span class="modal-tag">Arduino</span><span class="modal-tag">GPS</span><span class="modal-tag">Solar</span><span class="modal-tag">O-Ring Sealing</span><span class="modal-tag">Buoyancy Analysis</span><span class="modal-tag">3D Print</span><span class="modal-tag">Field Testing</span></div>`}]},
  arm:{icon:'&#x1f9be;',type:'Electromechanical Systems',title:'Robotic Arm Controller',sub:'11-DOF hand-tracking robotic arm. Materials sourced, build day incoming.',sections:[
    {title:'// Overview',content:`<p>An 11 degree-of-freedom robotic arm designed for real-time webcam hand tracking control via MediaPipe. All materials have been purchased and the build is ready for assembly day. Mechanical challenges include servo mounting, joint linkage geometry, cable routing, and structural rigidity under dynamic loads.</p>`},
    {title:'// Mechanical Design',content:`<ul><li><strong>Servo brackets</strong> with bearing surfaces for smooth rotation under load</li><li><strong>Four-bar linkages</strong> translating servo rotation into natural gripping motion</li><li><strong>Internal cable channels</strong> preventing wire snagging during movement</li><li><strong>Weighted base</strong> with anti-tip geometry for full arm extension</li><li><strong>Gusseted joints</strong> at high-stress points</li></ul>`},
    {title:'// Technologies',content:`<div class="modal-tags"><span class="modal-tag">Servo Mechanisms</span><span class="modal-tag">4-Bar Linkages</span><span class="modal-tag">ESP32</span><span class="modal-tag">MediaPipe</span><span class="modal-tag">Python</span><span class="modal-tag">3D Print</span></div>`}]},
  sound:{icon:'&#x1f50a;',type:'Sensor Enclosure + AI',title:'Sound Alert Pro',sub:'Acoustically-optimized enclosures with AI classification',sections:[
    {title:'// Overview',content:`<p>YAMNet-based sound classification on Raspberry Pi. Mechanical focus: enclosures balancing acoustic performance, thermal management, and multi-room deployment flexibility.</p>`},
    {title:'// Enclosure Engineering',content:`<ul><li><strong>Acoustic ports:</strong> Calculated geometry for omnidirectional pickup</li><li><strong>Thermal ventilation:</strong> Slot patterns sized for passive RPi cooling</li><li><strong>Modular mounting:</strong> Wall, desk, ceiling with tool-free quick-release</li></ul>`},
    {title:'// Technologies',content:`<div class="modal-tags"><span class="modal-tag">Acoustic Design</span><span class="modal-tag">Thermal Analysis</span><span class="modal-tag">RPi</span><span class="modal-tag">YAMNet</span><span class="modal-tag">Flask</span><span class="modal-tag">WebSocket</span><span class="modal-tag">3D Print</span></div>`}]}
};

// Modal logic
const overlay=document.getElementById('modalOverlay'),modalC=document.getElementById('modalContent');
document.querySelectorAll('.proj[data-project]').forEach(c=>{c.addEventListener('click',()=>{
  const d=projectData[c.dataset.project];if(!d)return;
  let h=`<button class="modal-close" id="mc">&times;</button><div class="modal-header"><div class="modal-badge">${d.icon}</div><div class="modal-meta"><div class="proj-type">${d.type}</div><h2>${d.title}</h2><div class="modal-sub">${d.sub}</div></div></div><div class="modal-body">`;
  d.sections.forEach(s=>{h+=`<div class="modal-section"><h3>${s.title}</h3>${s.content}</div>`});
  h+='</div>';modalC.innerHTML=h;overlay.classList.add('open');document.body.style.overflow='hidden';
  document.getElementById('mc').addEventListener('click',closeM)})});
function closeM(){overlay.classList.remove('open');document.body.style.overflow=''}
overlay.addEventListener('click',e=>{if(e.target===overlay)closeM()});
document.addEventListener('keydown',e=>{if(e.key==='Escape')closeM()});

// ============ OBSERVERS ============
const rObs=new IntersectionObserver(e=>{e.forEach(x=>{if(x.isIntersecting){x.target.classList.add('vis');
  if(x.target.id==='terminal-sec'){startTerminal();animateFlow()}}})},{threshold:.1});
document.querySelectorAll('.sr').forEach(el=>rObs.observe(el));

const tlObs=new IntersectionObserver(e=>{e.forEach(x=>{if(x.isIntersecting)x.target.classList.add('active')})},{threshold:.2,rootMargin:'0px 0px -60px 0px'});
document.querySelectorAll('.tl-item').forEach(el=>tlObs.observe(el));

// Radar + skill bars animation
const skObs=new IntersectionObserver(e=>{e.forEach(x=>{if(x.isIntersecting&&!radarAnimated){
  radarAnimated=true;let p=0;const anim=()=>{p+=0.025;drawRadar(Math.min(1,p));if(p<1)requestAnimationFrame(anim)};anim();
  x.target.querySelectorAll('.skill-fill').forEach(b=>b.classList.add('anim'))}})},{threshold:.15});
document.querySelectorAll('.radar-wrapper').forEach(el=>skObs.observe(el));

// Stat counters
const stObs=new IntersectionObserver(e=>{e.forEach(x=>{if(x.isIntersecting){const el=x.target,target=parseInt(el.dataset.count),suffix=el.dataset.suffix||'';
let cur=0;const step=Math.max(1,Math.floor(target/30));
const t=setInterval(()=>{cur+=step;if(cur>=target){cur=target;clearInterval(t)}el.innerHTML=cur+`<span class="stat-plus">${suffix}</span>`},35);
stObs.unobserve(el)}})},{threshold:.5});
document.querySelectorAll('.stat-num').forEach(el=>stObs.observe(el));

// Nav active
const navObs=new IntersectionObserver(e=>{e.forEach(x=>{if(x.isIntersecting){const id=x.target.id||'hero';
document.querySelectorAll('.nav-links a').forEach(a=>{a.classList.toggle('act',a.getAttribute('href')==='#'+id)})}})},{threshold:.2});
document.querySelectorAll('.section, .hero').forEach(s=>navObs.observe(s));
document.querySelectorAll('a[href^="#"]').forEach(a=>{a.addEventListener('click',e=>{e.preventDefault();const t=document.querySelector(a.getAttribute('href'));if(t)t.scrollIntoView({behavior:'smooth'})})});

// ============ SCROLL PROGRESS BAR ============
const scrollFill = document.getElementById('scrollFill');
window.addEventListener('scroll', () => {
  const max = document.documentElement.scrollHeight - window.innerHeight;
  const pct = (window.scrollY / max) * 100;
  scrollFill.style.width = pct + '%';
}, { passive: true });

// ============ BACK TO TOP ============
const backTop = document.getElementById('backTop');
window.addEventListener('scroll', () => {
  backTop.classList.toggle('show', window.scrollY > 600);
}, { passive: true });
backTop.addEventListener('click', () => window.scrollTo({ top: 0, behavior: 'smooth' }));

// ============ PROJECT FILTER TABS ============
const filterBtns = document.querySelectorAll('.filter-btn');
const projCards = document.querySelectorAll('.proj[data-cats]');
filterBtns.forEach(btn => {
  btn.addEventListener('click', () => {
    filterBtns.forEach(b => b.classList.remove('active'));
    btn.classList.add('active');
    const filter = btn.dataset.filter;
    projCards.forEach(card => {
      if (filter === 'all' || card.dataset.cats.includes(filter)) {
        card.classList.remove('filter-hidden');
        card.classList.add('filter-show');
      } else {
        card.classList.add('filter-hidden');
        card.classList.remove('filter-show');
      }
    });
  });
});

// ============ HEATMAP TOOLTIPS ============
const hmTooltip = document.getElementById('hmTooltip');
const dayNames = ['Mon','Tue','Wed','Thu','Fri','Sat','Sun'];
const activityLabels = ['No activity','Light work','Moderate building','Heavy fabrication','Full build day'];
document.querySelectorAll('#heatmap .hm-cell').forEach((cell, idx) => {
  const weekIdx = Math.floor(idx / 7);
  const dayIdx = idx % 7;
  const weeksAgo = 25 - weekIdx;
  const d = new Date();
  d.setDate(d.getDate() - (weeksAgo * 7) - (6 - dayIdx));
  const dateStr = d.toLocaleDateString('en-US', { month: 'short', day: 'numeric', year: 'numeric' });
  const level = parseInt(cell.dataset.level || '0');

  cell.addEventListener('mouseenter', e => {
    hmTooltip.querySelector('.ht-date').textContent = dayNames[dayIdx] + ', ' + dateStr;
    hmTooltip.querySelector('.ht-val').textContent = activityLabels[level];
    hmTooltip.classList.add('show');
  });
  cell.addEventListener('mousemove', e => {
    hmTooltip.style.left = (e.clientX + 12) + 'px';
    hmTooltip.style.top = (e.clientY - 40) + 'px';
  });
  cell.addEventListener('mouseleave', () => hmTooltip.classList.remove('show'));
});

// ============ EXPANDABLE TIMELINE ============
document.querySelectorAll('.tl-item').forEach(item => {
  const toggle = item.querySelector('.tl-toggle');
  const expand = item.querySelector('.tl-expand');
  if (toggle && expand) {
    item.addEventListener('click', (e) => {
      // Don't interfere with tag links
      if (e.target.closest('.tl-tag')) return;
      const isOpen = item.classList.contains('expanded');
      // Close all others
      document.querySelectorAll('.tl-item.expanded').forEach(other => {
        other.classList.remove('expanded');
        other.querySelector('.tl-expand').classList.remove('open');
      });
      if (!isOpen) {
        item.classList.add('expanded');
        expand.classList.add('open');
      }
    });
  }
});

// ============ COMMAND CONSOLE ============
const cmdToggle = document.getElementById('cmdToggle');
const cmdBar = document.getElementById('cmdBar');
const cmdInput = document.getElementById('cmdInput');
const cmdOutput = document.getElementById('cmdOutput');
let cmdOpen = false;

function toggleConsole() {
  cmdOpen = !cmdOpen;
  cmdBar.classList.toggle('show', cmdOpen);
  if (cmdOpen) {
    setTimeout(() => {
      const barH = cmdBar.getBoundingClientRect().height;
      cmdToggle.style.bottom = (barH + 8) + 'px';
      cmdToggle.innerHTML = '<span>&#x2715;</span> Close Console <span class="kbd">Esc</span>';
      cmdInput.focus();
    }, 50);
  } else {
    cmdToggle.style.bottom = '1.5rem';
    cmdToggle.innerHTML = '<span>&#x2318;</span> Command Console <span class="kbd">Ctrl+K</span>';
  }
}
cmdToggle.addEventListener('click', toggleConsole);
document.addEventListener('keydown', e => {
  if ((e.ctrlKey || e.metaKey) && e.key === 'k') { e.preventDefault(); toggleConsole(); }
  if (e.key === 'Escape' && cmdOpen) toggleConsole();
});

function cmdPrint(html, cls) {
  const d = document.createElement('div');
  d.className = cls || '';
  d.innerHTML = html;
  cmdOutput.appendChild(d);
  cmdOutput.scrollTop = cmdOutput.scrollHeight;
  // Reposition toggle above growing console
  if (cmdOpen) {
    requestAnimationFrame(() => {
      const barH = cmdBar.getBoundingClientRect().height;
      cmdToggle.style.bottom = (barH + 8) + 'px';
    });
  }
}

const cmdHistArr = [];
let histIdx = -1;

const cmds = {
  help: () => {
    cmdPrint('<span class="co-hl">Available commands:</span>');
    cmdPrint('  <span class="co-cmd">help</span>            Show this list of commands');
    cmdPrint('  <span class="co-cmd">locate</span> &lt;section&gt;  Navigate to a section (home, about, timeline, projects, skills, contact)');
    cmdPrint('  <span class="co-cmd">inspect</span> &lt;project&gt; Open detailed project breakdown (pipboy, gtr, sentry, arm, sound)');
    cmdPrint('  <span class="co-cmd">contact</span>          Jump to contact info');
    cmdPrint('  <span class="co-cmd">whoami</span>           Quick bio');
    cmdPrint('  <span class="co-cmd">projects --list</span>  List all projects with status');
    cmdPrint('  <span class="co-cmd">skills --top</span>     Show top skills ranked');
    cmdPrint('  <span class="co-cmd">status</span>           Current build status');
    cmdPrint('  <span class="co-cmd">clear</span>            Clear console output');
  },
  locate: (args) => {
    const map = { home:'hero', about:'terminal-sec', timeline:'timeline', projects:'projects', skills:'skills', contact:'contact' };
    const t = args[0]?.toLowerCase();
    if (!t) { cmdPrint('<span class="co-err">Usage: locate &lt;section&gt;</span> -- Options: home, about, timeline, projects, skills, contact'); return; }
    const id = map[t];
    if (id) { document.getElementById(id).scrollIntoView({behavior:'smooth'}); cmdPrint('<span class="co-grn">Navigating to '+t+'...</span>'); }
    else cmdPrint('<span class="co-err">Unknown section "'+t+'".</span> Try: home, about, timeline, projects, skills, contact');
  },
  inspect: (args) => {
    const t = args[0]?.toLowerCase();
    if (!t) { cmdPrint('<span class="co-err">Usage: inspect &lt;project&gt;</span> -- Options: pipboy, gtr, echo, sentry, arm, sound'); return; }
    const data = projectData[t];
    if (data) { cmdPrint('<span class="co-grn">Opening '+data.title+'...</span>'); document.querySelector(`.proj[data-project="${t}"]`)?.click(); }
    else cmdPrint('<span class="co-err">Unknown project "'+t+'".</span> Try: pipboy, gtr, sentry, arm, sound');
  },
  contact: () => { document.getElementById('contact').scrollIntoView({behavior:'smooth'}); cmdPrint('<span class="co-grn">Navigating to contact...</span>'); },
  whoami: () => {
    cmdPrint('<span class="co-hl">Easton Drummonds</span>');
    cmdPrint('Junior in high school // Georgia');
    cmdPrint('Mechanical & Embedded Systems Engineer');
    cmdPrint('Focus: CAD, 3D printing, firmware, iterative prototyping');
    cmdPrint('Tools: Onshape, AutoCAD, Bambu H2D, ESP32, Arduino');
    cmdPrint('Currently building: Pip-Boy 3000 wearable computer');
  },
  status: () => {
    cmdPrint('<span class="co-hl">Current Build Status</span>');
    cmdPrint('  <span class="co-grn">[BUILT]</span>   Pip-Boy 3000 -- prototype complete, evaluating custom PCB');
    cmdPrint('  <span class="co-cmd">[LIVE]</span>    GT-R Brakelight -- 9+ months running');
    cmdPrint('  <span class="co-cmd">[7TH]</span>     Sediment Sentry v4 -- 7th at TSA State SLC');
    cmdPrint('  <span class="co-cmd">[READY]</span>   Robotic Arm -- materials purchased, awaiting build day');
    cmdPrint('  <span class="co-cmd">[DONE]</span>    Sound Alert Pro -- deployed');
    cmdPrint('  <span class="co-grn">[1ST]</span>     Wayward Echo -- 1st at State SLC, Nationals June 2026');
  },
  clear: () => { cmdOutput.innerHTML = ''; requestAnimationFrame(() => { const barH = cmdBar.getBoundingClientRect().height; cmdToggle.style.bottom = (barH + 8) + 'px'; }); },
  projects: (args) => {
    if (args[0]==='--list') {
      cmdPrint('<span class="co-hl">Project Registry</span>');
      cmdPrint('  01  Pip-Boy 3000         <span class="co-grn">[BUILT]</span>   Mechanical + Embedded');
      cmdPrint('  02  GT-R Brakelight      <span class="co-cmd">[LIVE]</span>    Automotive Engineering');
      cmdPrint('  03  Sediment Sentry      <span class="co-cmd">[7TH]</span>     Marine // 7th at State SLC');
      cmdPrint('  04  Robotic Arm          <span class="co-cmd">[READY]</span>   Materials purchased');
      cmdPrint('  05  Sound Alert Pro      <span class="co-cmd">[DONE]</span>    Sensor + AI');
      cmdPrint('  06  Wayward Echo         <span class="co-grn">[1ST]</span>     1st at State // Nationals');
      cmdPrint('Use <span class="co-cmd">inspect &lt;name&gt;</span> for details.');
    } else { document.getElementById('projects').scrollIntoView({behavior:'smooth'}); cmdPrint('<span class="co-grn">Navigating to projects...</span>'); }
  },
  skills: (args) => {
    if (args[0]==='--top') {
      cmdPrint('<span class="co-hl">Top Skills (ranked)</span>');
      cmdPrint('  1. 3D Printing (FDM)     <span class="co-hl">95%</span>');
      cmdPrint('  2. ESP32 / Arduino       <span class="co-hl">93%</span>');
      cmdPrint('  3. C / C++               <span class="co-hl">90%</span>');
      cmdPrint('  4. CAD (Onshape)         <span class="co-hl">88%</span>');
      cmdPrint('  5. Python                <span class="co-hl">88%</span>');
      cmdPrint('  6. Enclosure Design      <span class="co-hl">88%</span>');
    } else { document.getElementById('skills').scrollIntoView({behavior:'smooth'}); cmdPrint('<span class="co-grn">Navigating to skills...</span>'); }
  }
};

cmdInput.addEventListener('keydown', e => {
  if (e.key === 'Enter') {
    const raw = cmdInput.value.trim();
    if (!raw) return;
    cmdPrint('<span class="co-cmd">easton &gt;</span> ' + raw);
    cmdHistArr.unshift(raw); histIdx = -1;
    const parts = raw.split(/\s+/);
    const cmd = parts[0].toLowerCase();
    const args = parts.slice(1);
    if (cmds[cmd]) cmds[cmd](args);
    else cmdPrint('<span class="co-err">Unknown command: "'+cmd+'".</span> Type <span class="co-cmd">help</span> for available commands.');
    cmdInput.value = '';
  }
  if (e.key==='ArrowUp') { e.preventDefault(); if(histIdx<cmdHistArr.length-1){histIdx++;cmdInput.value=cmdHistArr[histIdx]} }
  if (e.key==='ArrowDown') { e.preventDefault(); if(histIdx>0){histIdx--;cmdInput.value=cmdHistArr[histIdx]}else{histIdx=-1;cmdInput.value=''} }
  if (e.key==='Tab') { e.preventDefault(); const v=cmdInput.value.toLowerCase();
    const all=['help','locate','inspect','contact','whoami','projects','skills','status','clear'];
    const m=all.find(c=>c.startsWith(v)); if(m)cmdInput.value=m+' '; }
});
</script>
</body>
</html>
