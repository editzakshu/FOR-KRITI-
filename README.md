<!DOCTYPE html>
<html lang="hi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>For My Queen Kirti</title>
    <link href="https://fonts.googleapis.com/css2?family=Dancing+Script:wght@700&family=Poppins:wght@300;600&display=swap" rel="stylesheet">
    <style>
        body { margin: 0; padding: 0; background: #fff0f3; font-family: 'Poppins', sans-serif; overflow: hidden; }

        /* Background Watermark */
        body::before {
            content: "KIRTI ❤️ AKSHAY";
            position: fixed; top: 50%; left: 50%; transform: translate(-50%, -50%) rotate(-30deg);
            font-size: 8vw; font-weight: bold; color: rgba(255, 77, 109, 0.05);
            white-space: nowrap; z-index: -1; font-family: 'Dancing Script', cursive;
        }

        .container { scroll-snap-type: y mandatory; overflow-y: scroll; height: 100vh; scroll-behavior: smooth; }

        .section {
            height: 100vh; display: flex; flex-direction: column; justify-content: center;
            align-items: center; text-align: center; padding: 20px; scroll-snap-align: start;
            position: relative; background: rgba(255, 255, 255, 0.2); backdrop-filter: blur(2px);
        }

        img {
            width: 80%; max-width: 280px; border: 8px solid #fff; border-radius: 30px;
            box-shadow: 0 20px 40px rgba(255, 77, 109, 0.2); margin-bottom: 25px;
            animation: floatImg 3s ease-in-out infinite;
        }

        @keyframes floatImg { 0%, 100% { transform: translateY(0); } 50% { transform: translateY(-10px); } }

        .shayari {
            font-family: 'Dancing Script', cursive; color: #d63384; font-size: 1.6rem;
            background: rgba(255, 255, 255, 0.9); padding: 20px; border-radius: 25px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.05); max-width: 85%; border-left: 5px solid #ff4d6d;
        }

        .leaf { position: fixed; top: -50px; z-index: 100; animation: fall 5s linear infinite; }
        @keyframes fall { to { transform: translateY(110vh) rotate(360deg); } }

        .btn-container { position: relative; margin-top: 40px; width: 100%; height: 100px; }

        button {
            padding: 15px 40px; font-size: 1.2rem; border-radius: 50px; border: none;
            cursor: pointer; font-weight: bold; transition: 0.3s;
        }

        #yesBtn { background: #ff4d6d; color: white; position: absolute; left: 50%; transform: translateX(-110%); }
        #noBtn { background: #fff; color: #888; border: 1px solid #ddd; position: absolute; left: 50%; transform: translateX(10%); }

        /* Success Page */
        #successPage {
            display: none; position: fixed; top: 0; left: 0; width: 100%; height: 100%;
            background: white; z-index: 1000; flex-direction: column; justify-content: center; align-items: center;
        }

        .social-links { margin-top: 25px; }
        .snap { 
            background: #FFFC00; color: black !important; 
            padding: 15px 30px; border-radius: 15px; text-decoration: none; 
            font-weight: bold; box-shadow: 0 5px 15px rgba(0,0,0,0.1);
            display: inline-block;
        }
    </style>
</head>
<body>

<div id="mainContent" class="container">
    <div class="section">
        <img src="1.jpg" alt="Kirti">
        <div class="shayari">"Kirti, Aapki ek smile mera pura din bana deti hai! ✨"</div>
    </div>

    <div class="section">
        <img src="2.jpg" alt="Love">
        <div class="shayari">"Khuda se aur kya mangu, <br> Jab meri duniya hi aap ho! 🌹"</div>
    </div>

    <div class="section">
        <h1 style="font-family: 'Dancing Script'; color: #ff4d6d; font-size: 3rem; margin: 0;">Akshay ❤️ Kirti</h1>
        <p style="font-size: 1.1rem;">Will you make me the luckiest guy ever?</p>
        <div class="btn-container">
            <button id="yesBtn" onclick="celebrate()">YES! 🥰</button>
            <button id="noBtn" onmouseover="moveBtn()" onclick="moveBtn()">NO</button>
        </div>
    </div>
</div>

<div id="successPage">
    <h1 style="font-family: 'Dancing Script'; color: #ff4d6d; font-size: 3rem;">I Love You, Kirti! ❤️</h1>
    <p>Yayyy! Chalo ab jaldi se Snapchat par batao!</p>
    <div class="social-links">
        <a href="https://snapchat.com/add/YOUR_USERNAME" class="snap">👻 Snapchat Pe Batao</a>
    </div>
    <br>
    <img src="https://media.giphy.com/media/v1.Y2lkPTc5MGI3NjExOHYybmNodmFhZ2JpbmZ1N2JtZzh0ZzBwaHljZzR4ZzR4ZzR4ZzR4JmVwPXYxX2ludGVybmFsX2dpZl9ieV9pZCZjdD1n/KztT2c4u8mYYUiMKdJ/giphy.gif" style="width: 200px;">
</div>

<script>
    const emojis = ['🌸', '✨', '💖', '🌹'];
    function createLeaf() {
        const leaf = document.createElement('div');
        leaf.classList.add('leaf');
        leaf.innerHTML = emojis[Math.floor(Math.random() * emojis.length)];
        leaf.style.left = Math.random() * 100 + 'vw';
        leaf.style.animationDuration = Math.random() * 2 + 3 + 's';
        document.body.appendChild(leaf);
        setTimeout(() => leaf.remove(), 5000);
    }
    setInterval(createLeaf, 300);

    function moveBtn() {
        const btn = document.getElementById('noBtn');
        btn.style.position = 'fixed';
        btn.style.left = Math.random() * (window.innerWidth - 100) + 'px';
        btn.style.top = Math.random() * (window.innerHeight - 100) + 'px';
        btn.style.transform = 'none';
    }

    function celebrate() {
        document.getElementById('mainContent').style.display = 'none';
        document.getElementById('successPage').style.display = 'flex';
    }
</script>
</body>
</html>
