---
layout: page
title: TOD
permalink: /TOD/
---

 {% include nav/home.html %}

This is my idea for my new game!

<style>
    body {
        font-family: Arial, sansx-serif;
        background-color: #f0f0f0;
        color: #333;
        text-align: center;
    }

    canvas {
        border: 2px solid #333;
        display: block;
        margin: 20px auto;
        background-color: #fff;
    }

    .menu {
        margin: 20px;
    }

    .menu button {
        padding: 10px;
        background-color: #333;
        color: white;
        border: none;
        margin: 5px;
        cursor: pointer;
    }

    .menu button:hover {
        background-color: #555;
    }

    .menu p {
        font-size: 20px;
    }

    /* Theme colors */
    .white-theme {
        background-color: white;
        color: black;
    }

    .dark-theme {
        background-color: black;
        color: white;
    }

    .blue-theme {
        background-color: lightblue;
        color: navy;
    }

    .red-theme {
        background-color: lightcoral;
        color: darkred;
    }

    .green-theme {
        background-color: lightgreen;
        color: darkgreen;
    }

    .grey-theme {
        background-color: grey;
        color: white;
    }

    /* Ensuring text visibility in dark and grey themes */
    .dark-theme .menu p, .dark-theme .menu button, 
    .grey-theme .menu p, .grey-theme .menu button {
        color: white;
    }
</style>

<div class="menu">
    <p>Resources: <span id="resources">100</span></p>
    <p>Wave: <span id="wave">1</span></p>
    <p>Lives: <span id="lives">10</span></p>
    <button id="start">Start Wave</button>
    <button id="place-tower">Place Tower</button>
    <button id="switch-theme">Switch Theme</button>
</div>

<canvas id="gameCanvas" width="600" height="400"></canvas>

<script>
    const canvas = document.getElementById("gameCanvas");
    const ctx = canvas.getContext("2d");

    // Game variables
    let resources = 100;
    let wave = 1;
    let lives = 10;
    let enemies = [];
    let towers = [];
    let placingTower = false;
    let currentTheme = 0;

    const themes = ['white-theme', 'dark-theme', 'blue-theme', 'red-theme', 'green-theme', 'grey-theme'];

    // Set initial theme
    document.body.classList.add(themes[currentTheme]);

    // Handle theme switch
    document.getElementById("switch-theme").addEventListener("click", function() {
        document.body.classList.remove(themes[currentTheme]);
        currentTheme = (currentTheme + 1) % themes.length;
        document.body.classList.add(themes[currentTheme]);
    });

    document.getElementById("resources").textContent = resources;
    document.getElementById("wave").textContent = wave;
    document.getElementById("lives").textContent = lives;

    const box = 40; // Grid size

    // Tower object
    function Tower(x, y) {
        this.x = x;
        this.y = y;
        this.range = 100;
        this.attackSpeed = 1000;
        this.damage = 10;
        this.target = null;
    }

    Tower.prototype.draw = function() {
        ctx.fillStyle = "blue";
        ctx.fillRect(this.x, this.y, box, box);
    };

    // Enemy object
    function Enemy(x, y) {
        this.x = x;
        this.y = y;
        this.speed = 1 + wave * 0.1; // Speed increases each wave
        this.health = 50 + wave * 10; // Health increases each wave
        this.alive = true;
    }

    Enemy.prototype.move = function() {
        if (this.alive) {
            this.x += this.speed;
        }

        // Enemy reaches end
        if (this.x > canvas.width) {
            this.alive = false;
            lives--;
            document.getElementById("lives").textContent = lives;
        }
    };

    Enemy.prototype.draw = function() {
        if (this.alive) {
            ctx.fillStyle = "red";
            ctx.fillRect(this.x, this.y, box, box);
        }
    };

    function spawnEnemy() {
        enemies.push(new Enemy(0, Math.floor(Math.random() * canvas.height / box) * box));
    }

    function gameLoop() {
        ctx.clearRect(0, 0, canvas.width, canvas.height);

        // Draw and move enemies
        enemies.forEach(enemy => {
            enemy.move();
            enemy.draw();
        });

        // Draw towers
        towers.forEach(tower => {
            tower.draw();
        });

        // Tower attacks
        towers.forEach(tower => {
            enemies.forEach(enemy => {
                const distance = Math.sqrt((enemy.x - tower.x) ** 2 + (enemy.y - tower.y) ** 2);
                if (distance < tower.range && enemy.alive) {
                    enemy.health -= tower.damage;
                    if (enemy.health <= 0) {
                        enemy.alive = false;
                        resources += 10; // Gain resources for defeating an enemy
                        document.getElementById("resources").textContent = resources;
                    }
                }
            });
        });

        if (lives <= 0) {
            clearInterval(gameInterval);
            alert("Game Over!");
        }
    }

    // Handle placing tower
    canvas.addEventListener("click", function(e) {
        if (placingTower) {
            const x = Math.floor(e.offsetX / box) * box;
            const y = Math.floor(e.offsetY / box) * box;
            if (resources >= 50) {
                towers.push(new Tower(x, y));
                resources -= 50;
                document.getElementById("resources").textContent = resources;
            }
            placingTower = false;
        }
    });

    // Start wave button
    document.getElementById("start").addEventListener("click", function() {
        for (let i = 0; i < wave * 5; i++) {
            setTimeout(spawnEnemy, i * 500);
        }
        wave++;
        document.getElementById("wave").textContent = wave;
    });

    // Place tower button
    document.getElementById("place-tower").addEventListener("click", function() {
        placingTower = true;
    });

    // Start game loop
    let gameInterval = setInterval(gameLoop, 100);
</script>
