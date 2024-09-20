---
layout: base
title: Course Descriptions
description: An overview of Computer Science pathway at Del Norte High School
author: Manas Goel
image: /images/mario_animation.png
hide: false
---

{% include nav/home.html %}

<style>
    body {
        font-family: 'Poppins', sans-serif;
        background-color: #f0f8ff;
        margin: 0;
        padding: 0;
        text-align: center;
        overflow-x: hidden; /* Prevents horizontal scroll */
    }

    h1 {
        font-size: 3em;
        color: #007acc;
        margin-top: 20px;
        animation: slideInDown 1s;
        letter-spacing: 2px;
        text-shadow: 2px 2px 5px rgba(0, 0, 0, 0.2);
    }

    p {
        font-size: 1.5em;
        color: #333;
        margin-bottom: 20px;
        animation: fadeIn 1.5s;
    }

    .game-container {
        position: relative;
        width: 350px;
        height: 350px;
        margin: 50px auto;
        border: 2px solid #007acc;
        border-radius: 10px;
        background-color: #e6f7ff;
        box-shadow: 0 10px 20px rgba(0, 0, 0, 0.1);
        overflow: hidden;
        animation: bounceIn 1s;
    }

    .manas-avatar {
        position: absolute;
        width: 50px;
        height: 50px;
        background-color: #ff6347;
        border-radius: 50%;
        cursor: pointer;
        box-shadow: 0 5px 10px rgba(0, 0, 0, 0.3);
        transition: transform 0.3s ease;
    }

    .manas-avatar:hover {
        transform: scale(1.2);
    }

    .score-board {
        font-size: 1.8em;
        color: #007acc;
        margin-top: 20px;
        background-color: #e6f7ff;
        padding: 10px;
        border-radius: 8px;
        display: inline-block;
        animation: fadeIn 2s;
        box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
    }

    button {
        font-size: 1.5em;
        background-color: #007acc;
        color: white;
        border: none;
        padding: 10px 20px;
        border-radius: 8px;
        cursor: pointer;
        margin-top: 30px;
        transition: background-color 0.3s, box-shadow 0.3s;
        box-shadow: 0 5px 15px rgba(0, 122, 204, 0.3);
    }

    button:hover {
        background-color: #005fa3;
        box-shadow: 0 5px 20px rgba(0, 122, 204, 0.5);
    }

    /* Animations */
    @keyframes slideInDown {
        from {
            opacity: 0;
            transform: translateY(-50px);
        }
        to {
            opacity: 1;
            transform: translateY(0);
        }
    }

    @keyframes fadeIn {
        from {
            opacity: 0;
        }
        to {
            opacity: 1;
        }
    }

    @keyframes bounceIn {
        from {
            opacity: 0;
            transform: scale(0.9);
        }
        to {
            opacity: 1;
            transform: scale(1);
        }
    }
</style>

<h1>Catch the Manas!</h1>
<p>Click on Manas as he moves around the box to score points!</p>

<div class="game-container">
    <div id="manas" class="manas-avatar"></div>
</div>

<div class="score-board">
    Score: <span id="score">0</span>
</div>

<!-- Reset Button -->
<button id="reset-btn">Reset Game</button>

<script>
    const manas = document.getElementById('manas');
    const scoreBoard = document.getElementById('score');
    const resetBtn = document.getElementById('reset-btn');
    let score = 0;

    function moveManas() {
        const container = document.querySelector('.game-container');
        const maxX = container.offsetWidth - manas.offsetWidth;
        const maxY = container.offsetHeight - manas.offsetHeight;
        const randomX = Math.floor(Math.random() * maxX);
        const randomY = Math.floor(Math.random() * maxY);
        
        manas.style.left = randomX + 'px';
        manas.style.top = randomY + 'px';
    }

    manas.addEventListener('click', function() {
        score++;
        scoreBoard.textContent = score;
        moveManas();
    });

    setInterval(moveManas, 1000); // Move every 1 second

    // Reset Game
    resetBtn.addEventListener('click', function() {
        score = 0;
        scoreBoard.textContent = score;
    });
</script>

## Manas Goel

Cannot wait to learn how to make a better game!

