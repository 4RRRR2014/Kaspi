<!DOCTYPE html>
<html lang="kk">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Kaspi ашу</title>

<style>
body{
    margin:0;
    font-family:-apple-system,BlinkMacSystemFont,sans-serif;
    background:#f2f2f7;
    display:flex;
    justify-content:center;
    align-items:center;
    height:100vh;
}
button{
    width:90%;
    max-width:400px;
    padding:16px;
    font-size:16px;
    font-weight:600;
    border:none;
    border-radius:14px;
    background:#E60012;
    color:#fff;
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
}
</script>

</head>
<body>

<button onclick="openKaspi()">
Kaspi қосымшасын ашу
</button>

</body>
</html>
