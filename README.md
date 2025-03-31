<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Combined Page</title>
    <style>
    /* Main Styles */
    body {
        font-family: 'Poppins', sans-serif;
        background-color: #1a1a1a;
        color: white;
        text-align: center;
        margin: 0;
        padding: 0;
    }
    .container {
        max-width: 1200px;
        margin: auto;
        padding: 20px;
    }
    .header {
        font-size: 2.5em;
        font-weight: bold;
        color: #ffcc00;
        margin-bottom: 20px;
    }
    .games {
        display: flex;
        justify-content: center;
        padding: 20px;
    }
    .game {
        background-color: #292929;
        padding: 20px;
        border-radius: 15px;
        cursor: pointer;
        transition: transform 0.3s;
    }
    .game:hover {
        transform: scale(1.05);
    }
    .game img {
        width: 200px;
        border-radius: 10px;
    }
    .play-button {
        background: rgba(255, 204, 0, 0.9);
        padding: 10px 20px;
        border-radius: 10px;
        font-size: 1em;
        font-weight: bold;
        display: none;
    }
    
    /* Game Styles */
    .game-container {
        margin-top: 20px;
    }
    .score {
        font-size: 1.5em;
        margin: 10px;
    }
    </style>
</head>
<body>
    <div class="container">
        <div class="header">Welcome to the Game Hub</div>
        <div class="games">
            <div class="game" onclick="startGame()">
                <img src="game_thumbnail.png" alt="Game Thumbnail">
                <div class="play-button">Play</div>
            </div>
        </div>
    </div>
    
    <div class="game-container" id="gameArea">
        <h2>Game Zone</h2>
        <p class="score">Score: <span id="score">0</span></p>
        <canvas id="gameCanvas"></canvas>
    </div>
    
    <script>
    // Main JavaScript
    function startGame() {
        document.getElementById("gameArea").style.display = "block";
    }
    
    // Game JavaScript
    let score = 0;
    function increaseScore() {
        score++;
        document.getElementById("score").textContent = score;
    }
    document.getElementById("gameCanvas").addEventListener("click", increaseScore);
    </script>
</body>
</html>
