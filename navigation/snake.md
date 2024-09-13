---
layout: page
title: Snake
permalink: /snake/
---

 {% include nav/home.html %}

Future home of snake game 

<style>
    canvas {
        border: 1px solid #000;
        background-color: #fff;
    }

    #game-over {
        font-size: 2em;
        color: red;
        text-align: center;
        display: none;
    }
</style>

<h1 id="game-over">Game Over!</h1>

<canvas id="gameCanvas" width="400" height="400"></canvas>

<script>
    const canvas = document.getElementById("gameCanvas");
    const ctx = canvas.getContext("2d");

    // Unit size of the grid
    const box = 20;

    // Create the snake
    let snake = [];
    snake[0] = { x: 9 * box, y: 10 * box };

    // Create the food
    let food = {
        x: Math.floor(Math.random() * 19 + 1) * box,
        y: Math.floor(Math.random() * 19 + 1) * box
    };

    // Initial snake direction
    let direction;

    // Score
    let score = 0;

    // Control the snake with keyboard
    document.addEventListener("keydown", changeDirection);

    function changeDirection(event) {
        if (event.keyCode == 37 && direction != "RIGHT") {
            direction = "LEFT";
        } else if (event.keyCode == 38 && direction != "DOWN") {
            direction = "UP";
        } else if (event.keyCode == 39 && direction != "LEFT") {
            direction = "RIGHT";
        } else if (event.keyCode == 40 && direction != "UP") {
            direction = "DOWN";
        }
    }

    function collision(head, array) {
        for (let i = 0; i < array.length; i++) {
            if (head.x == array[i].x && head.y == array[i].y) {
                return true;
            }
        }
        return false;
    }

    // Draw everything on the canvas
    function draw() {
        ctx.clearRect(0, 0, canvas.width, canvas.height);

        // Draw snake
        for (let i = 0; i < snake.length; i++) {
            ctx.fillStyle = i == 0 ? "green" : "lightgreen";
            ctx.fillRect(snake[i].x, snake[i].y, box, box);
        }

        // Draw food
        ctx.fillStyle = "red";
        ctx.fillRect(food.x, food.y, box, box);

        // Old head position
        let snakeX = snake[0].x;
        let snakeY = snake[0].y;

        // Move the snake
        if (direction == "LEFT") snakeX -= box;
        if (direction == "UP") snakeY -= box;
        if (direction == "RIGHT") snakeX += box;
        if (direction == "DOWN") snakeY += box;

        // Snake eats the food
        if (snakeX == food.x && snakeY == food.y) {
            score++;
            food = {
                x: Math.floor(Math.random() * 19 + 1) * box,
                y: Math.floor(Math.random() * 19 + 1) * box
            };
        } else {
            snake.pop();
        }

        // New head
        let newHead = {
            x: snakeX,
            y: snakeY
        };

        // Game over conditions
        if (snakeX < 0 || snakeY < 0 || snakeX >= canvas.width || snakeY >= canvas.height || collision(newHead, snake)) {
            document.getElementById("game-over").style.display = "block";
            clearInterval(game);
        }

        snake.unshift(newHead);

        // Score display
        ctx.fillStyle = "black";
        ctx.font = "20px Arial";
        ctx.fillText("Score: " + score, 10, 30);
    }

    // Call draw function every 100ms
    let game = setInterval(draw, 100);
</script>
