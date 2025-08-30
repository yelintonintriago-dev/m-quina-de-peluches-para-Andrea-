# m-quina-de-peluches-para-Andrea-
<!DOCTYPE html><html lang="es">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Máquina de Amor</title>
  <meta name="description" content="Una mini máquina de peluches romántica para jugar y declararte 💘" />
  <style>
    :root{
      --bg:#fff0f5;           /* rosado pastel del fondo */
      --machine:#c98bb9;      /* color de la máquina */
      --machine-dark:#a56e98; /* bordes y acentos */
      --glass:#ffe6f2aa;      /* vidrio */
      --heart:#ff3b6b;        /* corazones */
      --win:#4caf50;          /* verde éxito */
      --text:#2b2240;
    }*{box-sizing:border-box}
html,body{height:100%;margin:0;font-family:system-ui,-apple-system,Segoe UI,Roboto,Ubuntu,"Helvetica Neue",Arial}
body{
  background: radial-gradient(1200px 800px at 10% -10%, #ffd7ef 0%, #ffeaf6 40%, var(--bg) 80%),
              radial-gradient(900px 600px at 110% 20%, #ffd7ef 0%, var(--bg) 70%);
  color:var(--text);
  display:flex;align-items:center;justify-content:center; padding:24px;
}

.app{width:min(920px, 95vw);}

header{
  text-align:center; margin: 0 0 14px;
}
h1{font-size:clamp(22px,3.5vw,36px);margin:6px 0 2px}
.subtitle{opacity:.8;font-size:clamp(13px,2.2vw,16px)}

.machine-wrap{display:grid;grid-template-columns:1fr;gap:14px}

.machine{
  position:relative;
  margin:auto;
  width:min(460px, 92vw);
  aspect-ratio:3/4;
  background:linear-gradient(180deg, var(--machine) 0 80%, #d8a6c8 80%);
  border-radius:14px; box-shadow:0 14px 30px #00000018, inset 0 0 0 4px var(--machine-dark);
  overflow:hidden;
}

/* marco superior */
.top{position:absolute;left:0;top:0;width:100%;height:22%;background:linear-gradient(180deg,#f9cce2,#f3b7d8); border-bottom:6px solid var(--machine-dark)}
.title-led{position:absolute;inset:8px 12px auto;display:flex;gap:8px;align-items:center}
.led{width:10px;height:10px;border-radius:50%;background:#ffd1e6;box-shadow:0 0 8px #ffd1e6}

.glass{position:absolute;left:6%;top:24%;width:88%;height:48%;background:var(--glass);border:6px solid var(--machine-dark);border-radius:8px;overflow:hidden}

/* piso donde están los peluches */
.pit{position:absolute;left:6%;bottom:18%;width:88%;height:22%;background:linear-gradient(180deg,#b66da1,#804b78);border:6px solid var(--machine-dark);border-radius:10px}

/* chute de premio */
.chute{position:absolute;left:7%;bottom:4%;width:18%;height:12%;background:#76add8;border:6px solid #2d5b87;border-radius:6px}

/* controles */
.panel{position:absolute;right:8%;bottom:6%;display:flex;gap:10px;align-items:center}
.btn{
  -webkit-tap-highlight-color: transparent;
  user-select:none; border:none; outline:none; cursor:pointer;
  width:56px;height:56px;border-radius:12px; background:#f7e0ee; box-shadow:0 4px 0 #d9b8cd;
  display:grid;place-items:center;font-size:22px;font-weight:700;color:#6b2d59;
  transition:transform .05s ease; touch-action:manipulation;
}
.btn:active{transform:translateY(2px)}

/* garra */
.rail{position:absolute;left:8%;top:26%;width:84%;height:10px;background:linear-gradient(180deg,#e7c8da,#d1a7c1);border:3px solid var(--machine-dark);border-radius:8px}
.trolley{position:absolute;top:-12px;width:48px;height:24px;background:#e6c0d7;border:3px solid var(--machine-dark);border-radius:6px}
.rope{position:absolute;left:50%;transform:translateX(-50%);top:20px;width:3px;height:0;background:#333}
.claw{position:absolute;left:50%;transform:translateX(-50%);top:20px;width:36px;height:28px}
.claw::before,.claw::after{content:"";position:absolute;bottom:-6px;width:10px;height:22px;background:#333;border-radius:12px 12px 2px 2px}
.claw::before{left:2px;transform-origin:top right;}
.claw::after{right:2px;transform-origin:top left;}
.claw.open::before{transform:rotate(-18deg)}
.claw.open::after{transform:rotate(18deg)}
.claw.closed::before{transform:rotate(6deg)}
.claw.closed::after{transform:rotate(-6deg)}

/* juguetes */
.toy{position:absolute;width:48px;height:48px;border-radius:10px;display:grid;place-items:center;font-size:24px;filter:drop-shadow(0 3px 2px #0001)}
.toy:nth-child(odd){transform:rotate(-2deg)}

/* marcador */
.hud{display:flex;justify-content:center;gap:10px;margin:6px 0}
.badge{padding:8px 12px;border-radius:999px;background:#ffd3e7;font-weight:700;box-shadow:inset 0 -2px 0 #e3b1ca}

.toast{position:fixed;inset:auto 12px 12px;max-width:calc(100vw - 24px);background:#ffffff;border:2px solid #e4c3d7;border-radius:12px;padding:10px 14px;box-shadow:0 10px 26px #00000020;display:flex;gap:10px;align-items:center;font-weight:600}
.toast.hide{display:none}

.footer{margin-top:10px;text-align:center;font-size:13px;opacity:.8}
.footer a{color:#a33779}

/* confeti corazones */
.heart{position:fixed;pointer-events:none;opacity:0.9}
@keyframes pop{
  0%{transform:translateY(0) scale(.8);opacity:0}
  10%{opacity:1}
  100%{transform:translateY(-140vh) scale(1.1);opacity:0}
}

.music-btn{position:fixed;right:12px;top:12px;z-index:10;border:none;border-radius:999px;padding:10px 12px;background:#ffffffcc;backdrop-filter:blur(6px);box-shadow:0 6px 16px #0002;cursor:pointer;font-size:18px} .music-btn:active{transform:translateY(1px)} </style>

</head>
<body>
  <div class="app">
    <header>
      <h1>🎁 Máquina de Amor</h1>
      <div class="subtitle" id="tagline">Atrapa un regalo para tu amor</div>
    </header><div class="hud">
  <div class="badge">❤️ <span id="score">0</span> premios</div>
  <div class="badge">Intentos: <span id="tries">0</span></div>
</div>

<div class="machine-wrap">
  <div class="machine" id="machine">
    <div class="top">
      <div class="title-led">
        <div class="led"></div><div class="led"></div><div class="led"></div>
      </div>
    </div>

    <div class="glass" id="glass"></div>
    <div class="pit" id="pit"></div>
    <div class="chute" id="chute"></div>

    <div class="rail" id="rail">
      <div class="trolley" id="trolley">
        <div class="rope" id="rope"></div>
        <div class="claw open" id="claw"></div>
      </div>
    </div>

    <div class="panel">
      <button class="btn" id="left" aria-label="Izquierda">◀</button>
      <button class="btn" id="drop" aria-label="Bajar">⬇</button>
      <button class="btn" id="right" aria-label="Derecha">▶</button>
    </div>
  </div>
</div>

<div class="footer">
  Personaliza el enlace con <code>?para=Nombre</code> —
  <a href="#" id="copyLink">copiar mi enlace</a>
</div>

  </div>  <div class="toast hide" id="toast">Pulsa y mantén ◀ ▶ para mover. Toca ⬇ para bajar la garra.</div>  <!-- Música de fondo (YouTube) --><button class="music-btn" id="musicBtn" title="Música">🔇</button>

  <div style="position:absolute;width:0;height:0;overflow:hidden">
    <iframe id="bgMusic" src="https://www.youtube.com/embed/CwGbMYLjIpQ?autoplay=1&loop=1&playlist=CwGbMYLjIpQ&mute=1&controls=0&modestbranding=1" allow="autoplay" frameborder="0"></iframe>
  </div><script>
(function(){
  // ===== Utilidad: parámetros =====
  const qs = new URLSearchParams(location.search);
  const target = (qs.get('para')||'tu persona especial').trim();
  document.getElementById('tagline').textContent = `Atrapa un regalo para ${target} 💖`;

  // ===== Referencias DOM =====
  const machine = document.getElementById('machine');
  const rail = document.getElementById('rail');
  const trolley = document.getElementById('trolley');
  const rope = document.getElementById('rope');
  const claw = document.getElementById('claw');
  const pit = document.getElementById('pit');
  const glass = document.getElementById('glass');
  const chute = document.getElementById('chute');
  const btnLeft = document.getElementById('left');
  const btnRight = document.getElementById('right');
  const btnDrop = document.getElementById('drop');
  const scoreEl = document.getElementById('score');
  const triesEl = document.getElementById('tries');
  const toast = document.getElementById('toast');
  const musicBtn = document.getElementById('musicBtn');
  const music = document.getElementById('bgMusic');
  let musicMuted = true;

  // ===== Estado del juego =====
  let running = false;           // animación
  let dropping = false;          // está bajando/subiendo
  let moveDir = 0;               // -1 izquierda, 1 derecha
  let x = 16;                    // px relativo al rail
  let y = 0;                     // alto del cable
  let speed = 2.2;               // px por frame
  let score = 0;                 // premios
  let tries = 0;                 // intentos
  const railBounds = {min: 8, max: rail.clientWidth - 56};

  const EMOJIS = ['🧸','🐼','💖','🐱','🦄','🐶','💘','🐻','🎁','💝'];

  function rand(min,max){return Math.random()*(max-min)+min}

  // Crear juguetes aleatorios en el área de la vitrina
  const toys = [];
  function placeToys(){
    const n = 8 + Math.floor(Math.random()*4);
    const rect = glass.getBoundingClientRect();
    const padX = 16, padY = 10;
    for(let i=0;i<n;i++){
      const d = document.createElement('div');
      d.className='toy'; d.textContent = EMOJIS[i%EMOJIS.length];
      glass.appendChild(d);
      const gx = rand(padX, rect.width - padX - 48);
      const gy = rand( rect.height*0.10, rect.height*0.72);
      d.style.left = gx+ 'px';
      d.style.top  = gy+ 'px';
      toys.push(d);
    }
  }

  function reset(){
    toys.forEach(t=>t.remove()); toys.length=0; placeToys();
    score=0; tries=0; y=0; x=16; moveDir=0; updateHUD();
    trolley.style.left = x + 'px'; rope.style.height = '0px';
    claw.classList.remove('closed'); claw.classList.add('open');
  }

  function updateHUD(){scoreEl.textContent=score; triesEl.textContent=tries}

  // ===== Entrada (teclado + táctil) =====
  function pressLeft(){moveDir=-1}
  function pressRight(){moveDir=1}
  function release(){moveDir=0}

  btnLeft.addEventListener('mousedown',pressLeft); btnLeft.addEventListener('touchstart',pressLeft, {passive:true});
  btnRight.addEventListener('mousedown',pressRight); btnRight.addEventListener('touchstart',pressRight, {passive:true});
  [btnLeft,btnRight].forEach(b=>{b.addEventListener('mouseup',release);b.addEventListener('mouseleave',release);b.addEventListener('touchend',release)});

  window.addEventListener('keydown',e=>{if(e.key==='ArrowLeft')pressLeft(); if(e.key==='ArrowRight')pressRight(); if(e.key===' '||e.key==='ArrowDown') doDrop();});
  window.addEventListener('keyup',e=>{if(e.key==='ArrowLeft'&&moveDir<0)release(); if(e.key==='ArrowRight'&&moveDir>0)release();});

  btnDrop.addEventListener('click',()=>doDrop());

  function doDrop(){
    if(dropping) return;
    dropping = true; tries++; updateHUD();
    toast.classList.add('hide');
  }

  // ===== Animación principal =====
  function loop(){
    running = true;
    // mover en X
    if(!dropping){
      x += moveDir*speed*2.2;
      x = Math.max(railBounds.min, Math.min(railBounds.max, x));
      trolley.style.left = x + 'px';
    }

    // bajada/subida de la garra
    const maxRope = glass.offsetTop + glass.clientHeight - rail.offsetTop - 30; // límite inferior dentro del vidrio
    if(dropping){
      if(y < maxRope){ y += speed*2.4; } else { catchAttempt(); y = Math.max(0, y - speed*2.8); if(y<=0){dropping=false; claw.classList.add('open'); claw.classList.remove('closed');} }
    } else { if(y>0){ y = Math.max(0, y - speed*2.2); }
    }
    rope.style.height = y + 'px';

    requestAnimationFrame(loop);
  }

  // ===== Lógica de captura =====
  function catchAttempt(){
    // Punto de agarre en coordenadas relativas al vidrio
    const glassRect = glass.getBoundingClientRect();
    const railRect = rail.getBoundingClientRect();
    const hookX = (railRect.left + x + 24) - glassRect.left;
    const hookY = (railRect.top + 20 + y) - glassRect.top;

    // buscar el juguete más cercano
    let best=null, bestDist=9999;
    for(const t of toys){
      const tx = parseFloat(t.style.left) + t.clientWidth/2;
      const ty = parseFloat(t.style.top) + t.clientHeight/2;
      const dx = tx-hookX, dy = ty-hookY; const dist = Math.hypot(dx,dy);
      if(dist < bestDist){best=t; bestDist=dist}
    }

    // éxito si estamos cerca del centro y un poco de suerte
    if(best && bestDist < 32 && Math.random() < 0.85){
      claw.classList.remove('open'); claw.classList.add('closed');
      pick(best);
    }
  }

  function pick(el){
    // enganchar al gancho mientras sube
    const glassRect = glass.getBoundingClientRect();
    const railRect = rail.getBoundingClientRect();

    let rafId; const follow=()=>{
      const hookX = (railRect.left + x + 24) - glassRect.left - el.clientWidth/2;
      const hookY = (railRect.top + 20 + y) - glassRect.top - el.clientHeight/2 + 12;
      el.style.left = hookX + 'px';
      el.style.top  = hookY + 'px';
      if(dropping || y>0){ rafId = requestAnimationFrame(follow); } else { cancelAnimationFrame(rafId); dropIntoChute(el); }
    };
    follow();
  }

  function dropIntoChute(el){
    // animar hacia el chute
    const cr = chute.getBoundingClientRect();
    const gr = glass.getBoundingClientRect();
    const targetX = (cr.left - gr.left) + cr.width/2 - el.clientWidth/2;
    const targetY = (cr.top - gr.top) + 4;

    el.style.transition = 'transform .5s ease-in, opacity .5s ease-in';
    const curX = parseFloat(el.style.left), curY = parseFloat(el.style.top);
    const dx = targetX - curX, dy = targetY - curY;
    el.style.transform = `translate(${dx}px, ${dy}px)`;
    el.style.opacity = '0.2';

    setTimeout(()=>{ el.remove(); heartConfetti(); score++; updateHUD(); }, 520);
  }

  function heartConfetti(){
    for(let i=0;i<24;i++){
      const s = document.createElement('div');
      s.className='heart'; s.textContent = Math.random()>0.2 ? '💖' : '💘';
      s.style.left = rand(10, 90) + 'vw';
      s.style.bottom = '-10vh';
      s.style.fontSize = rand(18,36) + 'px';
      s.style.animation = `pop ${rand(1.8,3.2)}s linear forwards`;
      document.body.appendChild(s);
      setTimeout(()=>s.remove(), 3600);
    }
  }

  // Copiar enlace personalizado
  document.getElementById('copyLink').addEventListener('click',e=>{
    e.preventDefault();
    const name = prompt('¿Para quién es? Escribe el nombre:', target) || target;
    const url = `${location.origin}${location.pathname}?para=${encodeURIComponent(name)}`;
    navigator.clipboard.writeText(url).then(()=>{
      toast.textContent = 'Enlace copiado: pégalo en tu chat ✨';
      toast.classList.remove('hide');
      setTimeout(()=>toast.classList.add('hide'), 2600);
    });
  });

  // Mostrar ayuda inicial (1 vez)
  setTimeout(()=>toast.classList.remove('hide'), 800);
  setTimeout(()=>toast.classList.add('hide'), 4800);

  // Inicio
  placeToys();

  // Música: alternar mute/unmute (autoplay permitido en mute). Reinicia el iframe para aplicar el cambio.
  musicBtn.addEventListener('click', ()=>{
    musicMuted = !musicMuted;
    const base = 'https://www.youtube.com/embed/CwGbMYLjIpQ';
    const params = `?autoplay=1&loop=1&playlist=CwGbMYLjIpQ&controls=0&modestbranding=1&mute=${musicMuted?1:0}`;
    music.src = base + params;
    musicBtn.textContent = musicMuted ? '🔇' : '🔊';
  });
  trolley.style.left = x + 'px';
  if(!running) requestAnimationFrame(loop);
  
})();
</script></body>
</html>
