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
}

/* Контейнер */
.container{
    width:100%;
    max-width:480px;
    padding:20px;
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


}

.note{
    font-size:13px;
    color:#666;
    margin-top:10px;
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
    const phone = "7781407102";

    if (navigator.clipboard) {
        navigator.clipboard.writeText(phone).catch(()=>{});
    }

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

<!-- 📌 ЖОҒАРҒЫ СУРЕТ -->
<img src="Whats.jpeg" alt="Жоғарғы сурет" class="top-image">

<div class="container">

<button onclick="openKaspi()">
Kaspi қосымшасын ашу
</button>

<div class="note">
<b>Аударым жасалатын нөмір автоматты түрде көшіріледі</b>
</div>


</div>

</body>
</html>
