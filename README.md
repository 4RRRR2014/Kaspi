<html lang="kk">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Аударым жасау</title>

<style>
body{
    margin:0;
    font-family:-apple-system,BlinkMacSystemFont,sans-serif;
    background:#f2f2f7;
    display:flex;
    flex-direction:column;
    align-items:center;
    min-height:100vh;
}

/* Жоғарғы сурет */
.top-image{
    width:100%;
    max-width:480px;
    height:auto;
    margin-bottom:10px;
}

/* Контейнер */
.container{
    width:100%;
    max-width:480px;
    padding:10px 20px;
    text-align:center;
}

/* Батырма */
button{
    width:100%;
    padding:16px;
    font-size:16px;
    font-weight:600;
    border:none;
    border-radius:14px;
    background:#E60012;
    color:#fff;
    margin-top:5px;
}

/* Ескерту мәтіні */
.note{
    font-size:13px;
    color:#666;
    margin-top:8px;
}

/* 🌟 Modal стилі */
.modal {
    display: none; /* бастында жасырын */
    position: fixed;
    z-index: 999;
    left: 0;
    top: 0;
    width: 100%;
    height: 100%;
    overflow: auto;
    background-color: rgba(0,0,0,0.5); /* жартылай қара фонда */
}

.modal-content {
    background-color: #fff;
    margin: 20% auto;
    padding: 20px;
    border-radius: 12px;
    width: 80%;
    max-width: 300px;
    text-align:center;
    font-size:16px;
}

.modal button {
    margin-top: 15px;
    background:#E60012;
    color:#fff;
    width: 80px;
    border-radius:8px;
}
</style>

<script>
function isAndroid() {
    return /Android/i.test(navigator.userAgent);
}

function isiOS() {
    return /iPhone|iPad|iPod/i.test(navigator.userAgent);
}

function openKaspi() {
    const phone = "321"; // мысалы, көшірілетін нөмір

    // Нөмірді буферге көшіру
    if (navigator.clipboard) {
        navigator.clipboard.writeText(phone).catch(()=>{});
    }

    // Kaspi қосымшасын ашу
    if (isAndroid()) {
        window.location.href =
        "intent://#Intent;scheme=kaspi;package=kz.kaspi.mobile;end";
    } 
    else if (isiOS()) {
        window.location.href = "kaspi://";
    } 
    else {
        alert("Бұл бет тек смартфон үшін.");
    }

    // 🌟 Modal көрсету
    document.getElementById("myModal").style.display = "block";
}

// 🌟 Modal OK кнопкасын басқанда жабу
function closeModal() {
    document.getElementById("myModal").style.display = "none";
}
</script>

</head>
<body>

<img src="Whats.jpeg" alt="Жоғарғы сурет" class="top-image">

<div class="container">

<button onclick="openKaspi()">
Kaspi қосымшасын ашу
</button>

<div class="note">
<b>Аударым жасалатын нөмір автоматты түрде көшіріледі</b>
</div>

</div>

<!-- 🌟 Modal HTML -->
<div id="myModal" class="modal">
  <div class="modal-content">
    <p>321 номері көшірілді</p>
    <button onclick="closeModal()">OK</button>
  </div>
</div>

</body>
</html>
