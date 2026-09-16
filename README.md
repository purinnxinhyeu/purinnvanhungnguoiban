<!DOCTYPE html>
<html lang="vi">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>Pompurin's Little World 🍮</title>

<style>

/* =====================================================
   FONT + BASIC
===================================================== */

*{
    box-sizing:border-box;
    margin:0;
    padding:0;
}

:root{
    --bg:#fff7df;
    --bg2:#fffdf5;

    --card:rgba(255,255,255,.78);
    --card2:rgba(255,255,255,.55);

    --text:#554941;
    --sub:#8d7c70;

    --yellow:#ffd66b;
    --yellow2:#ffedaa;

    --pink:#ffabc0;
    --pink2:#ffe0e8;

    --blue:#aee7ff;
    --blue2:#e1f7ff;

    --green:#bdebc8;

    --shadow:
        0 18px 45px rgba(123,92,43,.13);

    --shadow2:
        0 30px 80px rgba(123,92,43,.20);
}

body.dark{

    --bg:#252331;
    --bg2:#302d3e;

    --card:rgba(53,50,66,.86);
    --card2:rgba(70,65,82,.65);

    --text:#fff6e9;
    --sub:#c7bdc2;

    --shadow:
        0 18px 45px rgba(0,0,0,.25);

    --shadow2:
        0 30px 80px rgba(0,0,0,.45);
}


/*
   Font viết tay nhưng dễ đọc.
   Segoe Print có sẵn trên nhiều máy Windows.
*/
body{

    font-family:
        "Segoe Print",
        "Bradley Hand",
        "Comic Sans MS",
        cursive;

    color:var(--text);

    min-height:100vh;

    background:
        radial-gradient(
            circle at 10% 15%,
            #ffe6a3 0 8%,
            transparent 25%
        ),

        radial-gradient(
            circle at 90% 20%,
            #ffd9e5 0 8%,
            transparent 25%
        ),

        radial-gradient(
            circle at 50% 100%,
            #c9efff 0 12%,
            transparent 35%
        ),

        linear-gradient(
            135deg,
            var(--bg),
            var(--bg2)
        );

    overflow-x:hidden;

    transition:.5s;
}


/* =====================================================
   DECORATIVE BACKGROUND
===================================================== */

.background{
    position:fixed;
    inset:0;
    pointer-events:none;
    overflow:hidden;
    z-index:-10;
}


/* BIG PASTEL BLOBS */

.blob{
    position:absolute;
    border-radius:50%;
    filter:blur(2px);
    opacity:.55;
}

.blob.one{
    width:330px;
    height:330px;

    background:#ffd6e3;

    top:-120px;
    left:-120px;
}

.blob.two{
    width:270px;
    height:270px;

    background:#bcecff;

    right:-80px;
    top:35%;
}

.blob.three{
    width:360px;
    height:360px;

    background:#ffe6a7;

    left:30%;
    bottom:-220px;
}


/* CLOUDS */

.cloud{
    position:absolute;

    width:180px;
    height:55px;

    background:rgba(255,255,255,.7);

    border-radius:50px;

    opacity:.8;

    animation:
        cloudMove 28s linear infinite;
}

.cloud:before,
.cloud:after{

    content:"";

    position:absolute;

    background:inherit;

    border-radius:50%;
}

.cloud:before{

    width:80px;
    height:80px;

    left:25px;
    bottom:0;
}

.cloud:after{

    width:95px;
    height:95px;

    right:20px;
    bottom:0;
}

.cloud.a{
    top:13%;
    left:-220px;
}

.cloud.b{

    top:70%;

    left:-300px;

    transform:scale(.7);

    animation-delay:10s;
}

@keyframes cloudMove{

    from{
        transform:translateX(0);
    }

    to{
        transform:translateX(calc(100vw + 500px));
    }
}


/* STARS */

.star{

    position:absolute;

    color:white;

    font-size:20px;

    animation:
        sparkle 2.5s ease-in-out infinite;
}

.star.s1{
    left:12%;
    top:28%;
}

.star.s2{
    left:85%;
    top:38%;

    animation-delay:.7s;
}

.star.s3{
    left:72%;
    top:12%;

    animation-delay:1.2s;
}

.star.s4{
    left:20%;
    top:72%;

    animation-delay:1.8s;
}

.star.s5{
    left:93%;
    top:78%;

    animation-delay:1s;
}

