<!DOCTYPE html>
<html lang="fa-AF" dir="rtl">
<head>
    <meta charset="UTF-8">

    <meta name="viewport"
          content="width=device-width, initial-scale=1.0">

    <meta name="description"
          content="صفحه توسط ادمین قیس حیدری مسدود گردیده.">

    <meta name="theme-color"
          content="#050505">

    <title>
        صفحه مسدود گردیده | قیس حیدری
    </title>

    <style>
        /* ==============================
           RESET
        ============================== */

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        /* ==============================
           VARIABLES
        ============================== */

        :root {
            --bg: #030303;
            --bg-light: #0b0b0b;

            --red: #ff1744;
            --red-light: #ff5575;

            --gold: #ffd700;

            --white: #ffffff;
            --gray: #9b9b9b;

            --border:
                rgba(255, 255, 255, 0.12);
        }

        /* ==============================
           BODY
        ============================== */

        html,
        body {
            width: 100%;
            min-height: 100%;
        }

        body {
            min-height: 100vh;

            display: flex;
            align-items: center;
            justify-content: center;

            overflow: hidden;

            font-family:
                Tahoma,
                Arial,
                sans-serif;

            color: var(--white);

            background:
                radial-gradient(
                    circle at center,
                    rgba(255, 23, 68, 0.13),
                    transparent 32%
                ),
                radial-gradient(
                    circle at 10% 10%,
                    rgba(255, 215, 0, 0.06),
                    transparent 25%
                ),
                linear-gradient(
                    135deg,
                    #010101,
                    #0b0b0b,
                    #020202
                );
        }

        /* ==============================
           BACKGROUND GLOW
        ============================== */

        .glow {
            position: fixed;

            width: 420px;
            height: 420px;

            border-radius: 50%;

            filter: blur(120px);

            opacity: 0.13;

            pointer-events: none;

            animation:
                floatingGlow 10s ease-in-out
                infinite alternate;
        }

        .glow-red {
            top: -180px;
            right: -160px;

            background: var(--red);
        }

        .glow-gold {
            bottom: -180px;
            left: -160px;

            background: var(--gold);

            animation-delay: 2s;
        }

        @keyframes floatingGlow {
            from {
                transform:
                    translate3d(0, 0, 0)
                    scale(1);
            }

            to {
                transform:
                    translate3d(-70px, 60px, 0)
                    scale(1.25);
            }
        }

        /* ==============================
           GRID
        ============================== */

        .grid {
            position: fixed;
            inset: 0;

            pointer-events: none;

            opacity: 0.04;

            background-image:
                linear-gradient(
                    rgba(255,255,255,.6) 1px,
                    transparent 1px
                ),
                linear-gradient(
                    90deg,
                    rgba(255,255,255,.6) 1px,
                    transparent 1px
                );

            background-size: 50px 50px;

            mask-image:
                radial-gradient(
                    circle,
                    #000 15%,
                    transparent 80%
                );
        }

        /* ==============================
           PARTICLES
        ============================== */

        #particles {
            position: fixed;
            inset: 0;

            width: 100%;
            height: 100%;

            pointer-events: none;
        }

        /* ==============================
           MAIN CARD
        ============================== */

        .container {
            position: relative;

            width: min(900px, calc(100% - 30px));

            padding: 55px 30px;

            text-align: center;

            border:
                1px solid var(--border);

            border-radius: 36px;

            background:
                linear-gradient(
                    145deg,
                    rgba(255,255,255,.08),
                    rgba(255,255,255,.025)
                );

            backdrop-filter: blur(25px);
            -webkit-backdrop-filter: blur(25px);

            box-shadow:
                0 35px 100px
                rgba(0,0,0,.7),

                inset 0 1px
                rgba(255,255,255,.12);

            animation:
                containerIn
                1s cubic-bezier(.16,1,.3,1);

            transition:
                transform .18s ease-out;
        }

        .container::before {
            content: "";

            position: absolute;
            inset: 0;

            border-radius: 36px;

            pointer-events: none;

            border:
                1px solid
                rgba(255, 23, 68, .15);
        }

        @keyframes containerIn {
            from {
                opacity: 0;

                transform:
                    translateY(40px)
                    scale(.92);
            }

            to {
                opacity: 1;

                transform:
                    translateY(0)
                    scale(1);
            }
        }

        /* ==============================
           LOCK
        ============================== */

        .lock-area {
            position: relative;

            width: 140px;
            height: 145px;

            margin:
                0 auto 25px;

            display: flex;
            align-items: flex-end;
            justify-content: center;
        }

        .lock-glow {
            position: absolute;

            width: 145px;
            height: 145px;

            border-radius: 50%;

            background:
                radial-gradient(
                    circle,
                    rgba(255,23,68,.25),
                    transparent 68%
                );

            animation:
                lockGlow 2s ease-in-out
                infinite;
        }

        @keyframes lockGlow {
            0%,
            100% {
                transform: scale(.8);
                opacity: .5;
            }

            50% {
                transform: scale(1.15);
                opacity: 1;
            }
        }

        .lock {
            position: relative;

            width: 85px;
            height: 72px;

            border-radius: 13px;

            background:
                linear-gradient(
                    145deg,
                    #ff6079,
                    #e00032 50%,
                    #79001c
                );

            box-shadow:
                0 15px 40px
                rgba(255,0,55,.35),

                inset 0 2px
                rgba(255,255,255,.35);

            animation:
                lockShake 4s infinite;
        }

        .lock::before {
            content: "";

            position: absolute;

            width: 48px;
            height: 58px;

            left: 18px;
            top: -49px;

            border:
                9px solid #e9edf0;

            border-bottom: 0;

            border-radius:
                30px 30px 0 0;
        }

        .lock::after {
            content: "";

            position: absolute;

            width: 14px;
            height: 25px;

            left: 35px;
            top: 24px;

            border-radius: 10px;

            background: #280009;
        }

        @keyframes lockShake {

            0%,
            80%,
            100% {
                transform: rotate(0);
            }

            83% {
                transform: rotate(-5deg);
            }

            86% {
                transform: rotate(5deg);
            }

            89% {
                transform: rotate(-4deg);
            }

            92% {
                transform: rotate(3deg);
            }

            95% {
                transform: rotate(0);
            }
        }

        /* ==============================
           WARNING
        ============================== */

        .warning {
            display: inline-flex;

            align-items: center;

            gap: 9px;

            padding:
                9px 18px;

            margin-bottom: 20px;

            border:
                1px solid
                rgba(255,23,68,.35);

            border-radius: 30px;

            background:
                rgba(255,23,68,.07);

            color: #ff8499;

            font-size: 13px;
            font-weight: 700;

            animation:
                warningPulse 2s infinite;
        }

        .warning-dot {
            width: 8px;
            height: 8px;

            border-radius: 50%;

            background: var(--red);

            box-shadow:
                0 0 14px var(--red);

            animation:
                blink 1s infinite;
        }

        @keyframes blink {
            50% {
                opacity: .2;
                transform: scale(.6);
            }
        }

        @keyframes warningPulse {
            50% {
                box-shadow:
                    0 0 30px
                    rgba(255,23,68,.15);
            }
        }

        /* ==============================
           TITLE
        ============================== */

        h1 {
            margin: 0;

            font-size:
                clamp(30px, 6vw, 64px);

            line-height: 1.45;

            font-weight: 900;

            background:
                linear-gradient(
                    90deg,
                    #fff,
                    #ffb5c1,
                    #ff1744,
                    #fff,
                    #ffd700
                );

            background-size: 400% auto;

            -webkit-background-clip: text;
            background-clip: text;

            color: transparent;

            animation:
                titleAnimation
                5s linear infinite;
        }

        @keyframes titleAnimation {
            to {
                background-position:
                    400% center;
            }
        }

        /* ==============================
           ADMIN
        ============================== */

        .admin {
            display: inline-block;

            color: var(--gold);

            font-size:
                clamp(25px, 4vw, 42px);

            text-shadow:
                0 0 15px
                rgba(255,215,0,.4);

            animation:
                adminPulse
                2s ease-in-out infinite
                alternate;
        }

        @keyframes adminPulse {
            from {
                text-shadow:
                    0 0 7px
                    rgba(255,215,0,.2);
            }

            to {
                text-shadow:
                    0 0 22px
                    rgba(255,215,0,.65);
            }
        }

        /* ==============================
           DESCRIPTION
        ============================== */

        .description {
            max-width: 650px;

            min-height: 55px;

            margin:
                18px auto 0;

            color: var(--gray);

            font-size:
                clamp(13px, 2vw, 16px);

            line-height: 2;
        }

        /* ==============================
           STATUS
        ============================== */

        .status {
            display: inline-flex;

            align-items: center;

            gap: 9px;

            margin-top: 20px;

            padding:
                11px 20px;

            border:
                1px solid
                rgba(255,255,255,.08);

            border-radius: 18px;

            background:
                rgba(0,0,0,.3);

            color: #999;

            font-size: 13px;
        }

        .status-dot {
            width: 8px;
            height: 8px;

            border-radius: 50%;

            background: var(--red);

            box-shadow:
                0 0 12px var(--red);

            animation:
                blink 1.2s infinite;
        }

        .status strong {
            color:
                var(--red-light);
        }

        /* ==============================
           BUTTON
        ============================== */

        .button {
            display: inline-flex;

            align-items: center;
            justify-content: center;

            margin-top: 28px;

            min-height: 46px;

            padding:
                0 28px;

            border-radius: 30px;

            color: #111;

            background:
                linear-gradient(
                    135deg,
                    #fff176,
                    #ffd700,
                    #ff9800
                );

            font-size: 14px;
            font-weight: 800;

            text-decoration: none;

            box-shadow:
                0 10px 30px
                rgba(255,174,0,.2);

            transition:
                transform .25s ease,
                box-shadow .25s ease;
        }

        .button:hover {
            transform:
                translateY(-4px)
                scale(1.04);

            box-shadow:
                0 18px 45px
                rgba(255,174,0,.35);
        }

        .button:focus-visible {
            outline:
                3px solid
                rgba(255,215,0,.5);

            outline-offset: 4px;
        }

        /* ==============================
           FOOTER
        ============================== */

        .footer {
            position: fixed;

            right: 0;
            bottom: 14px;
            left: 0;

            text-align: center;

            color: #555;

            font-size: 11px;
        }

        .footer strong {
            color: #777;
        }

        /* ==============================
           MOBILE
        ============================== */

        @media (max-width: 600px) {

            .container {
                width:
                    calc(100% - 20px);

                padding:
                    40px 18px;

                border-radius: 28px;
            }

            .container::before {
                border-radius: 28px;
            }

            .lock-area {
                transform: scale(.88);

                margin-bottom: 5px;
            }

            .warning {
                font-size: 11px;
            }

            h1 {
                font-size: 29px;
            }

            .admin {
                font-size: 25px;
            }

            .description {
                font-size: 12px;
            }

            .status {
                font-size: 11px;
            }

            .button {
                width: 100%;
                max-width: 300px;
            }

            .footer {
                bottom: 7px;
            }
        }

        /* ==============================
           REDUCED MOTION
        ============================== */

        @media (prefers-reduced-motion: reduce) {

            *,
            *::before,
            *::after {
                animation-duration: .01ms !important;
                animation-iteration-count: 1 !important;
                transition-duration: .01ms !important;
            }
        }
    </style>
