<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">
<title>For Pranjal 💌</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Fraunces:ital,opsz,wght@0,9..144,600;1,9..144,500&family=Gaegu:wght@400;700&display=swap" rel="stylesheet">
<style>
  :root {
    --blush: #ffd9e3;
    --berry: #8a1c4f;
    --butter: #ffeaa8;
    --sky: #d3e9ff;
    --ink: #3d1231;
    --paper: #fffafc;
    --leaf: #4f9d69;
    --tulip: #ff5b7f;
    --display: "Fraunces", Georgia, serif;
    --hand: "Gaegu", "Comic Sans MS", cursive;
  }
  * { box-sizing: border-box; margin: 0; }
  html { scroll-behavior: smooth; height: 100%; }
  body {
    background: var(--blush);
    color: var(--ink);
    font-family: var(--hand);
    font-size: 1.35rem;
    line-height: 1.5;
    min-height: 100%;
    overflow-x: hidden;
    padding: env(safe-area-inset-top) 0 env(safe-area-inset-bottom);
  }
  h1, h2 { font-family: var(--display); font-weight: 600; line-height: 1.15; }
  section { padding: 4.5rem 1.25rem; max-width: 640px; margin: 0 auto; text-align: center; }
  section h2 { font-size: clamp(1.7rem, 6vw, 2.3rem); }
  .hint { opacity: .75; }
  :focus-visible { outline: 3px solid var(--berry); outline-offset: 3px; }
  [hidden] { display: none !important; }

  /* ---------- Envelope ---------- */
  #hero { min-height: 100svh; display: flex; flex-direction: column; align-items: center; justify-content: center; gap: 1.5rem; }
  #hero h1 { font-size: clamp(2rem, 8vw, 3.2rem); }
  .envelope {
    position: relative; width: min(84vw, 340px); aspect-ratio: 4/3;
    background: var(--butter); border-radius: 10px; border: 3px solid var(--ink);
    cursor: pointer; padding: 0; font: inherit; color: inherit;
    box-shadow: 6px 6px 0 var(--ink); transition: transform .2s;
  }
  .envelope:hover { transform: rotate(-1.5deg); }
  .envelope .flap {
    position: absolute; inset: 0 0 auto 0; height: 58%;
    background: #ffdf7e; clip-path: polygon(0 0, 100% 0, 50% 100%);
    transform-origin: top; transition: transform .6s ease; z-index: 3;
  }
  .envelope .front {
    position: absolute; inset: 0; z-index: 2; border-radius: 8px;
    background: linear-gradient(to top right, transparent 49.5%, var(--ink) 50%, transparent 50.6%),
                linear-gradient(to top left, transparent 49.5%, var(--ink) 50%, transparent 50.6%);
    background-size: 50% 62%; background-position: left bottom, right bottom; background-repeat: no-repeat;
  }
  .seal {
    position: absolute; left: 50%; top: 50%; z-index: 4; transform: translate(-50%, -50%);
    width: 64px; height: 64px; border-radius: 50%; background: var(--berry);
    border: 3px solid var(--ink); display: grid; place-items: center; font-size: 1.9rem;
    transition: opacity .3s; animation: beat 1.6s ease-in-out infinite;
  }
  @keyframes beat { 50% { transform: translate(-50%, -50%) scale(1.12); } }
  .envelope.open { pointer-events: none; }
  .envelope.open .flap { transform: rotateX(180deg); z-index: 1; }
  .envelope.open .seal { opacity: 0; animation: none; }

  /* ---------- Letter ---------- */
  #letter.show { animation: rise .8s ease both; }
  @keyframes rise { from { opacity: 0; transform: translateY(40px); } }
  .paper {
    background: var(--paper); border: 3px solid var(--ink); border-radius: 14px;
    padding: 2rem 1.5rem; box-shadow: 6px 6px 0 var(--ink); text-align: left;
    background-image: repeating-linear-gradient(transparent 0 1.9rem, #f6d3df 1.9rem calc(1.9rem + 2px));
    line-height: 1.9rem;
  }
  .paper h2 { font-size: 1.8rem; margin-bottom: 1rem; line-height: 2.4rem; }
  .paper p + p { margin-top: 1.9rem; }
  .sign { text-align: right; margin-top: 1.9rem; font-weight: 700; }

  /* ---------- Counter ---------- */
  .counter { display: flex; gap: .75rem; justify-content: center; flex-wrap: wrap; margin-top: 1.5rem; }
  .counter div, .chip {
    background: var(--sky); border: 3px solid var(--ink); border-radius: 16px;
    padding: .6rem 1rem; min-width: 5.2rem; box-shadow: 4px 4px 0 var(--ink);
  }
  .counter b { display: block; font-family: var(--display); font-size: 2rem; }
  .milestones { display: grid; gap: 1rem; margin-top: 2rem; }
  .chip { background: var(--butter); text-align: left; display: flex; gap: .9rem; align-items: center; }
  .chip:nth-child(2) { background: #ffc2d4; }
  .chip .em { font-size: 2rem; }
  .chip small { display: block; font-size: 1.1rem; opacity: .8; }

  /* ---------- Favourites ---------- */
  .cards { display: grid; grid-template-columns: repeat(auto-fit, minmax(160px, 1fr)); gap: 1rem; margin-top: 1.75rem; }
  .card { perspective: 700px; background: none; border: 0; padding: 0; font: inherit; color: inherit; cursor: pointer; }
  .card .in { position: relative; display: block; height: 170px; transition: transform .5s; transform-style: preserve-3d; }
  .card.flipped .in { transform: rotateY(180deg); }
  .card .face {
    position: absolute; inset: 0; display: grid; place-items: center; padding: .9rem;
    border: 3px solid var(--ink); border-radius: 16px; backface-visibility: hidden; box-shadow: 4px 4px 0 var(--ink);
  }
  .card .back { transform: rotateY(180deg); background: var(--paper); font-size: 1.15rem; line-height: 1.3; }
  .card .front { font-size: 2.6rem; align-content: center; }
  .card .front span { display: block; font-size: 1.2rem; font-family: var(--display); }
  .card:nth-child(4n+1) .front { background: var(--butter); }
  .card:nth-child(4n+2) .front { background: var(--sky); }
  .card:nth-child(4n+3) .front { background: #ffc2d4; }
  .card:nth-child(4n) .front { background: #d8f0d2; }

  /* ---------- Garden ---------- */
  #gardenBox {
    position: relative; height: 300px; margin-top: 1.5rem; overflow: hidden; cursor: pointer;
    border: 3px solid var(--ink); border-radius: 20px; box-shadow: 6px 6px 0 var(--ink);
    background: linear-gradient(var(--sky) 0 72%, #9ad19a 72% 100%);
    touch-action: manipulation;
  }
  #gardenBox svg.bloom { position: absolute; transform-origin: 50% 100%; animation: grow .7s cubic-bezier(.3,1.6,.5,1) both; pointer-events: none; }
  @keyframes grow { from { transform: scale(0); } }
  .sun { position: absolute; right: 18px; top: 14px; font-size: 2.2rem; }
  .garden-count { margin-top: 1rem; }
  .linkbtn {
    display: inline-block; margin-top: 1.25rem; text-decoration: none; font-weight: 700;
  }

  /* ---------- Question ---------- */
  #ask { padding-bottom: 6rem; }
  .btns { display: flex; gap: 1rem; justify-content: center; align-items: center; margin-top: 2rem; min-height: 4.5rem; flex-wrap: wrap; }
  button.pill, a.pill {
    font: inherit; font-weight: 700; font-size: 1.4rem; padding: .6rem 1.6rem; cursor: pointer;
    border: 3px solid var(--ink); border-radius: 999px; box-shadow: 4px 4px 0 var(--ink); color: var(--ink);
    background: var(--butter); text-decoration: none; display: inline-block;
  }
  button.pill:active { transform: translate(3px, 3px); box-shadow: 1px 1px 0 var(--ink); }
  .yes { background: var(--berry) !important; color: #fff !important; transition: transform .2s; }
  .no { background: var(--paper) !important; }
  #answer { display: none; margin-top: 1.5rem; }
  #answer.show { display: block; animation: rise .6s ease both; }
  #answer h2 { margin-bottom: .5rem; }

  /* ---------- Birthday ---------- */
  #bday .chip { justify-content: center; text-align: center; display: inline-flex; flex-direction: column; gap: .2rem; padding: 1rem 1.6rem; background: var(--butter); }
  #bday .chip b { font-family: var(--display); font-size: 2.6rem; line-height: 1; }

  /* ---------- Hearts ---------- */
  .heart { position: fixed; pointer-events: none; z-index: 50; font-size: 1.6rem; animation: float 2.4s ease-out forwards; }
  @keyframes float { to { transform: translate(var(--dx), -85vh) rotate(var(--r)); opacity: 0; } }
  footer { text-align: center; padding: 0 1rem 3rem; opacity: .7; }

  @media (prefers-reduced-motion: reduce) {
    *, *::before, *::after { animation: none !important; transition: none !important; }
    .heart { display: none; }
  }
</style>
</head>
<body>

<!-- ✏️ Edit the CONFIG in the <script> at the bottom to change any text, date, or link ✏️ -->

<section id="hero">
  <h1 id="heroTitle">Hey Pranjal… this is for you</h1>
  <button class="envelope" id="envelope" aria-label="Open the letter">
    <span class="flap"></span><span class="front"></span><span class="seal">💗</span>
  </button>
  <p class="hint" id="hint">tap the heart</p>
</section>

<section id="letter" hidden aria-live="polite">
  <div class="paper">
    <h2 id="letterTitle"></h2>
    <div id="letterBody"></div>
    <p class="sign" id="letterSign"></p>
  </div>
</section>

<section id="together" hidden>
  <h2>Us, so far</h2>
  <div class="counter" id="counter" aria-live="off"></div>
  <div class="milestones">
    <div class="chip"><span class="em">🌷</span><div id="m1"></div></div>
    <div class="chip"><span class="em">💍</span><div id="m2"></div></div>
  </div>
</section>

<section id="loves" hidden>
  <h2>All the things you love</h2>
  <p class="hint">tap a card</p>
  <div class="cards" id="cards"></div>
</section>

<section id="garden" hidden>
  <h2>A little garden for you</h2>
  <p class="hint">tap anywhere to plant tulips &amp; lilies</p>
  <div id="gardenBox" role="button" tabindex="0" aria-label="Tap to plant a flower">
    <span class="sun">☀️</span>
  </div>
  <p class="garden-count" id="gardenCount">0 flowers planted</p>
  <a class="pill linkbtn" id="playlistBtn" target="_blank" rel="noopener" hidden>🎧 Our song corner</a>
</section>

<section id="ask" hidden>
  <h2 id="question"></h2>
  <div class="btns" id="btns">
    <button class="pill yes" id="yes">Yes 💖</button>
    <button class="pill no" id="no">No</button>
  </div>
  <div id="answer">
    <h2 id="answerTitle"></h2>
    <p id="answerText"></p>
  </div>
</section>

<section id="bday" hidden>
  <h2>Your birthday is coming</h2>
  <p style="margin-top:1rem"><span class="chip"><b id="bdayDays">0</b><span>days to go 🎂</span></span></p>
  <p style="margin-top:1.25rem" id="bdayText"></p>
</section>

<footer id="footer" hidden>made with love (and a little code)</footer>

<script>
/* ============================================================
   ✏️  EDIT ME
   ============================================================ */
const CONFIG = {
  herName: "Pranjal",
  yourName: "Me",                          // 👈 put your name / nickname here
  metDate: "2026-02-28T00:00:00",          // day it all began
  gfDate: "2026-04-03T00:00:00",           // day she became my girlfriend
  birthday: { month: 1, day: 16 },         // 16 January
  playlistUrl: "",                         // 👈 paste a Spotify link (e.g. a Marías playlist) or leave empty

  letterTitle: "Dear {name},",
  letter: [
    "I made you this tiny corner of the internet because you deserve something that's just yours.",
    "Six months with you, and every day still feels like the good part of the story. Thank you for being you, my favourite person.",
    "Scroll down. I filled it with the things you love."
  ],
  sign: "Forever yours, {you} 💌",

  loves: [
    { icon: "🌷", title: "Tulips", text: "Soft, bright and a little dramatic. So basically you." },
    { icon: "🤍", title: "Lilies", text: "Elegant and calming. I'd bring you a bouquet every week." },
    { icon: "⚔️", title: "Attack on Titan", text: "You'd fight a whole wall of titans for the people you love. Same energy." },
    { icon: "🎶", title: "The Marías", text: "Dreamy, late night drive songs. Every one of them sounds like you." },
    { icon: "🥟", title: "Momos", text: "Steamed, fried, tandoori, I'm in for all of them if you're across the plate." },
    { icon: "🧸", title: "Plushies", text: "I'm officially applying to be your biggest, huggiest plushie." }
  ],

  question: "Will you keep being my favourite person?",
  yesTitle: "YAYYY 🎉",
  yesText: "Best decision ever. I love you so much, {name}. 💗",
  noDodges: ["Are you sure? 🥺", "Think again 😌", "Nope, wrong button", "Try the pink one 💖", "Pretty please? 🧸"],

  birthdayText: "Get ready. There will be flowers, momos and way too many plushies. 🎁"
};
/* ============================================================ */

const $ = (id) => document.getElementById(id);
const fill = (s) => s.replaceAll("{name}", CONFIG.herName).replaceAll("{you}", CONFIG.yourName);
const reduced = matchMedia("(prefers-reduced-motion: reduce)").matches;
const fmt = (d) => d.toLocaleDateString(undefined, { day: "numeric", month: "long", year: "numeric" });

document.title = "For " + CONFIG.herName + " 💌";
$("heroTitle").textContent = "Hey " + CONFIG.herName + "… this is for you";

/* Hearts */
function burst(x, y, n = 14) {
  if (reduced) return;
  const set = ["💖", "💗", "💕", "🌷", "🤍", "✨", "🧸", "🥟"];
  for (let i = 0; i < n; i++) {
    const h = document.createElement("span");
    h.className = "heart";
    h.textContent = set[Math.floor(Math.random() * set.length)];
    h.style.left = x + "px"; h.style.top = y + "px";
    h.style.setProperty("--dx", (Math.random() * 240 - 120) + "px");
    h.style.setProperty("--r", (Math.random() * 90 - 45) + "deg");
    h.style.animationDelay = (Math.random() * 0.3) + "s";
    document.body.appendChild(h);
    setTimeout(() => h.remove(), 3000);
  }
}

/* Open envelope */
$("envelope").addEventListener("click", () => {
  const env = $("envelope");
  env.classList.add("open");
  $("hint").textContent = "scroll down 💗";
  const r = env.getBoundingClientRect();
  burst(r.left + r.width / 2, r.top + r.height / 2, 18);

  $("letterTitle").textContent = fill(CONFIG.letterTitle);
  $("letterBody").innerHTML = CONFIG.letter.map(() => "<p></p>").join("");
  [...$("letterBody").children].forEach((el, i) => el.textContent = fill(CONFIG.letter[i]));
  $("letterSign").textContent = fill(CONFIG.sign);

  ["letter", "together", "loves", "garden", "ask", "bday", "footer"].forEach((id) => $(id).hidden = false);
  $("letter").classList.add("show");
  setTimeout(() => $("letter").scrollIntoView({ behavior: reduced ? "auto" : "smooth", block: "start" }), 700);
}, { once: true });

/* Counter + milestones */
const met = new Date(CONFIG.metDate), gf = new Date(CONFIG.gfDate);
$("m1").innerHTML = `Our first day<small>${fmt(met)}</small>`;
$("m2").innerHTML = `You became my girlfriend<small>${fmt(gf)}</small>`;
function tick() {
  let diff = Math.max(0, Date.now() - met.getTime());
  const d = Math.floor(diff / 864e5); diff %= 864e5;
  const h = Math.floor(diff / 36e5); diff %= 36e5;
  const m = Math.floor(diff / 6e4);
  const s = Math.floor((diff % 6e4) / 1e3);
  $("counter").innerHTML = [["days", d], ["hours", h], ["mins", m], ["secs", s]]
    .map(([l, v]) => `<div><b>${v}</b>${l}</div>`).join("");
}
tick(); setInterval(tick, 1000);

/* Favourite cards */
CONFIG.loves.forEach((r) => {
  const b = document.createElement("button");
  b.className = "card";
  b.setAttribute("aria-pressed", "false");
  b.innerHTML = `<span class="in"><span class="face front"></span><span class="face back"></span></span>`;
  b.querySelector(".front").innerHTML = `${r.icon}<span></span>`;
  b.querySelector(".front span").textContent = r.title;
  b.querySelector(".back").textContent = r.text;
  b.addEventListener("click", (e) => {
    const on = b.classList.toggle("flipped");
    b.setAttribute("aria-pressed", on);
    if (on) burst(e.clientX, e.clientY, 5);
  });
  $("cards").appendChild(b);
});

/* Garden */
function tulipSVG(color) {
  return `<svg class="bloom" width="46" height="90" viewBox="0 0 46 90" aria-hidden="true">
    <path d="M23 88 C23 70 22 56 23 40" stroke="#2f7d4a" stroke-width="4" fill="none" stroke-linecap="round"/>
    <path d="M23 76 C10 72 6 62 8 54 C18 58 22 66 23 76Z" fill="#4f9d69" stroke="#3d1231" stroke-width="2"/>
    <path d="M9 12 C9 30 14 42 23 42 C32 42 37 30 37 12 L30 20 L23 8 L16 20Z" fill="${color}" stroke="#3d1231" stroke-width="2.5" stroke-linejoin="round"/>
  </svg>`;
}
function lilySVG() {
  const petals = [0, 60, 120, 180, 240, 300].map(a =>
    `<ellipse cx="23" cy="14" rx="5.5" ry="13" transform="rotate(${a} 23 27)" fill="#fffafc" stroke="#3d1231" stroke-width="2"/>`).join("");
  return `<svg class="bloom" width="46" height="90" viewBox="0 0 46 90" aria-hidden="true">
    <path d="M23 88 C23 70 24 56 23 34" stroke="#2f7d4a" stroke-width="4" fill="none" stroke-linecap="round"/>
    <path d="M23 74 C36 70 40 60 38 52 C28 56 24 64 23 74Z" fill="#4f9d69" stroke="#3d1231" stroke-width="2"/>
    ${petals}
    <circle cx="23" cy="27" r="4" fill="#ffb84d" stroke="#3d1231" stroke-width="1.5"/>
  </svg>`;
}
const tulipColors = ["#ff5b7f", "#ff8fb0", "#ffb84d", "#c77dff", "#ff6b6b"];
let planted = 0;
function plant(x, y) {
  const box = $("gardenBox");
  const wrap = document.createElement("div");
  const isLily = Math.random() < 0.4;
  wrap.innerHTML = isLily ? lilySVG() : tulipSVG(tulipColors[Math.floor(Math.random() * tulipColors.length)]);
  const svg = wrap.firstElementChild;
  const w = 46, h = 90;
  const left = Math.min(Math.max(x - w / 2, 0), box.clientWidth - w);
  const groundTop = box.clientHeight * 0.72;
  const bottom = Math.min(Math.max(y + 10, groundTop + 10), box.clientHeight - 6);
  svg.style.left = left + "px";
  svg.style.top = (bottom - h) + "px";
  svg.style.zIndex = Math.round(bottom);
  box.appendChild(svg);
  planted++;
  $("gardenCount").textContent = planted + (planted === 1 ? " flower planted" : " flowers planted") + (planted >= 10 ? " 🌷 look at it bloom!" : "");
}
$("gardenBox").addEventListener("click", (e) => {
  const r = e.currentTarget.getBoundingClientRect();
  plant(e.clientX - r.left, e.clientY - r.top);
});
$("gardenBox").addEventListener("keydown", (e) => {
  if (e.key === "Enter" || e.key === " ") {
    e.preventDefault();
    const b = $("gardenBox");
    plant(Math.random() * b.clientWidth, b.clientHeight * (0.75 + Math.random() * 0.2));
  }
});
if (CONFIG.playlistUrl) { const p = $("playlistBtn"); p.href = CONFIG.playlistUrl; p.hidden = false; }

/* The question */
$("question").textContent = CONFIG.question;
let dodge = 0;
const no = $("no"), yes = $("yes");
function runAway() {
  no.textContent = CONFIG.noDodges[dodge++ % CONFIG.noDodges.length];
  const area = $("btns").getBoundingClientRect();
  const maxX = Math.max(0, area.width - no.offsetWidth);
  no.style.position = "relative";
  no.style.left = (Math.random() * maxX - maxX / 2) + "px";
  no.style.top = (Math.random() * 90 - 45) + "px";
  yes.style.transform = "scale(" + Math.min(1.6, 1 + dodge * 0.1) + ")";
}
no.addEventListener("pointerenter", runAway);
no.addEventListener("click", (e) => { e.preventDefault(); runAway(); });
yes.addEventListener("click", () => {
  $("btns").style.display = "none";
  $("answerTitle").textContent = CONFIG.yesTitle;
  $("answerText").textContent = fill(CONFIG.yesText);
  $("answer").classList.add("show");
  for (let i = 0; i < 6; i++) setTimeout(() => burst(Math.random() * innerWidth, innerHeight - 40, 10), i * 250);
});

/* Birthday countdown */
(function () {
  const now = new Date();
  let next = new Date(now.getFullYear(), CONFIG.birthday.month - 1, CONFIG.birthday.day);
  const today = new Date(now.getFullYear(), now.getMonth(), now.getDate());
  if (next < today) next = new Date(now.getFullYear() + 1, CONFIG.birthday.month - 1, CONFIG.birthday.day);
  const days = Math.round((next - today) / 864e5);
  $("bdayDays").textContent = days;
  $("bdayText").textContent = days === 0 ? "HAPPY BIRTHDAY " + CONFIG.herName.toUpperCase() + "!! 🎉🎂" : fill(CONFIG.birthdayText);
})();
</script>
</body>
</html>
