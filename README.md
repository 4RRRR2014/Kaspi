<html lang="kk">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Kaspi Төлем</title>

<style>
body {
    margin: 0;
    font-family: -apple-system, BlinkMacSystemFont, sans-serif;
    background: #f2f2f7;
    text-align: center;
}

.container {
    max-width: 480px;
    margin: auto;
    padding: 40px 20px;
}

button {
    width: 100%;
    padding: 16px;
    border-radius: 14px;
    border: none;
    font-size: 16px;
    font-weight: 600;
    margin-top: 15px;
    cursor: pointer;
}

.kaspi {
    background: #E60012;
    color: white;
}
</style>

<script>
function isAndroid() {
    return /Android/i.test(navigator.userAgent);
}

function isiOS() {
    return /iPhone|iPad|iPod/i.test(navigator.userAgent);
}

function copy(phone) {
    if (navigator.clipboard) {
        navigator.clipboard.writeText(phone).catch(()=>{});
    }
}

function openKaspi(phone) {
    copy(phone);

    if (isAndroid()) {
        window.location.href =
        "intent://transfers#Intent;scheme=kaspi;package=kz.kaspi.mobile;end";
    }
    else if (isiOS()) {
        window.location.href = "kaspi://transfers";
    }
    else {
        alert("Тек смартфоннан ашыңыз");
    }
}
</script>

</head>
<body>

<div class="container">

<h2>Kaspi арқылы аударым</h2>
<p>+7 700 123 45 67</p>

<button class="kaspi"
onclick="openKaspi('77001234567')">
Kaspi ашу
</button>

</div>

</body>
</html>