@keyframes sparkle{

    0%,100%{
        transform:scale(.7) rotate(0deg);
        opacity:.35;
    }

    50%{
        transform:scale(1.3) rotate(15deg);
        opacity:1;
    }
}


/* LITTLE DOTS */

.dot{

    position:absolute;

    width:9px;
    height:9px;

    border-radius:50%;

    background:white;

    opacity:.65;

    animation:
        dotFloat 5s ease-in-out infinite;
}

.dot.d1{
    left:8%;
    top:60%;
}

.dot.d2{
    left:90%;
    top:25%;

    animation-delay:1s;
}

.dot.d3{
    left:55%;
    top:18%;

    animation-delay:2s;
}

@keyframes dotFloat{

    50%{
        transform:translateY(-20px);
        opacity:.25;
    }
}


/* =====================================================
   TOP BAR
===================================================== */

.topbar{

    width:min(1100px,92%);

    margin:20px auto 12px;

    display:flex;

    justify-content:space-between;

    align-items:center;
}

.logo{

    font-size:25px;

    font-weight:700;

    color:#e6a92d;

    text-shadow:
        2px 2px white;
}

.tools{

    display:flex;

    gap:8px;
}

.tool{

    border:0;

    background:var(--card);

    color:var(--text);

    padding:9px 13px;

    border-radius:50px;

    cursor:pointer;

    box-shadow:var(--shadow);

    backdrop-filter:blur(15px);

    font-family:inherit;

    font-weight:700;

    transition:.25s;
}

.tool:hover{

    transform:
        translateY(-4px)
        rotate(-3deg);
}


/* =====================================================
   CHARACTER TABS
===================================================== */

.character-tabs{

    width:min(1100px,92%);

    margin:auto;

    display:flex;

    gap:10px;

    overflow-x:auto;

    padding:8px 4px 15px;

    scrollbar-width:none;
}

.character-tabs::-webkit-scrollbar{
    display:none;
}


.character-tab{

    flex:0 0 auto;

    border:2px solid transparent;

    background:var(--card);

    color:var(--text);

    border-radius:22px;

    padding:9px 15px;

    display:flex;

    align-items:center;

    gap:8px;

    cursor:pointer;

    font-family:inherit;

    font-weight:700;

    box-shadow:var(--shadow);

    backdrop-filter:blur(15px);

    transition:.3s;
}

.character-tab:hover{

    transform:
        translateY(-5px)
        rotate(-2deg);
}

.character-tab.active{

    background:
        linear-gradient(
            135deg,
            #ffe58b,
            #ffb8c9
        );

    border-color:white;

    color:#6b5140;

    transform:
        translateY(-4px);

    box-shadow:
        0 15px 35px rgba(255,171,193,.3);
}

.tab-face{

    width:34px;
    height:34px;

    border-radius:12px;

    object-fit:cover;

    background:white;
}


/* =====================================================
   MAIN
===================================================== */

.container{

    width:min(1100px,92%);

    margin:8px auto 60px;
}


/* =====================================================
   HERO PROFILE
===================================================== */

.hero{

    display:grid;

    grid-template-columns:
        300px
        1fr;

    gap:20px;

    perspective:1200px;
}


/* PROFILE CARD */

.profile-card{

    position:relative;

    background:var(--card);

    border:
        2px solid
        rgba(255,255,255,.75);

    border-radius:38px;

    padding:20px;

    text-align:center;

    box-shadow:var(--shadow2);

    backdrop-filter:blur(22px);

    transform-style:preserve-3d;

    transition:
        transform .5s,
        box-shadow .5s;

    overflow:hidden;
}


/* decorative corner */

.profile-card:before{

    content:"✦";

    position:absolute;

    right:20px;
    top:15px;

    color:#ffc95b;

    font-size:25px;

    animation:sparkle 2s infinite;
}

.profile-card:after{

    content:"♡";

    position:absolute;

    left:20px;
    bottom:12px;

    color:#ff9db5;

    font-size:30px;

    animation:
        heartFloat 3s ease-in-out infinite;
}

@keyframes heartFloat{

    50%{
        transform:
            translateY(-7px)
            rotate(-8deg);
    }
}


.profile-card:hover{

    transform:
        perspective(1000px)
        rotateY(-4deg)
        rotateX(3deg)
        translateY(-5px);

    box-shadow:
        0 35px 80px rgba(110,82,40,.2);
}


/* AVATAR */

.avatar-frame{

    position:relative;

    display:inline-block;

    margin:3px auto 8px;
}

