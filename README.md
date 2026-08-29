<!DOCTYPE html>
<html lang="fa" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>صفحه مسدود گردیده | قیس حیدری</title>

<style>
@import url('https://fonts.googleapis.com/css2?family=Tajawal:wght@400;500;700;800;900&display=swap');

*{
    margin:0;
    padding:0;
    box-sizing:border-box;
}

:root{
    --red:#ff1744;
    --red2:#ff3d00;
    --gold:#ffd700;
    --white:#ffffff;
    --dark:#030303;
    --glass:rgba(255,255,255,.07);
}

html,body{
    width:100%;
    min-height:100%;
}

body{
    min-height:100vh;
    overflow:hidden;
    font-family:'Tajawal',sans-serif;
    background:
        radial-gradient(circle at 50% 45%,rgba(255,23,68,.12),transparent 25%),
        radial-gradient(circle at 20% 20%,rgba(255,215,0,.07),transparent 30%),
        linear-gradient(135deg,#010101,#0b0b0b,#020202);
    color:white;
}

/* =========================
   Background
========================= */

.background{
    position:fixed;
    inset:0;
    overflow:hidden;
    z-index:-5;
}

.glow{
    position:absolute;
    width:450px;
    height:450px;
    border-radius:50%;
    filter:blur(100px);
    opacity:.16;
    animation:moveGlow 9s ease-in-out infinite alternate;
}

.glow.red{
    background:var(--red);
    top:-180px;
    right:-150px;
}

.glow.gold{
    background:var(--gold);
    bottom:-220px;
    left:-150px;
    animation-delay:2s;
}

@keyframes moveGlow{
    0%{
        transform:translate(0,0) scale(1);
    }
    100%{
        transform:translate(-70px,60px) scale(1.25);
    }
}

/* =========================
   Grid
========================= */

.grid{
    position:fixed;
    inset:0;
    opacity:.06;
    background-image:
        linear-gradient(rgba(255,255,255,.5) 1px,transparent 1px),
        linear-gradient(90deg,rgba(255,255,255,.5) 1px,transparent 1px);
    background-size:50px 50px;
    mask-image:linear-gradient(to bottom,transparent,black,transparent);
    z-index:-4;
}

/* =========================
   Particles
========================= */

#particles{
    position:fixed;
    inset:0;
    z-index:-3;
}

/* =========================
   Main
========================= */

main{
    min-height:100vh;
    display:flex;
    justify-content:center;
    align-items:center;
    padding:25px;
}

.panel{
    width:min(900px,100%);
    text-align:center;
    padding:55px 35px;
    border:1px solid rgba(255,23,68,.28);
    border-radius:38px;
    background:
        linear-gradient(
            145deg,
            rgba(255,255,255,.09),
            rgba(255,255,255,.025)
        );
    backdrop-filter:blur(22px);
    -webkit-backdrop-filter:blur(22px);
    box-shadow:
        0 30px 100px rgba(0,0,0,.65),
        inset 0 1px rgba(255,255,255,.12);
    animation:panelIn 1.2s cubic-bezier(.16,1,.3,1);
}

@keyframes panelIn{
    from{
        opacity:0;
        transform:translateY(40px) scale(.92);
    }
    to{
        opacity:1;
        transform:translateY(0) scale(1);
    }
}

/* =========================
   Lock
========================= */

.lock-wrap{
    position:relative;
    width:130px;
    height:150px;
    margin:0 auto 35px;
    display:flex;
    justify-content:center;
    align-items:center;
}

.lock-glow{
    position:absolute;
    width:150px;
    height:150px;
    border-radius:50%;
    background:rgba(255,23,68,.13);
    filter:blur(18px);
    animation:lockGlow 1.8s infinite alternate;
}

@keyframes lockGlow{
    from{
        transform:scale(.8);
        opacity:.4;
    }
    to{
        transform:scale(1.2);
        opacity:1;
    }
}

.lock{
    position:relative;
    width:82px;
    height:70px;
    margin-top:35px;
    border-radius:12px;
    background:
        linear-gradient(
            145deg,
            #ff5252,
            #d50000
        );
    box-shadow:
        0 12px 35px rgba(255,0,0,.35),
        inset 0 2px rgba(255,255,255,.3);
    animation:lockShake 3s infinite;
}

.lock::before{
    content:"";
    position:absolute;
    width:48px;
    height:55px;
    left:17px;
    top:-45px;
    border:10px solid #eee;
    border-bottom:0;
    border-radius:30px 30px 0 0;
    box-shadow:
        0 0 15px rgba(255,255,255,.15);
}

