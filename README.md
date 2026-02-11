# san-valentin-para-ti
Aún no es seguro que podamos vernos ese día, y por temas de trabajo no podremos compartirlo como quisiera, pero igual quiero celebrarte y hacerte sentir lo especial que eres para mí.
<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<title>¿Quieres ser mi San Valentín?</title>
<style>
    body {
        margin: 0;
        font-family: 'Arial', sans-serif;
        background: linear-gradient(135deg, #ffd6e8, #e0c3fc);
        display: flex;
        justify-content: center;
        align-items: center;
        height: 100vh;
        overflow: hidden;
    }

    .card {
        background: #fff;
        padding: 30px;
        border-radius: 20px;
        text-align: center;
        width: 90%;
        max-width: 400px;
        box-shadow: 0 10px 30px rgba(0,0,0,0.15);
        position: relative;
        z-index: 2;
    }

    h1 {
        color: #ff5c8a;
    }

    p {
        color: #555;
        font-size: 15px;
    }

    .buttons {
        margin-top: 20px;
        display: flex;
        justify-content: space-around;
    }

    button {
        border: none;
        padding: 12px 22px;
        border-radius: 30px;
        font-size: 16px;
        cursor: pointer;
        transition: all 0.3s ease;
    }

    #yesBtn {
        background: #ff8fab;
        color: white;
    }

    #noBtn {
        background: #ccc;
        color: #666;
    }

    .hidden {
        display: none;
    }

    .heart {
        position: absolute;
        bottom: -20px;
        color: rgba(255, 92, 138, 0.4);
        animation: float 6s infinite;
        font-size: 20px;
    }

    @keyframes float {
        0% { transform: translateY(0); opacity: 1; }
        100% { transform: translateY(-110vh); opacity: 0; }
    }
</style>
</head>
<body>

<div class="card" id="card">
    <h1>¿Quieres, aceptas ser mi San Valentín? 💖</h1>
    <p>
        Aunque no es seguro que podamos vernos para pedírtelo presencialmente,
        me gustaría poder celebrar un día tan bonito contigo.
        A pesar de que ese día, por motivos de trabajo, no estaré,
        me gustaría celebrarlo y principalmente celebrarte a ti.
    </p>

    <div class="buttons">
        <button id="yesBtn">Sí 💕</button>
        <button id="noBtn">No 😢</button>
    </div>
</div>

<div class="card hidden" id="result">
    <h1>💘 Eres la niña más hermosa 💘</h1>
    <p>Gracias por decir que sí 🥰</p>
    <a id="whatsappLink" target="_blank">
        <button style="background:#25D366;color:white;">Confirmar por WhatsApp 💬</button>
    </a>
</div>

<script>
    let yesBtn = document.getElementById("yesBtn");
    let noBtn = document.getElementById("noBtn");
    let card = document.getElementById("card");
    let result = document.getElementById("result");

    let scale = 1;

    noBtn.addEventListener("click", () => {
        scale += 0.2;
        yesBtn.style.transform = `scale(${scale})`;
    });

    yesBtn.addEventListener("click", () => {
        card.classList.add("hidden");
        result.classList.remove("hidden");

        const phone = "507XXXXXXXX"; // 50767276549
        const message = encodeURIComponent("Dije que sí 💖");
        document.getElementById("whatsappLink").href =
            `https://wa.me/${phone}?text=${message}`;
    });

    // Corazones flotando
    setInterval(() => {
        const heart = document.createElement("div");
        heart.classList.add("heart");
        heart.innerHTML = "❤️";
        heart.style.left = Math.random() * 100 + "vw";
        heart.style.fontSize = Math.random() * 20 + 15 + "px";
        heart.style.animationDuration = Math.random() * 3 + 4 + "s";
        document.body.appendChild(heart);

        setTimeout(() => heart.remove(), 7000);
    }, 500);
</script>

</body>
</html>