.avatar{

    width:220px;
    height:220px;

    object-fit:cover;

    border-radius:35px;

    border:
        7px solid white;

    box-shadow:
        0 18px 40px rgba(0,0,0,.15);

    transition:.5s;
}

.profile-card:hover .avatar{

    transform:
        scale(1.03)
        rotate(1deg);
}


.avatar-deco{

    position:absolute;

    font-size:28px;
}

.avatar-deco.one{
    top:-8px;
    left:-14px;
}

.avatar-deco.two{
    bottom:4px;
    right:-13px;
}


.profile-name{

    font-size:30px;

    font-weight:700;

    margin-top:5px;
}

.profile-tag{

    color:var(--sub);

    font-size:13px;

    margin-top:2px;
}


.online{

    display:inline-flex;

    align-items:center;

    gap:5px;

    background:#dff8df;

    color:#5da765;

    padding:6px 13px;

    border-radius:30px;

    font-size:12px;

    margin-top:12px;
}


/* =====================================================
   INFO CARD
===================================================== */

.info-card{

    position:relative;

    background:var(--card);

    border:
        2px solid
        rgba(255,255,255,.7);

    border-radius:38px;

    padding:32px;

    box-shadow:var(--shadow2);

    backdrop-filter:blur(22px);

    overflow:hidden;
}

.info-card:before{

    content:"";

    position:absolute;

    width:160px;
    height:160px;

    background:#fff0ae;

    border-radius:50%;

    right:-80px;
    top:-80px;

    opacity:.5;
}

.info-card:after{

    content:"✦  ♡  ✦";

    position:absolute;

    right:25px;
    bottom:20px;

    color:#ffb4c7;

    font-size:20px;
}


.mini-title{

    color:var(--sub);

    font-size:14px;
}

.info-card h1{

    font-size:43px;

    line-height:1.2;

    margin:5px 0 13px;
}

.info-card h1 span{

    color:#e8a72e;

    text-shadow:
        2px 2px #fff;
}


.description{

    max-width:650px;

    line-height:1.8;

    font-size:15px;
}


/* tags */

.tags{

    display:flex;

    gap:8px;

    flex-wrap:wrap;

    margin-top:18px;
}

.tag{

    padding:8px 13px;

    border-radius:15px;

    font-size:12px;

    font-weight:700;

    background:#fff1b7;
}

.tag:nth-child(2){
    background:#ffdce6;
}

.tag:nth-child(3){
    background:#d8f3ff;
}

.tag:nth-child(4){
    background:#dff5df;
}


/* =====================================================
   QUICK INFO
===================================================== */

.quick{

    display:grid;

    grid-template-columns:
        repeat(3,1fr);

    gap:10px;

    margin-top:22px;
}

.quick-box{

    background:var(--card2);

    border-radius:20px;

    padding:14px;

    text-align:center;

    border:1px solid rgba(255,255,255,.5);

    transition:.3s;
}

.quick-box:hover{

    transform:
        translateY(-5px)
        rotate(-1deg);
}

.quick-box b{

    display:block;

    font-size:20px;
}

.quick-box small{

    color:var(--sub);
}


/* =====================================================
   MENU
===================================================== */

.menu{

    display:grid;

    grid-template-columns:
        repeat(4,1fr);

    gap:12px;

    margin-top:18px;
}

.menu-button{

    border:0;

    background:var(--card);

    color:var(--text);

    border-radius:25px;

    padding:16px 10px;

    font-family:inherit;

    font-weight:700;

    cursor:pointer;

    box-shadow:var(--shadow);

    backdrop-filter:blur(15px);

    transition:.35s;

    transform-style:preserve-3d;
}

.menu-button .icon{

    display:block;

    font-size:28px;

    margin-bottom:4px;
}

.menu-button:hover{

    transform:
        perspective(700px)
        rotateX(10deg)
        rotateY(-6deg)
        translateY(-7px);

    box-shadow:
        0 25px 55px rgba(100,75,35,.2);
}


/* =====================================================
   CLOCK + WEATHER
===================================================== */

.widgets{

    display:grid;

    grid-template-columns:1fr 1fr;

    gap:12px;

    margin-top:12px;
}

.widget{

    position:relative;

    background:var(--card);

    border-radius:25px;

    padding:17px 20px;

    box-shadow:var(--shadow);

    backdrop-filter:blur(15px);

    overflow:hidden;
}

