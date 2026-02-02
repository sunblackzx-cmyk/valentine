<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Valentine ❤️</title>
<style>
    body {
        margin: 0;
        height: 100vh;
        overflow: hidden;
        font-family: 'Arial', sans-serif;
        background: linear-gradient(135deg, #ff9a9e, #fad0c4);
        display: flex;
        align-items: center;
        justify-content: center;
        text-align: center;
    }

    h1 {
        color: #fff;
        font-size: 2rem;
        margin-bottom: 20px;
        text-shadow: 0 2px 5px rgba(0,0,0,0.2);
    }

    .buttons {
        position: relative;
    }

    button {
        padding: 12px 24px;
        font-size: 1.1rem;
        border: none;
        border-radius: 30px;
        cursor: pointer;
        margin: 10px;
    }

    #yesBtn {
        background: #ff4d6d;
        color: #fff;
    }

    #noBtn {
        background: #fff;
        color: #ff4d6d;
        position: absolute;
    }

    #message {
        display: none;
        color: #fff;
        font-size: 1.6rem;
        margin-top: 20px;
    }

    /* Heart balloons */
    .heart {
        position: absolute;
        font-size: 24px;
        animation: float 6s linear infinite;
        opacity: 0.8;
    }

    @keyframes float {
        0% {
            transform: translateY(100vh);
            opacity: 0;
        }
        50% {
            opacity: 1;
        }
        100% {
            transform: translateY(-10vh);
            opacity: 0;
        }
    }
</style>
</head>
<body>

<div>
    <h1>Will you be my Valentine? 💘</h1>

    <div class="buttons">
        <button id="yesBtn">Yes ❤️</button>
        <button id="noBtn">No 🙈</button>
    </div>

    <div id="message">
        Yay! 💖 You just made my heart the happiest!
    </div>
</div>

<script>
    const noBtn = document.getElementById("noBtn");
    const yesBtn = document.getElementById("yesBtn");
    const message = document.getElementById("message");

    function moveButton() {
        const x = Math.random() * (window.innerWidth - 100);
        const y = Math.random() * (window.innerHeight - 50);
        noBtn.style.left = x + "px";
        noBtn.style.top = y + "px";
    }

    noBtn.addEventListener("mouseover", moveButton);
    noBtn.addEventListener("touchstart", moveButton);

    yesBtn.addEventListener("click", () => {
        message.style.display = "block";
        yesBtn.style.display = "none";
        noBtn.style.display = "none";
    });

    // create floating hearts
    setInterval(() => {
        const heart = document.createElement("div");
        heart.className = "heart";
        heart.innerHTML = "❤️";
        heart.style.left = Math.random() * 100 + "vw";
        heart.style.animationDuration = (4 + Math.random() * 3) + "s";
        document.body.appendChild(heart);

        setTimeout(() => {
            heart.remove();
        }, 7000);
    }, 500);
</script>

</body>
</html>