.lock::after{
    content:"";
    position:absolute;
    width:13px;
    height:24px;
    border-radius:10px;
    background:#390000;
    left:35px;
    top:24px;
    box-shadow:
        0 0 0 4px rgba(255,255,255,.08);
}

@keyframes lockShake{

    0%,82%,100%{
        transform:rotate(0);
    }

    84%{
        transform:rotate(-5deg);
    }

    86%{
        transform:rotate(5deg);
    }

    88%{
        transform:rotate(-4deg);
    }

    90%{
        transform:rotate(4deg);
    }

    92%{
        transform:rotate(0);
    }
}

/* =========================
   Warning
========================= */

.warning{
    display:inline-flex;
    align-items:center;
    gap:9px;
    padding:9px 18px;
    border-radius:30px;
    border:1px solid rgba(255,23,68,.35);
    background:rgba(255,23,68,.08);
    color:#ff8097;
    font-size:13px;
    font-weight:700;
    margin-bottom:25px;
    animation:warningPulse 2s infinite;
}

.warning-dot{
    width:8px;
    height:8px;
    border-radius:50%;
    background:var(--red);
    box-shadow:0 0 15px var(--red);
    animation:dotPulse 1s infinite;
}

@keyframes warningPulse{
    50%{
        box-shadow:0 0 30px rgba(255,23,68,.15);
    }
}

@keyframes dotPulse{
    50%{
        opacity:.25;
        transform:scale(.65);
    }
}

/* =========================
   Main Title
========================= */

.title{
    font-size:clamp(32px,6vw,68px);
    line-height:1.35;
    font-weight:900;
    margin-bottom:18px;

    background:
        linear-gradient(
            90deg,
            #fff,
            #ffb3bd,
            #ff1744,
            #fff
        );

    background-size:300% auto;
    -webkit-background-clip:text;
    background-clip:text;
    color:transparent;

    animation:titleShine 4s linear infinite;
}

@keyframes titleShine{
    to{
        background-position:300% center;
    }
}

/* =========================
   Admin
========================= */

.admin{
    display:inline-block;
    color:var(--gold);
    font-size:clamp(20px,3vw,30px);
    font-weight:900;
    text-shadow:
        0 0 12px rgba(255,215,0,.35);
    margin:8px 0;
}

.message{
    color:#aaa;
    font-size:15px;
    line-height:2;
    max-width:650px;
    margin:12px auto 0;
}

/* =========================
   Status
========================= */

.status{
    display:flex;
    justify-content:center;
    align-items:center;
    gap:10px;
    margin:30px auto 0;
    padding:13px 20px;
    width:max-content;
    max-width:100%;
    border-radius:18px;
    background:rgba(0,0,0,.28);
    border:1px solid rgba(255,255,255,.08);
    color:#ccc;
    font-size:13px;
}

.status-icon{
    color:var(--red);
    animation:statusBlink 1.2s infinite;
}

@keyframes statusBlink{
    50%{
        opacity:.25;
    }
}

/* =========================
   Button
========================= */

.btn{
    display:inline-flex;
    margin-top:28px;
    padding:13px 28px;
    border-radius:30px;
    text-decoration:none;
    color:#111;
    font-size:14px;
    font-weight:800;
    background:
        linear-gradient(
            135deg,
            #fff176,
            #ffd700,
            #ff9800
        );
    box-shadow:
        0 10px 35px rgba(255,174,0,.2);
    transition:.35s;
}

.btn:hover{
    transform:translateY(-4px) scale(1.04);
    box-shadow:
        0 15px 45px rgba(255,174,0,.35);
}

/* =========================
   Footer
========================= */

footer{
    position:fixed;
    bottom:20px;
    left:0;
    right:0;
    text-align:center;
    color:#555;
    font-size:11px;
}

footer strong{
    color:#777;
}

/* =========================
   Scan Line
========================= */

.scan{
    position:fixed;
    left:0;
    right:0;
    height:1px;
    background:linear-gradient(
        90deg,
        transparent,
        rgba(255,23,68,.5),
        transparent
    );
    box-shadow:0 0 12px rgba(255,23,68,.5);
    animation:scan 5s linear infinite;
    pointer-events:none;
    z-index:10;
}

@keyframes scan{
    0%{
        top:-5%;
    }
    100%{
        top:105%;
    }
}

/* =========================
   Responsive
========================= */