.widget:after{

    content:"✦";

    position:absolute;

    right:18px;
    top:12px;

    color:#ffd05e;

    font-size:20px;
}

.widget small{

    color:var(--sub);
}

.big-value{

    font-size:25px;

    font-weight:700;

    margin-top:4px;
}


/* =====================================================
   MODAL 3D
===================================================== */

.modal{

    position:fixed;

    inset:0;

    z-index:100;

    display:flex;

    align-items:center;

    justify-content:center;

    padding:20px;

    background:
        rgba(50,38,45,.45);

    backdrop-filter:blur(9px);

    opacity:0;

    pointer-events:none;

    transition:.35s;

    perspective:1200px;
}

.modal.show{

    opacity:1;

    pointer-events:auto;
}

.modal-box{

    width:min(600px,95%);

    max-height:82vh;

    overflow:auto;

    background:var(--card);

    border:
        2px solid
        rgba(255,255,255,.75);

    border-radius:38px;

    padding:30px;

    box-shadow:
        0 40px 100px rgba(0,0,0,.28);

    backdrop-filter:blur(25px);

    transform:
        rotateX(-25deg)
        rotateY(8deg)
        scale(.65)
        translateY(100px);

    transition:
        .55s
        cubic-bezier(.2,.85,.2,1);
}

.modal.show .modal-box{

    transform:
        rotateX(0)
        rotateY(0)
        scale(1)
        translateY(0);
}

.modal-box h2{

    font-size:30px;

    margin-bottom:15px;
}

.modal-box p{

    line-height:1.8;
}

.close{

    float:right;

    width:37px;
    height:37px;

    border:0;

    border-radius:50%;

    background:#ffd4df;

    cursor:pointer;

    font-size:20px;

    color:#795461;
}

.friend{

    display:flex;

    align-items:center;

    gap:13px;

    background:var(--card2);

    padding:12px;

    margin:10px 0;

    border-radius:20px;

    transition:.25s;
}

.friend:hover{

    transform:
        translateX(6px)
        rotate(-1deg);
}

.friend-face{

    width:55px;
    height:55px;

    border-radius:18px;

    background:#fff;

    display:flex;

    align-items:center;
    justify-content:center;

    font-size:30px;
}

.friend b{
    display:block;
}

.friend small{
    color:var(--sub);
}


/* =====================================================
   LOGIN
===================================================== */

.login{

    position:fixed;

    inset:0;

    z-index:200;

    display:flex;

    align-items:center;

    justify-content:center;

    background:
        rgba(55,40,45,.42);

    backdrop-filter:blur(12px);

    padding:20px;
}

.login-box{

    position:relative;

    width:min(400px,92%);

    background:var(--card);

    border:
        3px solid
        rgba(255,255,255,.8);

    border-radius:40px;

    padding:38px;

    text-align:center;

    box-shadow:
        0 40px 100px rgba(0,0,0,.25);

    animation:
        loginPop
        .7s
        cubic-bezier(.2,.8,.2,1);

    overflow:hidden;
}

.login-box:before{

    content:"✦";

    position:absolute;

    top:15px;
    left:25px;

    color:#ffd05e;

    font-size:25px;
}

.login-box:after{

    content:"♡";

    position:absolute;

    right:25px;
    bottom:15px;

    color:#ffabc0;

    font-size:30px;
}

@keyframes loginPop{

    from{

        opacity:0;

        transform:
            translateY(100px)
            rotateX(-25deg)
            scale(.65);
    }

    to{

        opacity:1;

        transform:none;
    }
}

.login-icon{

    font-size:70px;

    animation:
        pudding 2s ease-in-out infinite;
}

@keyframes pudding{

    50%{
        transform:
            translateY(-8px)
            rotate(3deg);
    }
}

.login-box h2{

    color:#e7a72d;

    font-size:28px;

    margin:8px 0;
}

.login-box p{

    color:var(--sub);

    line-height:1.7;
}

.login-box input{

    width:100%;

    border:
        2px solid
        transparent;

    outline:none;

    padding:14px 17px;

    border-radius:20px;

    margin:18px 0 10px;

    background:
        rgba(255,255,255,.85);

    font-family:inherit;

    color:#554941;

    transition:.25s;
}

.login-box input:focus{

    border-color:#ffd26b;

    transform:scale(1.02);
}

.enter{

    width:100%;

    border:0;

    padding:14px;

    border-radius:20px;

    background:
        linear-gradient(
            135deg,
            #ffd76b,
            #ff9fb7
        );

    color:white;

    font-family:inherit;

    font-weight:700;

    cursor:pointer;

    transition:.3s;
}

