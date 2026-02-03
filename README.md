<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Free Fire Challenge 🔥</title>

  <style>
    body {
      height: 100vh;
      margin: 0;
      display: flex;
      justify-content: center;
      align-items: center;
      background: #0b0b0b;
      color: white;
      font-family: Arial, sans-serif;
      overflow: hidden;
    }

    .box {
      text-align: center;
    }

    button {
      padding: 12px 26px;
      font-size: 18px;
      border: none;
      border-radius: 8px;
      cursor: pointer;
      margin: 10px;
      transition: all 0.2s ease;
    }

    #yes {
      background: #00ff88;
    }

    #no {
      background: #ff4444;
      position: absolute;
      transition: left 0.15s, top 0.15s;
    }
  </style>
</head>

<body>
  <div class="box">
    <h1>Khelega Free Fire? 🔥🎮</h1>
    <button id="yes" onclick="yesClick()">YES</button>
    <button id="no">NO</button>
  </div>

  <script>
    const noBtn = document.getElementById("no");
    const yesBtn = document.getElementById("yes");
    let yesSize = 18;

    function moveNo(x, y) {
      const rect = noBtn.getBoundingClientRect();
      const noX = rect.left + rect.width / 2;
      const noY = rect.top + rect.height / 2;

      const dx = noX - x;
      const dy = noY - y;
      const dist = Math.hypot(dx, dy);

      if (dist < 120) {
        let moveX = (dx / dist) * 150;
        let moveY = (dy / dist) * 150;

        let newX = rect.left + moveX;
        let newY = rect.top + moveY;

        newX = Math.max(0, Math.min(window.innerWidth - rect.width, newX));
        newY = Math.max(0, Math.min(window.innerHeight - rect.height, newY));

        noBtn.style.left = newX + "px";
        noBtn.style.top = newY + "px";

        yesSize += 1.3;
        yesBtn.style.fontSize = yesSize + "px";
      }
    }

    // PC mouse
    document.addEventListener("mousemove", (e) => {
      moveNo(e.clientX, e.clientY);
    });

    // Mobile touch
    document.addEventListener("touchmove", (e) => {
      const touch = e.touches[0];
      moveNo(touch.clientX, touch.clientY);
    });

    function yesClick() {
      alert("Aja noobde 😎🔥 1v1 custom mein!");
    }
  </script>
</body>
</html>
