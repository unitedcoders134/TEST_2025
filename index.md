---
layout: base
title: Course Descriptions
description: An overview of Computer Science pathway at Del Norte High School
author: Mihir Thaha
image: /images/mario_animation.png
hide: false
---

{% include nav/home.html %}


<script>
// JavaScript for Minesweeper Game

document.addEventListener('DOMContentLoaded', function () {
    const gridSize = 10; // Grid size (10x10)
    const mineCount = 15; // Number of mines
    const grid = document.getElementById("game");
    const cells = [];
    let gameOver = false;

    function createBoard() {
        grid.innerHTML = '';
        cells.length = 0;
        gameOver = false;

        // Create grid
        for (let i = 0; i < gridSize; i++) {
            const row = [];
            for (let j = 0; j < gridSize; j++) {
                const cell = document.createElement("button");
                cell.classList.add("cell");
                cell.dataset.x = i;
                cell.dataset.y = j;
                cell.addEventListener('click', () => handleClick(i, j));
                row.push(cell);
                grid.appendChild(cell);
            }
            cells.push(row);
        }

        // Randomly place mines
        let minesPlaced = 0;
        while (minesPlaced < mineCount) {
            const x = Math.floor(Math.random() * gridSize);
            const y = Math.floor(Math.random() * gridSize);
            if (!cells[x][y].classList.contains('mine')) {
                cells[x][y].classList.add('mine');
                minesPlaced++;
            }
        }

        // Calculate numbers for each cell
        for (let i = 0; i < gridSize; i++) {
            for (let j = 0; j < gridSize; j++) {
                if (!cells[i][j].classList.contains('mine')) {
                    const count = countMinesAround(i, j);
                    if (count > 0) cells[i][j].textContent = count;
                }
            }
        }
    }

    function countMinesAround(x, y) {
        let count = 0;
        for (let i = -1; i <= 1; i++) {
            for (let j = -1; j <= 1; j++) {
                const newX = x + i;
                const newY = y + j;
                if (newX >= 0 && newX < gridSize && newY >= 0 && newY < gridSize) {
                    if (cells[newX][newY].classList.contains('mine')) count++;
                }
            }
        }
        return count;
    }

    function handleClick(x, y) {
        if (gameOver || cells[x][y].classList.contains('revealed')) return;

        cells[x][y].classList.add('revealed');
        if (cells[x][y].classList.contains('mine')) {
            revealMines();
            alert('Game Over! You clicked on a mine.');
            gameOver = true;
        } else if (cells[x][y].textContent === '') {
            revealEmpty(x, y);
        }

        // Check if the game is won
        if (checkWin()) {
            alert('Congratulations! You won!');
            gameOver = true;
        }
    }

    function revealMines() {
        for (let i = 0; i < gridSize; i++) {
            for (let j = 0; j < gridSize; j++) {
                if (cells[i][j].classList.contains('mine')) {
                    cells[i][j].classList.add('revealed');
                    cells[i][j].textContent = '💣';
                }
            }
        }
    }

    function revealEmpty(x, y) {
        for (let i = -1; i <= 1; i++) {
            for (let j = -1; j <= 1; j++) {
                const newX = x + i;
                const newY = y + j;
                if (newX >= 0 && newX < gridSize && newY >= 0 && newY < gridSize) {
                    if (!cells[newX][newY].classList.contains('revealed') && !cells[newX][newY].classList.contains('mine')) {
                        cells[newX][newY].classList.add('revealed');
                        if (cells[newX][newY].textContent === '') {
                            revealEmpty(newX, newY);
                        }
                    }
                }
            }
        }
    }

    function checkWin() {
        for (let i = 0; i < gridSize; i++) {
            for (let j = 0; j < gridSize; j++) {
                if (!cells[i][j].classList.contains('mine') && !cells[i][j].classList.contains('revealed')) {
                    return false;
                }
            }
        }
        return true;
    }

    createBoard();
});
</script>

<style>
/* CSS for Minesweeper Game */

#game {
    display: grid;
    grid-template-columns: repeat(10, 40px);
    gap: 2px;
    margin-top: 20px;
}

.cell {
    width: 40px;
    height: 40px;
    background-color: #e0e0e0;
    border: none;
    font-size: 18px;
    cursor: pointer;
    transition: background-color 0.2s;
}

.cell.revealed {
    background-color: #fff;
    border: 1px solid #ccc;
    cursor: default;
}

.cell.mine.revealed {
    color: red;
    font-size: 24px;
}
</style>