.enter:hover{

    transform:
        translateY(-4px)
        scale(1.02);

    box-shadow:
        0 15px 30px rgba(255,160,185,.3);
}


/* =====================================================
   MOBILE
===================================================== */

@media(max-width:750px){

    .hero{

        grid-template-columns:1fr;
    }

    .avatar{

        width:190px;
        height:190px;
    }

    .info-card h1{

        font-size:32px;
    }

    .menu{

        grid-template-columns:
            repeat(2,1fr);
    }

    .quick{

        grid-template-columns:1fr 1fr;
    }

    .widgets{

        grid-template-columns:1fr;
    }

    .logo{

        font-size:20px;
    }
}

@media(max-width:450px){

    .quick{

        grid-template-columns:1fr;
    }

    .info-card{

        padding:23px;
    }

    .profile-card{

        padding:16px;
    }
}

</style>
</head>


<body>


<!-- =====================================================
     BACKGROUND
===================================================== -->

<div class="background">

    <div class="blob one"></div>
    <div class="blob two"></div>
    <div class="blob three"></div>

    <div class="cloud a"></div>
    <div class="cloud b"></div>

    <div class="star s1">✦</div>
    <div class="star s2">✧</div>
    <div class="star s3">✦</div>
    <div class="star s4">♡</div>
    <div class="star s5">✧</div>

    <div class="dot d1"></div>
    <div class="dot d2"></div>
    <div class="dot d3"></div>

</div>


<!-- =====================================================
     LOGIN
===================================================== -->

<div class="login" id="login">

    <div class="login-box">

        <div class="login-icon">
            🍮
        </div>

        <h2>
            Welcome to my world!
        </h2>

        <p>
            Nhập tên của m để bước vào<br>
            chiếc thế giới nhỏ xinh này ✨
        </p>

        <input
            id="username"
            maxlength="20"
            placeholder="Tên của bạn... 🍪"
        >

        <button
            class="enter"
            onclick="enterWorld()"
        >
            ✨ Let's go! ✨
        </button>

    </div>

</div>


<!-- =====================================================
     TOP BAR
===================================================== -->

<header class="topbar">

    <div class="logo">
        🍮 Pompurin's World
    </div>

    <div class="tools">

        <div class="tool" id="miniClock">
            🕐 --:--
        </div>

        <button
            class="tool"
            onclick="toggleDark()"
            id="themeBtn"
        >
            🌙
        </button>

    </div>

</header>


<!-- =====================================================
     CHARACTER TABS
===================================================== -->

<nav class="character-tabs">

    <button
        class="character-tab active"
        onclick="changeCharacter('pompurin',this)"
    >

        <span>🍮</span>

        Pompurin

    </button>


    <button
        class="character-tab"
        onclick="changeCharacter('mochi',this)"
    >

        <span>🐱</span>

        Khang

    </button>


    <button
        class="character-tab"
        onclick="changeCharacter('momo',this)"
    >

        <span>🐰</span>

        Chiêu Ninh

    </button>


    <button
        class="character-tab"
        onclick="changeCharacter('bubu',this)"
    >

        <span>🐥</span>

        Bubu

    </button>


    <button
        class="character-tab"
        onclick="changeCharacter('kero',this)"
    >

        <span>🐸</span>

        Kero

    </button>


    <button
        class="character-tab"
        onclick="changeCharacter('tofu',this)"
    >

        <span>🐼</span>

        Tofu

    </button>

</nav>


<!-- =====================================================
     MAIN
===================================================== -->

<main class="container">


