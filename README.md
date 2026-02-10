<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Be My Valentine 💖</title>

<style>
  body {
    margin: 0;
    height: 100vh;
    overflow: hidden;
    display: flex;
    justify-content: center;
    align-items: center;
    background: linear-gradient(135deg, #ff758c, #ff7eb3);
    font-family: 'Segoe UI', sans-serif;
  }

  .container {
    text-align: center;
    background: rgba(255,255,255,0.25);
    padding: 40px;
    border-radius: 25px;
    box-shadow: 0 15px 40px rgba(0,0,0,0.3);
    z-index: 2;
  }

  h1 {
    color: #b30059;
    font-size: 2.8rem;
    margin-bottom: 30px;
  }

  button {
    font-size: 1.2rem;
    padding: 12px 35px;
    margin: 10px;
    border: none;
    border-radius: 30px;
    cursor: pointer;
    transition: 0.2s;
  }

  #yesBtn {
    background: #ff3366;
    color: white;
  }

  #yesBtn:hover {
    transform: scale(1.1);
  }

  #noBtn {
    background: white;
    color: #ff3366;
    position: absolute;
  }

  .tooltip {
    position: absolute;
    background: #000;
    color: white;
    padding: 6px 12px;
    border-radius: 8px;
    font-size: 0.9rem;
    display: none;
  }

  /* Popup */
  .popup {
    position: fixed;
    inset: 0;
    background: rgba(0,0,0,0.6);
    display: none;
    justify-content: center;
    align-items: center;
    z-index: 5;
  }

  .popup-content {
    background: white;
    padding: 40px;
    border-radius: 25px;
    text-align: center;
    animation: pop 0.4s ease;
  }

  .popup-content h2 {
    color: #ff3366;
    font-size: 2rem;
  }

  @keyframes pop {
    from { transform: scale(0.6); }
    to { transform: scale(1); }
  }

  /* Hearts */
  .heart {
    position: absolute;
    bottom: -20px;
    color: rgba(255,255,255,0.8);
    font-size: 20px;
    animation: float 6s linear infinite;
  }

  @keyframes float {
    from {
      transform: translateY(0);
      opacity: 1;
    }
    to {
      transform: translateY(-100vh);
      opacity: 0;
    }
  }
</style>
</head>

<body>

<!-- Music -->
<audio autoplay loop>
  <source src="https://www.soundhelix.com/examples/mp3/SoundHelix-Song-1.mp3">
</audio>

<div class="container">
  <h1>Will you be my Valentine? 💕</h1>
  <button id="yesBtn">Yes 💖</button>
  <button id="noBtn">No 😜</button>
  <div class="tooltip" id="tooltip">Please click Yes 🥺❤️</div>
</div>

<!-- Popup -->
<div class="popup" id="popup">
  <div class="popup-content">
    <h2>I love you Raja 💋❤️</h2>
    <p>Ummah forever 😘💕</p>
  </div>
</div>

<script>
  const noBtn = document.getElementById("noBtn");
  const tooltip = document.getElementById("tooltip");
  const popup = document.getElementById("popup");

  noBtn.addEventListener("mouseover", () => {
    const x = Math.random() * (window.innerWidth - 150);
    const y = Math.random() * (window.innerHeight - 100);

    noBtn.style.left = x + "px";
    noBtn.style.top = y + "px";

    tooltip.style.left = x + "px";
    tooltip.style.top = (y - 30) + "px";
    tooltip.style.display = "block";
  });

  document.getElementById("yesBtn").addEventListener("click", () => {
    popup.style.display = "flex";
  });

  // Floating hearts
  setInterval(() => {
    const heart = document.createElement("div");
    heart.className = "heart";
    heart.innerHTML = "❤️";
    heart.style.left = Math.random() * 100 + "vw";
    heart.style.fontSize = Math.random() * 20 + 15 + "px";
    document.body.appendChild(heart);

    setTimeout(() => heart.remove(), 6000);
  }, 300);
</script>

</body>
</html>
