<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Simple Car Avoidance Game</title>
  <style>
    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    body {
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      min-height: 100vh;
      background-color: #1a1a1a;
      font-family: Arial, sans-serif;
      color: #fff;
    }

    #score-board {
      font-size: 24px;
      margin-bottom: 12px;
      font-weight: bold;
    }

    #game-container {
      position: relative;
      width: 320px;
      height: 500px;
      background-color: #333;
      border: 4px solid #fff;
      overflow: hidden;
      box-shadow: 0 10px 20px rgba(0,0,0,0.5);
    }

    /* Road Center Lines Animation */
    .road-line {
      position: absolute;
      left: 50%;
      width: 8px;
      height: 40px;
      background-color: #fff;
      transform: translateX(-50%);
    }

    /* Player Car */
    #player-car {
      position: absolute;
      bottom: 20px;
      left: 135px;
      width: 50px;
      height: 80px;
      background-color: #00bcd4;
      border-radius: 8px;
      border: 3px solid #00838f;
      box-shadow: inset 0 0 10px rgba(0,0,0,0.4);
    }

    /* Windows on Player Car */
    #player-car::before {
      content: '';
      position: absolute;
      top: 15px;
      left: 5px;
      width: 34px;
      height: 20px;
      background-color: #111;
      border-radius: 3px;
    }

    /* Enemy Car */
    .obstacle {
      position: absolute;
      width: 50px;
      height: 80px;
      background-color: #e91e63;
      border-radius: 8px;
      border: 3px solid #880e4f;
    }

    .obstacle::before {
      content: '';
      position: absolute;
      bottom: 15px;
      left: 5px;
      width: 34px;
      height: 20px;
      background-color: #111;
      border-radius: 3px;
    }

    /* Overlay Screen */
    #overlay {
      position: absolute;
      inset: 0;
      background: rgba(0, 0, 0, 0.8);
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      gap: 16px;
      z-index: 10;
    }

    #start-btn {
      padding: 10px 24px;
      font-size: 18px;
      font-weight: bold;
      color: #fff;
      background-color: #4caf50;
      border: none;
      border-radius: 4px;
      cursor: pointer;
    }

    #start-btn:hover {
      background-color: #45a049;
    }
  </style>
</head>
<body>

  <div id="score-board">Score: <span id="score">0</span></div>

  <div id="game-container">
    <div id="overlay">
      <h2 id="overlay-title">Car Dodge</h2>
      <p>Use ⬅️ and ➡️ keys to steer</p>
      <button id="start-btn" onclick="startGame()">Start Game</button>
    </div>

    <!-- Road Markings -->
    <div class="road-line" style="top: -60px;"></div>
    <div class="road-line" style="top: 60px;"></div>
    <div class="road-line" style="top: 180px;"></div>
    <div class="road-line" style="top: 300px;"></div>
    <div class="road-line" style="top: 420px;"></div>

    <div id="player-car"></div>
  </div>

  <script>
    const container = document.getElementById('game-container');
    const player = document.getElementById('player-car');
    const scoreDisplay = document.getElementById('score');
    const overlay = document.getElementById('overlay');
    const overlayTitle = document.getElementById('overlay-title');

    const containerWidth = 320;
    const carWidth = 50;
    const carHeight = 80;

    let playerX = 135;
    let score = 0;
    let gameSpeed = 5;
    let isGameOver = true;
    let animationFrameId;

    let keys = { ArrowLeft: false, ArrowRight: false };
    let obstacles = [];
    let roadLines = document.querySelectorAll('.road-line');

    // Controls listeners
    document.addEventListener('keydown', (e) => {
      if (e.key === 'ArrowLeft' || e.key === 'ArrowRight') {
        keys[e.key] = true;
      }
    });

    document.addEventListener('keyup', (e) => {
      if (e.key === 'ArrowLeft' || e.key === 'ArrowRight') {
        keys[e.key] = false;
      }
    });

    function startGame() {
      // Reset state
      isGameOver = false;
      score = 0;
      gameSpeed = 5;
      playerX = (containerWidth / 2) - (carWidth / 2);
      scoreDisplay.textContent = score;

      // Clear existing obstacles
      obstacles.forEach(obs => obs.element.remove());
      obstacles = [];

      overlay.style.display = 'none';

      // Start game loop
      gameLoop();
      spawnObstacle();
    }

    function spawnObstacle() {
      if (isGameOver) return;

      // Random X position inside boundaries
      const minX = 10;
      const maxX = containerWidth - carWidth - 10;
      const randomX = Math.floor(Math.random() * (maxX - minX + 1)) + minX;

      const obstacleElem = document.createElement('div');
      obstacleElem.classList.add('obstacle');
      obstacleElem.style.left = `${randomX}px`;
      obstacleElem.style.top = `-90px`;
      container.appendChild(obstacleElem);

      obstacles.push({
        element: obstacleElem,
        x: randomX,
        y: -90
      });

      // Schedule next obstacle spawn
      const spawnInterval = Math.max(800, 2000 - score * 50);
      setTimeout(spawnObstacle, spawnInterval);
    }

    function update() {
      // Move Player
      if (keys.ArrowLeft && playerX > 5) {
        playerX -= 6;
      }
      if (keys.ArrowRight && playerX < containerWidth - carWidth - 5) {
        playerX += 6;
      }
      player.style.left = `${playerX}px`;

      // Animate Road Lines
      roadLines.forEach(line => {
        let top = parseFloat(line.style.top);
        top += gameSpeed;
        if (top >= 500) top = -60;
        line.style.top = `${top}px`;
      });

      // Move and Handle Obstacles
      for (let i = obstacles.length - 1; i >= 0; i--) {
        const obs = obstacles[i];
        obs.y += gameSpeed;
        obs.element.style.top = `${obs.y}px`;

        // Check Collision
        const playerY = 500 - carHeight - 20; // Player CSS bottom position
        if (
          playerX < obs.x + carWidth &&
          playerX + carWidth > obs.x &&
          playerY < obs.y + carHeight &&
          playerY + carHeight > obs.y
        ) {
          endGame();
          return;
        }

        // Passed Obstacle (Score Point)
        if (obs.y > 500) {
          obs.element.remove();
          obstacles.splice(i, 1);
          score += 1;
          scoreDisplay.textContent = score;

          // Increase difficulty gradually
          if (score % 5 === 0) {
            gameSpeed += 0.5;
          }
        }
      }
    }

    function gameLoop() {
      if (isGameOver) return;
      update();
      animationFrameId = requestAnimationFrame(gameLoop);
    }

    function endGame() {
      isGameOver = true;
      cancelAnimationFrame(animationFrameId);
      overlayTitle.textContent = 'Game Over!';
      overlay.style.display = 'flex';
    }
  </script>
</body>
</html>