<section class="hero">


    <!-- PROFILE -->

    <div class="profile-card">

        <div class="avatar-frame">

            <div class="avatar-deco one">
                ✦
            </div>

            <img
                id="mainAvatar"
                class="avatar"
                src="pompurin.jpg"
                alt="Pompurin"
            >

            <div class="avatar-deco two">
                ♡
            </div>

        </div>


        <div
            class="profile-name"
            id="profileName"
        >
            Pompurin 🍮
        </div>


        <div
            class="profile-tag"
            id="profileTag"
        >
            professional pudding enjoyer
        </div>


        <div class="online">
            ● online & happy
        </div>

    </div>


    <!-- INFO -->

    <div class="info-card">

        <div class="mini-title">
            ✨ Welcome to my tiny universe
        </div>


        <h1>
            Hi, I'm
            <span id="bigName">
                Pompurin!
            </span>
        </h1>


        <p
            class="description"
            id="description"
        >
            Xin chào, tên của tớ là Pompurin, founder của nhà vgc cũng như
            người làm ra chiếc web này. Hiện tại tớ đang vào vai nàng vesna từ
            tựa game genshin impact.🍮
        </p>


        <div
            class="tags"
            id="tags"
        >

            <div class="tag">
                🍮 pudding lover
            </div>

            <div class="tag">
                🎮 gamer
            </div>

            <div class="tag">
                💤 sleepy
            </div>

            <div class="tag">
                ⭐ cute lv.99
            </div>

        </div>


        <div class="quick">

            <div class="quick-box">

                <b id="age">
                    ♡
                </b>

                <small>
                    mood
                </small>

            </div>


            <div class="quick-box">

                <b id="favorite">
                    🍮
                </b>

                <small>
                    favorite
                </small>

            </div>


            <div class="quick-box">

                <b id="level">
                    99
                </b>

                <small>
                    level
                </small>

            </div>

        </div>

    </div>

</section>


<!-- =====================================================
     MENU
===================================================== -->

<section class="menu">


    <button
        class="menu-button"
        onclick="openModal('about')"
    >

        <span class="icon">
            🍮
        </span>

        About Me

    </button>


    <button
        class="menu-button"
        onclick="openModal('hobbies')"
    >

        <span class="icon">
            🎮
        </span>

        Hobbies

    </button>


    <button
        class="menu-button"
        onclick="openModal('friends')"
    >

        <span class="icon">
            👥
        </span>

        Friends

    </button>


    <button
        class="menu-button"
        onclick="openModal('social')"
    >

        <span class="icon">
            💌
        </span>

        Social

    </button>

</section>


<!-- =====================================================
     TIME + WEATHER
===================================================== -->

<section class="widgets">


    <div class="widget">

        <small>
            🕐 Local Time
        </small>

        <div
            class="big-value"
            id="clock"
        >
            --:--:--
        </div>

        <small id="date">
            Loading...
        </small>

    </div>


    <div class="widget">

        <small>
            ☁️ Weather
        </small>

        <div
            class="big-value"
            id="weather"
        >
            Loading...
        </div>

        <small id="weatherDetail">
            Đang tìm thời tiết...
        </small>

    </div>


</section>

</main>


<!-- =====================================================
     MODAL
===================================================== -->

<div
    class="modal"
    id="modal"
    onclick="closeOutside(event)"
>

    <div class="modal-box">

        <button
            class="close"
            onclick="closeModal()"
        >
            ×
        </button>

        <div id="modalContent"></div>

    </div>

</div>


<script>

/* =====================================================
   CHARACTER DATA
===================================================== */

const characters = {

    pompurin:{

        name:"Pompurin 🍮",

        bigName:"Pompurin!",

        tag:"professional pudding enjoyer",

        image:"pompurin.jpg",

        description:
        "Một chiếc sinh vật thích pudding, ngủ, chơi game và sống một cuộc đời hơi lười nhưng cực kỳ đáng yêu 🍮",

        mood:"♡",

        favorite:"🍮",

        level:"99",

        tags:[
            "🍮 pudding lover",
            "🎮 gamer",
            "💤 sleepy",
            "⭐ cute lv.99"
        ]

    },


    mochi:{

        name:"Mochi 🐱",

        bigName:"Mochi!",

        tag:"professional chaos maker",

        image:"",

        description:
        "Một chú mèo nhỏ có niềm đam mê đặc biệt với việc leo lên những nơi không nên leo và phá đồ một cách rất đáng yêu 🐱",

        mood:"😼",

        favorite:"🐟",

        level:"72",

        tags:[
            "🐱 cat",
            "🐟 fish lover",
            "💥 chaotic",
            "✨ fluffy"
        ]

    },


    momo:{

        name:"Momo 🐰",

        bigName:"Momo!",

        tag:"carrot enthusiast",

        image:"",

        description:
        "Momo là một bé thỏ hiền lành, thích cà rốt, hoa và những buổi chiều nằm dưới nắng 🌷",

        mood:"🌸",

        favorite:"🥕",

        level:"65",

        tags:[
            "🐰 bunny",
            "🥕 carrot",
            "🌷 flower lover",
            "☀️ sunshine"
        ]

    },


    bubu:{

        name:"Bubu 🐥",

        bigName:"Bubu!",

        tag:"tiny confused bird",

        image:"",

        description:
        "Bubu thường không biết mình đang làm gì nhưng bằng một cách kỳ lạ nào đó luôn khiến mọi người cười 😂",

        mood:"😂",

        favorite:"🌽",

        level:"58",

        tags:[
            "🐥 bird",
            "🌽 corn",
            "😂 funny",
            "❓ confused"
        ]

    },


    kero:{

        name:"Kero 🐸",

        bigName:"Kero!",

        tag:"CEO of doing nothing",

        image:"",

        description:
        "Kero có triết lý sống rất đơn giản: nếu việc đó có thể làm ngày mai thì tại sao phải làm hôm nay? 🐸",

        mood:"😴",

        favorite:"🍃",

        level:"88",

        tags:[
            "🐸 frog",
            "😴 lazy",
            "🍃 chill",
            "👑 CEO"
        ]

    },


    tofu:{

        name:"Tofu 🐼",

        bigName:"Tofu!",

        tag:"snack collector",

        image:"",

        description:
        "Tofu thích sưu tầm đồ ăn vặt và luôn có một chiếc túi đầy snack dù chẳng ai biết nó lấy ở đâu 🐼",

        mood:"🍪",

        favorite:"🍪",

        level:"76",

        tags:[
            "🐼 panda",
            "🍪 snack",
            "🎒 collector",
            "💖 friendly"
        ]

    }

};


