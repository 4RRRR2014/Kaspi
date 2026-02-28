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

/* Modal стилі */
.modal {
    display: none;
    position: fixed;
    z-index: 999;
    left: 0;
    top: 0;
    width: 100%;
    height: 100%;
    overflow: auto;
    background-color: rgba(0,0,0,0.5);
}

.modal-content {
    background-color: #fff;
    margin: 25% auto;
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

let kaspiPhone = "321"; // Көшірілетін нөмір

// 1️⃣ Батырманы басқанда modal шығу
function showModal() {
    // Нөмірді буферге көшіру
    if (navigator.clipboard) {
        navigator.clipboard.writeText(kaspiPhone).catch(()=>{});
    }

    // Modal көрсету
    document.getElementById("myModal").style.display = "block";
}

// 2️⃣ OK батырмасын басқанда Kaspi қосымшасын ашу
function okAndOpenKaspi() {
    document.getElementById("myModal").style.display = "none";

    if (isAndroid()) {
        window.location.href =
        "intent://#Intent;scheme=kaspi;package=kz.kaspi.mobile;end";
    } 
    else if (isiOS()) {
        window.location.href = "https://kaspi.kz";
    } 
    else {
        alert("Бұл бет тек смартфон үшін.");
    }
}
</script>

</head>
<body>

<img src="Whats.jpeg" alt="Жоғарғы сурет" class="top-image">

<div class="container">

<button onclick="showModal()">
Kaspi қосымшасын ашу
</button>

</div>

<!-- Modal -->
<div id="myModal" class="modal">
  <div class="modal-content">
    <p>Аударым жасалатын нөмір автоматты түрде көшіріледі</p>
    <button onclick="okAndOpenKaspi()">OK</button>
  </div>
</div>

</body>
</html>
