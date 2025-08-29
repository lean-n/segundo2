<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="utf-8" />
<meta name="viewport" content="width=device-width, initial-scale=1" />
<title>Flyer - Consola</title>
<style>
  :root{
    --bg:#0b0f10;
    --panel:#0e1416;
    --text:#d1f7c4;
    --muted:#7aa37a;
    --accent:#2ee55f;
  }
  *{box-sizing:border-box}
  html,body{height:100%;margin:0}
  body{
    background: radial-gradient(1200px 800px at 50% 40%, #0f171a 0%, var(--bg) 60%);
    font-family: ui-monospace, SFMono-Regular, Menlo, Consolas, "Liberation Mono", monospace;
    color: var(--text);
    display:flex;
    align-items:center;
    justify-content:center;
    padding:24px;
  }
  .terminal{
    width:min(900px, 95vw);
    border-radius:12px;
    overflow:hidden;
    box-shadow: 0 10px 40px rgba(0,0,0,.6), inset 0 0 0 1px rgba(255,255,255,.04);
    background: var(--panel);
    position:relative;
  }
  .titlebar{
    display:flex;align-items:center;gap:8px;
    height:38px;padding:0 12px;
    background: linear-gradient(180deg, #121a1d, #0b1214);
    border-bottom:1px solid rgba(255,255,255,.06);
  }
  .dot{width:12px;height:12px;border-radius:50%}
  .dot.red{background:#ff5f56}
  .dot.yellow{background:#ffbd2e}
  .dot.green{background:#27c93f}
  .title{
    margin-left:8px;
    font-size:12px;
    color:#9fb8a4;
    letter-spacing:.3px;
  }
  .screen{
    position:relative;
    padding:28px;
    font-size: clamp(16px, 2.6vw, 22px);
    line-height:1.5;
    text-shadow: 0 0 8px rgba(46,229,95,.25);
  }
  .scanline{
    pointer-events:none;
    position:absolute;inset:0;
    background-image: repeating-linear-gradient(
      to bottom, rgba(255,255,255,0.06), rgba(255,255,255,0.06) 1px,
      rgba(0,0,0,0) 1px, rgba(0,0,0,0) 3px
    );
    mix-blend-mode: soft-light;
    opacity:.15;
  }
  .glow:before{
    content:"";
    position:absolute;inset:-40px;
    background: radial-gradient(600px 200px at 50% 0%, rgba(46,229,95,.15), transparent 60%);
    pointer-events:none;
  }
  .prompt{
    color:var(--muted);
  }
  .cmd{
    color:var(--text);
  }
  .k{color:var(--accent)}
  .cursor{
    display:inline-block;
    width:.6ch;height:1em;transform:translateY(2px);
    background: var(--accent);
    margin-left:.15ch;
    animation: blink 1s steps(1) infinite;
  }
  @keyframes blink{50%{opacity:0}}
  .grid{
    display:grid;
    grid-template-columns: 1fr;
    gap:.7em;
  }
  /* Print tweaks */
  @media print{
    body{background:white}
    .terminal{box-shadow:none}
    .scanline{opacity:.05}
  }
</style>
</head>
<body>
  <div class="terminal glow" role="img" aria-label="Flyer con estÃ©tica de consola">
    <div class="titlebar">
      <div class="dot red"></div>
      <div class="dot yellow"></div>
      <div class="dot green"></div>
      <div class="title">bash â€” flyer.sh</div>
    </div>
    <div class="screen">
      <div class="grid">
        <div><span class="prompt">$</span> <span class="cmd">echo <span class="k">&quot;JUANA MOLINA&quot;</span></span></div>
        <div><span class="prompt">$</span> <span class="cmd">echo <span class="k">&quot;Segundo&quot;</span></span></div>
        <div><span class="prompt">$</span> <span class="cmd">echo <span class="k">&quot;DirecciÃ³n por privado&quot;</span></span></div>
        <div><span class="prompt">$</span> <span class="cmd">echo <span class="k">&quot;Entrada con bono contribuciÃ³n&quot;</span></span></div>
        <div><span class="prompt">$</span> <span class="cmd">echo <span class="k">&quot;Traer un alimento no perecedero&quot;</span></span></div>
        <div><span class="prompt">$</span> <span class="cmd">echo <span class="k">&quot;DOMINGO 7; 18HS&quot;</span></span><span class="cursor"></span></div>
      </div>
      <div class="scanline"></div>
    </div>
  </div>
</body>
</html>