/* =====================================================
   CHANGE CHARACTER
===================================================== */

function changeCharacter(id,button){

    const c = characters[id];

    document
        .querySelectorAll(".character-tab")
        .forEach(tab=>{
            tab.classList.remove("active");
        });

    button.classList.add("active");


    const avatar =
        document.getElementById("mainAvatar");

    /*
       Nếu nhân vật chưa có ảnh,
       tạm dùng emoji.
    */

    if(c.image){

        avatar.src = c.image;

        avatar.style.display = "block";

    }else{

        avatar.style.display = "none";

        avatar.parentElement.style.fontSize="100px";

        avatar.parentElement.innerHTML =
            `<div style="
                font-size:100px;
                padding:50px 0;
            ">${id==="mochi"?"🐱":
                id==="momo"?"🐰":
                id==="bubu"?"🐥":
                id==="kero"?"🐸":"🐼"}
            </div>`;

    }


    document.getElementById("profileName")
        .textContent = c.name;

    document.getElementById("bigName")
        .textContent = c.bigName;

    document.getElementById("profileTag")
        .textContent = c.tag;

    document.getElementById("description")
        .textContent = c.description;

    document.getElementById("age")
        .textContent = c.mood;

    document.getElementById("favorite")
        .textContent = c.favorite;

    document.getElementById("level")
        .textContent = c.level;


    document.getElementById("tags").innerHTML =
        c.tags.map(tag =>
            `<div class="tag">${tag}</div>`
        ).join("");

}


/* =====================================================
   LOGIN
===================================================== */

function enterWorld(){

    const input =
        document.getElementById("username");

    const name =
        input.value.trim();

    if(name){

        localStorage.setItem(
            "visitorName",
            name
        );

    }

    document.getElementById("login")
        .style.display="none";
}


window.addEventListener("load",()=>{

    if(localStorage.getItem("visitorName")){

        document.getElementById("login")
            .style.display="none";

    }

});


/* =====================================================
   DARK MODE
===================================================== */

function toggleDark(){

    document.body
        .classList.toggle("dark");

    const dark =
        document.body.classList.contains("dark");

    localStorage.setItem(
        "darkMode",
        dark
    );

    document.getElementById("themeBtn")
        .textContent =
        dark ? "☀️" : "🌙";
}


if(localStorage.getItem("darkMode")==="true"){

    document.body.classList.add("dark");

    document.getElementById("themeBtn")
        .textContent="☀️";

}


/* =====================================================
   CLOCK
===================================================== */

function updateClock(){

    const now = new Date();

    const time =
        now.toLocaleTimeString(
            "vi-VN",
            {
                hour:"2-digit",
                minute:"2-digit",
                second:"2-digit"
            }
        );

    const date =
        now.toLocaleDateString(
            "vi-VN",
            {
                weekday:"long",
                day:"numeric",
                month:"long",
                year:"numeric"
            }
        );


    document.getElementById("clock")
        .textContent=time;

    document.getElementById("miniClock")
        .textContent="🕐 "+time;

    document.getElementById("date")
        .textContent=date;

}