</head>

<body>

    <!-- Background -->
    <div class="glow glow-red"></div>
    <div class="glow glow-gold"></div>

    <div class="grid"></div>

    <canvas
        id="particles"
        aria-hidden="true">
    </canvas>


    <!-- Main -->
    <main class="container" id="card">

        <!-- Lock -->
        <div
            class="lock-area"
            aria-hidden="true">

            <div class="lock-glow"></div>

            <div class="lock"></div>

        </div>


        <!-- Warning -->
        <div class="warning">

            <span class="warning-dot"></span>

            هشدار امنیتی

        </div>


        <!-- Main Message -->
        <h1>

            صفحه توسط ادمین

            <br>

            <span class="admin">
                قیس حیدری
            </span>

            <br>

            مسدود گردیده

        </h1>


        <!-- Description -->
        <p
            class="description"
            id="description"
            aria-live="polite">
        </p>


        <!-- Status -->
        <div class="status">

            <span class="status-dot"></span>

            وضعیت صفحه:

            <strong>
                مسدود
            </strong>

        </div>


        <!-- Back Button -->
        <a
            href="/"
            class="button"
            id="backButton">

            بازگشت به صفحه اصلی

        </a>

    </main>


    <!-- Footer -->
    <footer class="footer">

        مدیریت و نظارت توسط

        <strong>
            قیس حیدری
        </strong>

        © 2026

    </footer>


    <script>

        "use strict";


        /* =================================
           TYPEWRITER
        ================================= */

        const description =
            document.getElementById(
                "description"
            );

        const message =
            "دسترسی به این صفحه در حال حاضر امکان‌پذیر نمی‌باشد. این صفحه توسط مدیر سیستم مسدود شده است.";

        let index = 0;

        function typeMessage() {

            if (
                index >= message.length
            ) {
                return;
            }

            description.textContent +=
                message.charAt(index);

            index++;

            setTimeout(
                typeMessage,
                40
            );
        }

        setTimeout(
            typeMessage,
            700
        );


        /* =================================
           PARTICLES
        ================================= */

        const canvas =
            document.getElementById(
                "particles"
            );

        const ctx =
            canvas.getContext("2d");

        let particles = [];


        function resizeCanvas() {

            const ratio =
                Math.min(
                    window.devicePixelRatio || 1,
                    2
                );

            canvas.width =
                window.innerWidth * ratio;

            canvas.height =
                window.innerHeight * ratio;

            canvas.style.width =
                window.innerWidth + "px";

            canvas.style.height =
                window.innerHeight + "px";

            ctx.setTransform(
                ratio,
                0,
                0,
                ratio,
                0,
                0
            );
        }


        resizeCanvas();


        window.addEventListener(
            "resize",
            resizeCanvas,
            {
                passive: true
            }
        );


        class Particle {

            constructor() {

                this.reset();

            }


            reset() {

                this.x =
                    Math.random() *
                    window.innerWidth;

                this.y =
                    Math.random() *
                    window.innerHeight;

                this.size =
                    Math.random() *
                    1.5 + .3;

                this.speedX =
                    (Math.random() - .5)
                    * .25;

                this.speedY =
                    (Math.random() - .5)
                    * .25;

                this.opacity =
                    Math.random() *
                    .5 + .05;
            }


            update() {

                this.x +=
                    this.speedX;

                this.y +=
                    this.speedY;


                if (
                    this.x < -10 ||
                    this.x >
                    window.innerWidth + 10 ||
                    this.y < -10 ||
                    this.y >
                    window.innerHeight + 10
                ) {

                    this.reset();

                }
            }


            draw() {

                ctx.beginPath();

                ctx.arc(
                    this.x,
                    this.y,
                    this.size,
                    0,
                    Math.PI * 2
                );

                ctx.fillStyle =
                    `rgba(
                        255,
                        45,
                        75,
                        ${this.opacity}
                    )`;

                ctx.fill();
            }
        }


        const count =
            window.innerWidth < 600
                ? 70
                : 130;


        for (
            let i = 0;
            i < count;
            i++
        ) {

            particles.push(
                new Particle()
            );

        }


        function animateParticles() {

            ctx.clearRect(
                0,
                0,
                window.innerWidth,
                window.innerHeight
            );


            particles.forEach(
                particle => {

                    particle.update();

                    particle.draw();

                }
            );


            requestAnimationFrame(
                animateParticles
            );
        }


        animateParticles();


        /* =================================
           3D DESKTOP EFFECT
        ================================= */

        const card =
            document.getElementById(
                "card"
            );


        const reduceMotion =
            window.matchMedia(
                "(prefers-reduced-motion: reduce)"
            );


        if (
            !reduceMotion.matches
        ) {

            document.addEventListener(
                "mousemove",
                function(event) {

                    if (
                        window.innerWidth < 700
                    ) {
                        return;
                    }


                    const rotateY =
                        (
                            window.innerWidth / 2 -
                            event.clientX
                        ) / 100;


                    const rotateX =
                        (
                            window.innerHeight / 2 -
                            event.clientY
                        ) / 100;


                    card.style.transform =
                        `
                        perspective(1200px)
                        rotateY(${rotateY}deg)
                        rotateX(${rotateX}deg)
                        `;
                },
                {
                    passive: true
                }
            );


            document.addEventListener(
                "mouseleave",
                function() {

                    card.style.transform =
                        `
                        perspective(1200px)
                        rotateY(0deg)
                        rotateX(0deg)
                        `;
                }
            );
        }


        /* =================================
           BACK BUTTON
        ================================= */

        document
            .getElementById("backButton")
            .addEventListener(
                "click",
                function(event) {

                    if (
                        window.history.length > 1
                    ) {

                        event.preventDefault();

                        window.history.back();

                    }

                }
            );

    </script>

</body>
</html>
