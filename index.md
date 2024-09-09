---
layout: base
title: Course Descriptions
description: An overview of Computer Science pathway at Del Norte High School
author: Manas Goel
image: /images/mario_animation.png
hide: false
---

<style>
    body {
        font-family: Arial, sans-serif;
        background-color: #f0f8ff;
        text-align: center;
    }
    .game-container {
        position: relative;
        width: 300px;
        height: 300px;
        margin: 50px auto;
        border: 2px solid #007acc;
        border-radius: 10px;
        background-color: #e6f7ff;
        overflow: hidden;
    }
    .manas-avatar {
        position: absolute;
        width: 50px;
        height: 50px;
        background-color: #007acc;
        border-radius: 50%;
        cursor: pointer;
    }
    .score-board {
        font-size: 20px;
        margin-top: 20px;
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

<script>
    const manas = document.getElementById('manas');
    const scoreBoard = document.getElementById('score');
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
</script>

## Manas Goel
 
Cannot wait to learn how to make a better game!