updateClock();

setInterval(
    updateClock,
    1000
);


/* =====================================================
   WEATHER
===================================================== */

function weatherText(code){

    if(code===0)
        return "☀️ Trời quang";

    if(code<=3)
        return "🌤️ Có mây";

    if(code<=48)
        return "🌫️ Sương mù";

    if(code<=67)
        return "🌧️ Có mưa";

    if(code<=77)
        return "❄️ Tuyết";

    if(code<=82)
        return "🌦️ Mưa rào";

    if(code>=95)
        return "⛈️ Dông";

    return "☁️ Thời tiết";
}


if(navigator.geolocation){

    navigator.geolocation.getCurrentPosition(

        position=>{

            const lat =
                position.coords.latitude;

            const lon =
                position.coords.longitude;


            fetch(
                `https://api.open-meteo.com/v1/forecast?latitude=${lat}&longitude=${lon}&current=temperature_2m,weather_code`
            )

            .then(res=>res.json())

            .then(data=>{

                const current =
                    data.current;

                document.getElementById("weather")
                    .textContent =
                    weatherText(
                        current.weather_code
                    );

                document.getElementById("weatherDetail")
                    .textContent =
                    `${Math.round(current.temperature_2m)}°C • hiện tại`;

            });

        },

        ()=>{

            document.getElementById("weather")
                .textContent="🌤️ Weather";

            document.getElementById("weatherDetail")
                .textContent=
                "Cho phép vị trí để xem thời tiết";

        }

    );

}


/* =====================================================
   MODALS
===================================================== */

const modalContent = {

    about:`

        <h2>🍮 About Me</h2>

        <p>
            Xin chào! Tớ là Pompurin ✨
        </p>

        <br>

        <p>
            🍮 Pudding là chân ái<br>
            🎮 Game là niềm vui<br>
            💤 Ngủ là nghệ thuật<br>
            💛 Cute là một lối sống
        </p>

        <br>

        <p>
            <b>Current mission:</b><br>
            Tìm pudding ngon → ăn → ngủ → lặp lại.
        </p>

    `,


    hobbies:`

        <h2>🎮 Hobbies</h2>

        <p>
            🎮 Chơi game<br><br>
            🎨 Vẽ và thiết kế<br><br>
            📱 Lướt mạng xã hội<br><br>
            🎧 Nghe nhạc<br><br>
            🍮 Ăn pudding<br><br>
            💤 Ngủ
        </p>

    `,


    friends:`

        <h2>👥 My Friends</h2>

        <div class="friend">

            <div class="friend-face">
                🐱
            </div>

            <div>
                <b>Mochi</b>
                <small>
                    Chuyên gia phá đồ.
                </small>
            </div>

        </div>


        <div class="friend">

            <div class="friend-face">
                🐰
            </div>

            <div>
                <b>Momo</b>
                <small>
                    Cà rốt là tất cả.
                </small>
            </div>

        </div>


        <div class="friend">

            <div class="friend-face">
                🐥
            </div>

            <div>
                <b>Bubu</b>
                <small>
                    Không hiểu gì nhưng vẫn vui.
                </small>
            </div>

        </div>


        <div class="friend">

            <div class="friend-face">
                🐸
            </div>

            <div>
                <b>Kero</b>
                <small>
                    CEO của hội lười.
                </small>
            </div>

        </div>


        <div class="friend">

            <div class="friend-face">
                🐼
            </div>

            <div>
                <b>Tofu</b>
                <small>
                    Snack collector.
                </small>
            </div>

        </div>

    `,


    social:`

        <h2>💌 Social</h2>

        <p>
            📸 Instagram<br><br>
            🎮 Discord<br><br>
            🎵 TikTok<br><br>
            💻 GitHub
        </p>

        <br>

        <small>
            M thay bằng link thật của m sau nhé ✨
        </small>

    `

};


function openModal(type){

    document.getElementById("modalContent")
        .innerHTML =
        modalContent[type];

    document.getElementById("modal")
        .classList.add("show");

}


function closeModal(){

    document.getElementById("modal")
        .classList.remove("show");

}


function closeOutside(event){

    if(event.target.id==="modal"){

        closeModal();

    }

}


document.addEventListener(
    "keydown",
    event=>{

        if(event.key==="Escape"){

            closeModal();

        }

    }
);

</script>

</body>
</html>