@media(max-width:600px){

    main{
        padding:15px;
    }

    .panel{
        padding:42px 20px;
        border-radius:28px;
    }

    .lock-wrap{
        transform:scale(.85);
        margin-bottom:20px;
    }

    .message{
        font-size:13px;
    }

    .status{
        font-size:11px;
        padding:11px 14px;
    }

    footer{
        bottom:10px;
    }
}
</style>
</head>

<body>

<div class="background">
    <div class="glow red"></div>
    <div class="glow gold"></div>
</div>

<div class="grid"></div>

<canvas id="particles"></canvas>

<div class="scan"></div>

<main>

    <section class="panel">

        <div class="lock-wrap">
            <div class="lock-glow"></div>
            <div class="lock"></div>
        </div>

        <div class="warning">
            <span class="warning-dot"></span>
            هشدار امنیتی
        </div>

        <h1 class="title">
            صفحه توسط ادمین
            <br>
            <span class="admin">قیس حیدری</span>
            <br>
            مسدود گردیده
        </h1>

        <p class="message">
            دسترسی به این صفحه در حال حاضر امکان‌پذیر نمی‌باشد.
            این صفحه توسط مدیر سیستم مسدود شده است.
        </p>

        <div class="status">
            <span class="status-icon">●</span>
            وضعیت صفحه: <strong>مسدود</strong>
        </div>

        <a href="#" class="btn" id="backButton">
            بازگشت
        </a>

    </section>

</main>

<footer>
    مدیریت و نظارت توسط <strong>قیس حیدری</strong>
</footer>

<script>

/* =========================================
   Particle System
========================================= */

const canvas = document.getElementById("particles");
const ctx = canvas.getContext("2d");

let particles = [];

function resizeCanvas(){

    canvas.width = window.innerWidth;
    canvas.height = window.innerHeight;

}

resizeCanvas();

window.addEventListener("resize",resizeCanvas);

class Particle{

    constructor(){

        this.reset();

    }

    reset(){

        this.x = Math.random() * canvas.width;
        this.y = Math.random() * canvas.height;

        this.size = Math.random() * 1.8 + .3;

        this.speedX =
            (Math.random() - .5) * .35;

        this.speedY =
            (Math.random() - .5) * .35;

        this.opacity =
            Math.random() * .5 + .1;

    }

    update(){

        this.x += this.speedX;
        this.y += this.speedY;

        if(
            this.x < 0 ||
            this.x > canvas.width ||
            this.y < 0 ||
            this.y > canvas.height
        ){
            this.reset();
        }

    }

    draw(){

        ctx.beginPath();

        ctx.arc(
            this.x,
            this.y,
            this.size,
            0,
            Math.PI * 2
        );

        ctx.fillStyle =
            `rgba(255,80,100,${this.opacity})`;

        ctx.fill();

    }

}

for(let i=0;i<150;i++){

    particles.push(new Particle());

}

function animateParticles(){

    ctx.clearRect(
        0,
        0,
        canvas.width,
        canvas.height
    );

    particles.forEach(p => {

        p.update();
        p.draw();

    });

    requestAnimationFrame(animateParticles);

}

animateParticles();


/* =========================================
   Mouse Parallax
========================================= */

const panel = document.querySelector(".panel");

document.addEventListener("mousemove",(e)=>{

    const x =
        (window.innerWidth / 2 - e.clientX) / 80;

    const y =
        (window.innerHeight / 2 - e.clientY) / 80;

    panel.style.transform =
        `perspective(1200px)
         rotateY(${-x}deg)
         rotateX(${y}deg)`;

});


/* =========================================
   Reset
========================================= */

document.addEventListener("mouseleave",()=>{

    panel.style.transform =
        "perspective(1200px) rotateY(0deg) rotateX(0deg)";

});


/* =========================================
   Back Button
========================================= */

document.getElementById("backButton")
.addEventListener("click",(e)=>{

    e.preventDefault();

    if(history.length > 1){

        history.back();

    }else{

        window.location.href = "/";

    }

});


/* =========================================
   Mobile Touch Effect
========================================= */

document.addEventListener("touchmove",(e)=>{

    if(!e.touches[0]) return;

    const touch = e.touches[0];

    const x =
        (window.innerWidth / 2 - touch.clientX) / 120;

    const y =
        (window.innerHeight / 2 - touch.clientY) / 120;

    panel.style.transform =
        `perspective(1200px)
         rotateY(${-x}deg)
         rotateX(${y}deg)`;

},{passive:true});

</script>

</body>
</html>
