<!DOCTYPE html>
<html lang="kk">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1, maximum-scale=1, user-scalable=no">
<title>Аударым жасау</title>

<style>
* {
    box-sizing: border-box;
}

html, body {
    margin: 0;
    padding: 0;
    font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif;
    background: #f2f2f7;
}

.wrapper {
    max-width: 480px;
    margin: 0 auto;
    min-height: 100vh;
    display: flex;
    flex-direction: column;
}

.header {
    background: #111;
    color: #fff;
    padding: 18px;
    text-align: center;
    font-size: 18px;
    font-weight: 600;
}

.card {
    background: #fff;
    margin: 20px 16px;
    padding: 20px;
    border-radius: 16px;
    box-shadow: 0 4px 16px rgba(0,0,0,0.06);
}

.phone {
    font-size: 22px;
    font-weight: 600;
    text-align: center;
    margin: 16px 0;
}

.button {
    width: 100%;
    padding: 16px;
    border-radius: 14px;
    font-size: 16px;
    font-weight: 600;
    border: none;
    margin-top: 12px;
    cursor: pointer;
}

.kaspi {
    background: #E60012;
    color: white;
}

.halyk {
    background: #009245;
    color: white;
}

.note {
    text-align: center;
    font-size: 13px;
    color: #777;
    margin-top: 12px;
}

.desktop-warning {
    display: none;
    text-align: center;
    padding: 40px;
    font-size: 16px;
}
</style>

<script>
function isMobile() {
    return /Android|iPhone|iPad|iPod/i.test(navigator.userAgent);
}

function copy(phone) {
    if (navigator.clipboard) {
        navigator.clipboard.writeText(phone).catch(()=>{});
    }
}

function openKaspi(phone) {
    copy(phone);
    var start = Date.now();
    window.location.href = "kaspi://transfers";
    setTimeout(function () {
        if (Date.now() - start < 2000) {
            window.location.href = "https://kaspi.kz";
        }
    }, 1500);
}

function openHalyk(phone) {
    copy(phone);
    var start = Date.now();
    window.location.href = "halyk://";
    setTimeout(function () {
        if (Date.now() - start < 2000) {
            window.location.href = "https://halykbank.kz";
        }
    }, 1500);
}

window.onload = function() {
    if (!isMobile()) {
        document.getElementById("mobileContent").style.display = "none";
        document.getElementById("desktopWarning").style.display = "block";
    }
}
</script>

</head>
<body>

<div class="wrapper">

<div id="mobileContent">
    <div class="header">Аударым жасау</div>

    <div class="card">
        <div style="text-align:center;">Аударым нөмірі</div>
        <div class="phone">+7 700 123 45 67</div>

        <button class="button kaspi"
        onclick="openKaspi('77001234567')">
        Kaspi арқылы төлеу
        </button>

        <button class="button halyk"
        onclick="openHalyk('77001234567')">
        Halyk арқылы төлеу
        </button>

        <div class="note">
        Нөмір автоматты түрде көшіріледі
        </div>
    </div>
</div>

<div id="desktopWarning" class="desktop-warning">
Бұл бет тек смартфон арқылы төлем жасауға арналған.
</div>

</div>

</body>
</html>
