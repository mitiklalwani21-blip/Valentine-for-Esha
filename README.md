<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Valentine 💖</title>
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<style>
  body {
    font-family: 'Arial', sans-serif;
    background: linear-gradient(135deg, #ffe6f0, #fff);
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    margin: 0;
    overflow: hidden;
  }

  .card {
    background: white;
    padding: 30px;
    border-radius: 22px;
    text-align: center;
    width: 90%;
    max-width: 360px;
    box-shadow: 0 20px 50px rgba(0,0,0,0.15);
    position: relative;
    z-index: 2;
  }

  h2 {
    color: #ff4d6d;
    margin-bottom: 25px;
  }

  button {
    padding: 12px 30px;
    margin: 10px;
    border-radius: 30px;
    border: none;
    font-size: 16px;
    cursor: pointer;
  }

  .yes {
    background: #ff4d6d;
    color: white;
  }

  .no {
    background: #ddd;
    color: #888;
    cursor: not-allowed;
  }

  .gif {
    margin-top: 20px;
    display: none;
  }

  img {
    width: 100%;
    border-radius: 16px;
  }

  /* Fireworks */
  .firework {
    position: absolute;
    width: 8px;
    height: 8px;
    background: pink;
    border-radius: 50%;
    animation: explode 1s ease-out forwards;
  }

  @keyframes explode {
    from {
      transform: scale(1);
      opacity: 1;
    }
    to {
      transform: translate(var(--x), var(--y)) scale(0);
      opacity: 0;
    }
  }
</style>
</head>

<body>

<div class="card">
  <h2>Will you be my Valentine, Esha? 💖</h2>

  <button class="yes" onclick="yesClicked()">Yes 💕</button>
  <button class="no" disabled>No 🙈</button>

  <div class="gif" id="yesGif">
    <img src="https://media.giphy.com/media/3oz8xKaR836UJOYeOc/giphy.gif" alt="Party Celebration">
    <p>It’s a love story, baby just say YES 💕🎉</p>
  </div>
</div>

<!-- Taylor Swift Love Story (instrumental-style preview link) -->
<audio id="loveSong">
  <source src="https://cdn.pixabay.com/audio/2023/10/24/audio_7f4d90c0d4.mp3" type="audio/mpeg">
</audio>

<script>
  function yesClicked() {
    document.getElementById("yesGif").style.display = "block";

    // Play music
    document.getElementById("loveSong").play();

    // Fireworks
    for (let i = 0; i < 25; i++) {
      const fw = document.createElement("div");
      fw.className = "firework";
      fw.style.left = Math.random() * window.innerWidth + "px";
      fw.style.top = Math.random() * window.innerHeight + "px";
      fw.style.setProperty("--x", (Math.random() * 300 - 150) + "px");
      fw.style.setProperty("--y", (Math.random() * 300 - 150) + "px");
      document.body.appendChild(fw);

      setTimeout(() => fw.remove(), 1000);
    }
  }
</script>

</body>
</html>
