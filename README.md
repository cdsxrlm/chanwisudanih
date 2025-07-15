<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <title>Graduation Invitation</title>
  <style>
    body {
      background-color: peachpuff; /* peach background */
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      overflow: hidden;
      font-family: sans-serif;
    }

    .envelope-icon {
      font-size: 200px; /* besar emoji amplop */
      cursor: pointer;
      transition: transform 0.3s ease;
    }

    .envelope-icon:hover {
      transform: scale(1.1);
    }

    .letter {
      position: absolute;
      top: 50%;
      transform: translateY(-50%);
      background: white;
      color: black;
      padding: 50px;
      border-radius: 20px;
      box-shadow: 0 5px 20px rgba(0,0,0,0.2);
      text-align: center;
      width: 600px;
      opacity: 0;
      pointer-events: none;
      transition: opacity 0.5s ease;
    }

    .letter.show {
      opacity: 1;
      pointer-events: auto;
    }

    canvas {
      position: fixed;
      top: 0;
      left: 0;
      pointer-events: none;
    }
  </style>
</head>
<body>
  <div class="envelope-icon" onclick="openLetter()">💌</div>

  <div class="letter" id="letterContent">
    <p>
     Hi!<br>
        Bagi ku, tinggal di Malang dan bertemu dengan mu<br>
        adalah ketidaksengajaan terbaik dari aamiinku⋆˙⟡<br>
        Senang sekali bisa mengenalmu, mau berbagi memori bersama untukku?(੭˃ᴗ˂)੭ <br>
        Jika memungkinkan datang ya di perayaan kecil ku untuk mengabadikan momen👇 <br>
    <br>
      📆: Sabtu, 19 Juli 2025<br>
      ⌚: 15:00 - 16:00<br>
      📍: Sekitar GKB & Gracak<br>
      👩🏻‍🤝‍🧑🏻: senyamannya<br>
      <br>
      Terima kasih telah menjadi ketidaksengajaan terbaik dalam memori<br>
      Baik-baik yah, sampai jumpa disana<br>
      karena ku masih ingin melihatmu esok hari🎓✨🎈<br>
    </p>
  </div>

  <!-- Backsound -->
  <audio id="bgMusic" src="graduation_hindia.mp3"></audio>

  <!-- Confetti -->
  <canvas id="confetti"></canvas>
  <script src="https://cdn.jsdelivr.net/npm/canvas-confetti@1.5.1/dist/confetti.browser.min.js"></script>

  <script>
  function openLetter() {
    const letter = document.getElementById('letterContent');
    const audio = document.getElementById('bgMusic');
    letter.classList.add('show');

    // Play audio: restart & play
    audio.currentTime = 0; 
    audio.volume = 1;
    audio.play().catch(e => {
      console.log("Audio play:", e);
    });

    // Confetti
    confetti({
      particleCount: 200,
      spread: 70,
      origin: { y: 0.6 }
    });
  }
</script>
</body>
</html>
