<!DOCTYPE html>
<html lang="vi">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Pompurin's Little World 🍮</title>

<style>
@import url('https://fonts.googleapis.com/css2?family=Quicksand:wght@400;500;600;700&family=Pacifico&display=swap');

*{
    box-sizing:border-box;
    margin:0;
    padding:0;
}

:root{
    --bg:#fff8df;
    --card:rgba(255,255,255,.72);
    --text:#574b42;
    --sub:#88796e;
    --yellow:#ffd86b;
    --pink:#ff9eb5;
    --blue:#aee7ff;
    --shadow:0 20px 50px rgba(122,93,45,.15);
}

body.dark{
    --bg:#242331;
    --card:rgba(45,44,59,.82);
    --text:#fff5e8;
    --sub:#c9c0c5;
    --shadow:0 20px 50px rgba(0,0,0,.35);
}

body{
    font-family:'Quicksand',sans-serif;
    color:var(--text);
    background:var(--bg);
    min-height:100vh;
    overflow-x:hidden;
    transition:.5s;
}

/* ===== BACKGROUND ===== */

.background{
    position:fixed;
    inset:0;
    z-index:-2;
    overflow:hidden;
    background:
        radial-gradient(circle at 10% 20%, #ffe7a8 0 8%, transparent 25%),
        radial-gradient(circle at 90% 15%, #ffd6e2 0 8%, transparent 25%),
        radial-gradient(circle at 50% 100%, #ccefff 0 10%, transparent 30%);
}

body.dark .background{
    background:
        radial-gradient(circle at 10% 20%, #49415d 0 8%, transparent 25%),
        radial-gradient(circle at 90% 15%, #533d55 0 8%, transparent 25%),
        #242331;
}

.cloud{
    position:absolute;
    width:180px;
    height:60px;
    background:rgba(255,255,255,.55);
    border-radius:100px;
    filter:blur(1px);
    animation:cloud 20s linear infinite;
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
    left:30px;
    bottom:0;
}

.cloud:after{
    width:100px;
    height:100px;
    right:25px;
    bottom:0;
}

.c1{top:12%;left:-220px;}
.c2{top:65%;left:-300px;animation-delay:8s;transform:scale(.7);}

@keyframes cloud{
    to{transform:translateX(calc(100vw + 500px));}
}

.bubble{
    position:absolute;
    width:12px;
    height:12px;
    border-radius:50%;
    background:rgba(255,255,255,.55);
    animation:float 7s ease-in-out infinite;
}

.b1{left:10%;top:40%}
.b2{left:80%;top:30%;animation-delay:2s}
.b3{left:65%;top:75%;animation-delay:4s}
.b4{left:25%;top:80%;animation-delay:1s}

@keyframes float{
    50%{transform:translateY(-30px) scale(1.4);opacity:.4}
}

/* ===== TOP BAR ===== */

.topbar{
    width:min(1100px,92%);
    margin:20px auto;
    display:flex;
    justify-content:space-between;
    align-items:center;
    gap:10px;
}

.logo{
    font-family:'Pacifico',cursive;
    font-size:25px;
    color:#e7a52d;
}

.tools{
    display:flex;
    gap:8px;
    align-items:center;
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
    transition:.25s;
}

.tool:hover{
    transform:translateY(-3px) rotate(-2deg);
}

/* ===== MAIN ===== */

.container{
    width:min(1000px,92%);
    margin:25px auto 50px;
}

/* HERO */

.hero{
    display:grid;
    grid-template-columns:240px 1fr;
    gap:25px;
    align-items:stretch;
}

.profile{
    background:var(--card);
    border:2px solid rgba(255,255,255,.7);
    border-radius:35px;
    padding:18px;
    text-align:center;
    box-shadow:var(--shadow);
    backdrop-filter:blur(20px);
    transform-style:preserve-3d;
    transition:.4s;
}

.profile:hover{
    transform:perspective(800px) rotateY(-5deg) rotateX(3deg);
}

.avatar{
    width:175px;
    height:175px;
    object-fit:cover;
    border-radius:30px;
    border:6px solid white;
    box-shadow:0 12px 30px rgba(0,0,0,.12);
}

.name{
    margin-top:12px;
    font-size:27px;
    font-weight:700;
}

.tag{
    color:var(--sub);
    font-size:13px;
}

.status{
    display:inline-block;
    margin-top:10px;
    background:#dff8df;
    color:#55a85c;
    padding:5px 12px;
    border-radius:30px;
    font-size:12px;
}

/* INFO */

.info{
    display:flex;
    flex-direction:column;
    justify-content:center;
    background:var(--card);
    border-radius:35px;
    padding:30px;
    box-shadow:var(--shadow);
    backdrop-filter:blur(20px);
}

.welcome{
    font-size:14px;
    color:var(--sub);
}

.info h1{
    font-size:42px;
    margin:5px 0;
}

.info h1 span{
    color:#efa72d;
}

.info p{
    line-height:1.7;
    max-width:650px;
}

.stats{
    display:flex;
    gap:10px;
    margin-top:18px;
    flex-wrap:wrap;
}

.stat{
    background:rgba(255,255,255,.55);
    padding:10px 16px;
    border-radius:18px;
    font-size:13px;
}

/* ===== MENU ===== */

.menu{
    margin-top:25px;
    display:grid;
    grid-template-columns:repeat(4,1fr);
    gap:12px;
}

.menu button{
    border:0;
    padding:17px 10px;
    border-radius:23px;
    background:var(--card);
    color:var(--text);
    font-family:inherit;
    font-weight:700;
    cursor:pointer;
    box-shadow:var(--shadow);
    backdrop-filter:blur(15px);
    transition:.3s;
}

.menu button span{
    display:block;
    font-size:27px;
    margin-bottom:5px;
}

.menu button:hover{
    transform:
        perspective(500px)
        translateY(-7px)
        rotateX(8deg)
        rotateY(-5deg);
    box-shadow:0 25px 45px rgba(122,93,45,.22);
}

/* ===== CLOCK / WEATHER ===== */

.widgets{
    display:grid;
    grid-template-columns:1fr 1fr;
    gap:12px;
    margin-top:12px;
}

.widget{
    background:var(--card);
    padding:18px 20px;
    border-radius:25px;
    box-shadow:var(--shadow);
    backdrop-filter:blur(15px);
}

.widget small{
    color:var(--sub);
}

.clock{
    font-size:25px;
    font-weight:700;
    margin-top:4px;
}

/* ===== MODAL 3D ===== */

.modal{
    position:fixed;
    inset:0;
    background:rgba(30,25,30,.45);
    backdrop-filter:blur(8px);
    display:flex;
    justify-content:center;
    align-items:center;
    padding:20px;
    opacity:0;
    pointer-events:none;
    transition:.3s;
    perspective:1200px;
    z-index:20;
}

.modal.show{
    opacity:1;
    pointer-events:auto;
}

.modal-box{
    width:min(600px,95%);
    max-height:80vh;
    overflow:auto;
    background:var(--card);
    border:2px solid rgba(255,255,255,.7);
    border-radius:35px;
    padding:30px;
    box-shadow:0 40px 100px rgba(0,0,0,.25);
    backdrop-filter:blur(25px);
    transform:rotateX(-20deg) scale(.7) translateY(80px);
    transition:.5s cubic-bezier(.2,.8,.2,1);
}

.modal.show .modal-box{
    transform:rotateX(0) scale(1) translateY(0);
}

.modal-box h2{
    font-size:30px;
    margin-bottom:12px;
}

.close{
    float:right;
    border:0;
    width:35px;
    height:35px;
    border-radius:50%;
    background:#ffd3df;
    cursor:pointer;
    font-size:18px;
}

.friend{
    display:flex;
    align-items:center;
    gap:15px;
    padding:13px;
    background:rgba(255,255,255,.4);
    border-radius:20px;
    margin:10px 0;
}

.friend-avatar{
    width:55px;
    height:55px;
    border-radius:18px;
    object-fit:cover;
}

.friend b{
    display:block;
}

.friend small{
    color:var(--sub);
}

/* ===== LOGIN ===== */

.login{
    position:fixed;
    inset:0;
    z-index:50;
    display:flex;
    align-items:center;
    justify-content:center;
    background:rgba(40,30,20,.45);
    backdrop-filter:blur(10px);
}

.login-box{
    width:min(390px,90%);
    background:var(--card);
    border-radius:35px;
    padding:35px;
    text-align:center;
    box-shadow:0 40px 100px rgba(0,0,0,.25);
    animation:loginPop .7s cubic-bezier(.2,.8,.2,1);
}

@keyframes loginPop{
    from{
        opacity:0;
        transform:translateY(100px) rotateX(-20deg) scale(.7);
    }
    to{
        opacity:1;
        transform:none;
    }
}

.login-icon{
    font-size:65px;
}

.login-box h2{
    font-family:'Pacifico',cursive;
    color:#e7a52d;
    margin:10px;
}

.login-box input{
    width:100%;
    border:0;
    outline:0;
    padding:14px 18px;
    border-radius:18px;
    margin:12px 0;
    background:rgba(255,255,255,.8);
    font-family:inherit;
}

.enter{
    width:100%;
    border:0;
    padding:14px;
    border-radius:20px;
    background:linear-gradient(135deg,#ffd86b,#ff9eb5);
    color:white;
    font-weight:700;
    font-family:inherit;
    cursor:pointer;
    transition:.25s;
}

.enter:hover{
    transform:translateY(-3px) scale(1.02);
}

/* ===== RESPONSIVE ===== */

@media(max-width:700px){
    .hero{
        grid-template-columns:1fr;
    }

    .avatar{
        width:140px;
        height:140px;
    }

    .info h1{
        font-size:32px;
    }

    .menu{
        grid-template-columns:repeat(2,1fr);
    }

    .widgets{
        grid-template-columns:1fr;
    }

    .topbar{
        align-items:flex-start;
    }

    .logo{
        font-size:20px;
    }
}
</style>
</head>

<body>

<div class="background">
    <div class="cloud c1"></div>
    <div class="cloud c2"></div>

    <div class="bubble b1"></div>
    <div class="bubble b2"></div>
    <div class="bubble b3"></div>
    <div class="bubble b4"></div>
</div>

<!-- LOGIN -->
<div class="login" id="login">
    <div class="login-box">
        <div class="login-icon">🍮</div>

        <h2>Welcome!</h2>

        <p>
            Chào mừng đến với<br>
            <b>Pompurin's Little World</b> ✨
        </p>

        <input
            id="username"
            type="text"
            placeholder="Tên của bạn là gì? 🍪"
            maxlength="20"
        >

        <button class="enter" onclick="enterWorld()">
            ✨ Vào thế giới ✨
        </button>
    </div>
</div>


<!-- TOP BAR -->
<header class="topbar">

    <div class="logo">
        🍮 Pompurin
    </div>

    <div class="tools">

        <div class="tool" id="miniClock">
            🕐 --:--
        </div>

        <button class="tool" onclick="toggleDark()">
            🌙
        </button>

    </div>

</header>


<main class="container">

    <!-- HERO -->
    <section class="hero">

        <div class="profile">

            <img
                src="pompurin.jpg"
                class="avatar"
                alt="Pompurin"
            >

            <div class="name">
                Pompurin 🍮
            </div>

            <div class="tag">
                professional pudding enjoyer
            </div>

            <div class="status">
                ● online & happy
            </div>

        </div>


        <div class="info">

            <div class="welcome">
                ✨ Welcome to my tiny world
            </div>

            <h1>
                Hi, I'm <span>Pompurin!</span>
            </h1>

            <p>
                Một chiếc profile nhỏ xinh dành cho một sinh vật
                thích pudding, ngủ, chơi game và làm mọi thứ
                theo cách hơi... lười một tí 🍮
            </p>

            <div class="stats">

                <div class="stat">
                    🍮 Pudding lover
                </div>

                <div class="stat">
                    🎮 Gamer
                </div>

                <div class="stat">
                    💤 Sleep expert
                </div>

                <div class="stat">
                    ⭐ Lv. 99 Cute
                </div>

            </div>

        </div>

    </section>


    <!-- MENU -->
    <section class="menu">

        <button onclick="openModal('about')">
            <span>🍮</span>
            About Me
        </button>

        <button onclick="openModal('friends')">
            <span>👥</span>
            Friends
        </button>

        <button onclick="openModal('hobbies')">
            <span>🎮</span>
            Hobbies
        </button>

        <button onclick="openModal('social')">
            <span>💌</span>
            Social
        </button>

    </section>


    <!-- WIDGETS -->
    <section class="widgets">

        <div class="widget">
            <small>🕐 Local Time</small>
            <div class="clock" id="clock">
                --:--:--
            </div>
            <small id="date">
                Loading...
            </small>
        </div>


        <div class="widget">
            <small>☁️ Weather</small>

            <div class="clock" id="weather">
                Loading...
            </div>

            <small id="weatherDetail">
                Đang tìm thời tiết...
            </small>
        </div>

    </section>

</main>


<!-- 3D MODAL -->
<div class="modal" id="modal" onclick="closeOutside(event)">

    <div class="modal-box">

        <button class="close" onclick="closeModal()">
            ×
        </button>

        <div id="modalContent"></div>

    </div>

</div>


<script>

/* =========================
   LOGIN
========================= */

function enterWorld(){

    const input = document.getElementById("username");
    const name = input.value.trim();

    if(name){
        localStorage.setItem("visitorName", name);
    }

    document.getElementById("login").style.display = "none";
}

window.addEventListener("load", () => {

    const saved = localStorage.getItem("visitorName");

    if(saved){
        document.getElementById("login").style.display = "none";
    }

});


/* =========================
   DARK MODE
========================= */

function toggleDark(){

    document.body.classList.toggle("dark");

    const dark = document.body.classList.contains("dark");

    localStorage.setItem("darkMode", dark);

}

if(localStorage.getItem("darkMode") === "true"){
    document.body.classList.add("dark");
}


/* =========================
   CLOCK
========================= */

function updateClock(){

    const now = new Date();

    const time =
        now.toLocaleTimeString("vi-VN", {
            hour:"2-digit",
            minute:"2-digit",
            second:"2-digit"
        });

    const date =
        now.toLocaleDateString("vi-VN", {
            weekday:"long",
            day:"numeric",
            month:"long",
            year:"numeric"
        });

    document.getElementById("clock").textContent = time;
    document.getElementById("miniClock").textContent = "🕐 " + time;
    document.getElementById("date").textContent = date;
}

updateClock();
setInterval(updateClock,1000);


/* =========================
   WEATHER
========================= */

function weatherText(code){

    if(code === 0) return "☀️ Trời quang";
    if(code <= 3) return "🌤️ Có mây";
    if(code <= 48) return "🌫️ Sương mù";
    if(code <= 67) return "🌧️ Có mưa";
    if(code <= 77) return "❄️ Tuyết";
    if(code <= 82) return "🌦️ Mưa rào";
    if(code >= 95) return "⛈️ Dông";

    return "☁️ Thời tiết";
}

if(navigator.geolocation){

    navigator.geolocation.getCurrentPosition(

        position => {

            const lat = position.coords.latitude;
            const lon = position.coords.longitude;

            fetch(
                `https://api.open-meteo.com/v1/forecast?latitude=${lat}&longitude=${lon}&current=temperature_2m,weather_code`
            )
            .then(res => res.json())
            .then(data => {

                const current = data.current;

                document.getElementById("weather").textContent =
                    weatherText(current.weather_code);

                document.getElementById("weatherDetail").textContent =
                    `${Math.round(current.temperature_2m)}°C • hiện tại`;

            })
            .catch(() => {

                document.getElementById("weather").textContent =
                    "☁️ Không tải được";

                document.getElementById("weatherDetail").textContent =
                    "Kiểm tra kết nối mạng";

            });

        },

        () => {

            document.getElementById("weather").textContent =
                "🌤️ Weather";

            document.getElementById("weatherDetail").textContent =
                "Cho phép vị trí để xem thời tiết";

        }

    );

}


/* =========================
   3D MODALS
========================= */

const contents = {

about: `
    <h2>🍮 About Me</h2>

    <p>
        Xin chào! Tớ là Pompurin ✨
    </p>

    <br>

    <p>
        🍮 Thích pudding<br>
        💤 Thích ngủ<br>
        🎮 Thích chơi game<br>
        🐶 Thích những thứ đáng yêu<br>
        💛 Ghét việc phải dậy sớm
    </p>

    <br>

    <p>
        <b>Current mission:</b><br>
        Tìm một chiếc pudding ngon và ngủ một giấc thật dài.
    </p>
`,

friends: `
    <h2>👥 My Friends</h2>

    <div class="friend">
        <div style="font-size:35px">🐱</div>
        <div>
            <b>Mochi</b>
            <small>Cat • chuyên gia phá đồ</small>
        </div>
    </div>

    <div class="friend">
        <div style="font-size:35px">🐰</div>
        <div>
            <b>Momo</b>
            <small>Rabbit • thích ăn cà rốt</small>
        </div>
    </div>

    <div class="friend">
        <div style="font-size:35px">🐥</div>
        <div>
            <b>Bubu</b>
            <small>Chicken • hơi ngáo</small>
        </div>
    </div>

    <div class="friend">
        <div style="font-size:35px">🐸</div>
        <div>
            <b>Kero</b>
            <small>Frog • CEO của hội lười</small>
        </div>
    </div>
`,

hobbies: `
    <h2>🎮 Hobbies</h2>

    <p>
        🎮 Chơi game<br><br>
        📱 Lướt mạng xã hội<br><br>
        🎨 Vẽ / thiết kế<br><br>
        🍮 Ăn pudding<br><br>
        💤 Ngủ<br><br>
        🎧 Nghe nhạc
    </p>
`,

social: `
    <h2>💌 Social</h2>

    <p>
        🌐 Internet<br><br>
        📸 Instagram<br><br>
        🎮 Discord<br><br>
        🎵 TikTok<br><br>
        💻 GitHub
    </p>

    <br>

    <small>
        Thay các mục trên bằng link social thật của m nhé ✨
    </small>
`

};


function openModal(type){

    document.getElementById("modalContent").innerHTML =
        contents[type];

    document.getElementById("modal").classList.add("show");

}

function closeModal(){

    document.getElementById("modal").classList.remove("show");

}

function closeOutside(e){

    if(e.target.id === "modal"){
        closeModal();
    }

}

document.addEventListener("keydown", e => {

    if(e.key === "Escape"){
        closeModal();
    }

});

</script>

</body>
</html>
