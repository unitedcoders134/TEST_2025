---
layout: page
title: Wordle
permalink: /wordle/
---

{% include nav/home.html %}

<style>
    body {
        font-family: Arial, sans-serif;
        background-color: #FFFFFF;
        color: #FFFFFF;
        margin: 0;
        padding: 0;
        line-height: 1.6;
        transition: background-color 0.5s, color 0.5s;
        scroll-behavior: smooth;
    }

    .container {
        max-width: 800px;
        margin: 0 auto;
        padding: 10px;
        background-color: #000;
        border-radius: 8px;
        box-shadow: 0 0 15px rgba(0, 0, 0, 0.3);
        transition: box-shadow 0.3s ease-in-out;
    }

    .container:hover {
        box-shadow: 0 0 25px rgba(0, 0, 0, 0.5);
    }

    .grid {
        display: grid;
        grid-template-columns: repeat(5, 50px);
        grid-gap: 10px;
        margin: 20px 0;
    }

    .tile {
        width: 50px;
        height: 50px;
        border: 2px solid #fff;
        display: flex;
        justify-content: center;
        align-items: center;
        font-size: 1.5em;
        background-color: #000;
        color: white;
    }

    .correct {
        background-color: green; /* Correct letter in the correct place */
    }

    .present {
        background-color: yellow; /* Correct letter in the wrong place */
    }

    .absent {
        background-color: grey; /* Incorrect letter */
    }

    .keyboard {
        display: flex;
        flex-wrap: wrap;
        justify-content: center;
        gap: 10px;
        margin-top: 20px;
    }

    .keyboard button {
        padding: 10px;
        font-size: 1.2em;
        background-color: #333;
        color: white;
        border: none;
        cursor: pointer;
        border-radius: 5px;
    }

    .keyboard button:hover {
        background-color: #444;
    }
</style>

<div class="container">
    <h1>Wordle</h1>

    <!-- Grid for 6 attempts, each row has 5 tiles -->
    <div class="grid" id="grid">
        <!-- Row 1 -->
        <div class="tile" id="tile-0"></div>
        <div class="tile" id="tile-1"></div>
        <div class="tile" id="tile-2"></div>
        <div class="tile" id="tile-3"></div>
        <div class="tile" id="tile-4"></div>
        <!-- Row 2 -->
        <div class="tile" id="tile-5"></div>
        <div class="tile" id="tile-6"></div>
        <div class="tile" id="tile-7"></div>
        <div class="tile" id="tile-8"></div>
        <div class="tile" id="tile-9"></div>
        <!-- Row 3 -->
        <div class="tile" id="tile-10"></div>
        <div class="tile" id="tile-11"></div>
        <div class="tile" id="tile-12"></div>
        <div class="tile" id="tile-13"></div>
        <div class="tile" id="tile-14"></div>
        <!-- Row 4 -->
        <div class="tile" id="tile-15"></div>
        <div class="tile" id="tile-16"></div>
        <div class="tile" id="tile-17"></div>
        <div class="tile" id="tile-18"></div>
        <div class="tile" id="tile-19"></div>
        <!-- Row 5 -->
        <div class="tile" id="tile-20"></div>
        <div class="tile" id="tile-21"></div>
        <div class="tile" id="tile-22"></div>
        <div class="tile" id="tile-23"></div>
        <div class="tile" id="tile-24"></div>
        <!-- Row 6 -->
        <div class="tile" id="tile-25"></div>
        <div class="tile" id="tile-26"></div>
        <div class="tile" id="tile-27"></div>
        <div class="tile" id="tile-28"></div>
        <div class="tile" id="tile-29"></div>
    </div>

    <div class="keyboard">
        <button onclick="handleKey('Q')">Q</button>
        <button onclick="handleKey('W')">W</button>
        <button onclick="handleKey('E')">E</button>
        <button onclick="handleKey('R')">R</button>
        <button onclick="handleKey('T')">T</button>
        <button onclick="handleKey('Y')">Y</button>
        <button onclick="handleKey('U')">U</button>
        <button onclick="handleKey('I')">I</button>
        <button onclick="handleKey('O')">O</button>
        <button onclick="handleKey('P')">P</button>
        <br />
        <button onclick="handleKey('A')">A</button>
        <button onclick="handleKey('S')">S</button>
        <button onclick="handleKey('D')">D</button>
        <button onclick="handleKey('F')">F</button>
        <button onclick="handleKey('G')">G</button>
        <button onclick="handleKey('H')">H</button>
        <button onclick="handleKey('J')">J</button>
        <button onclick="handleKey('K')">K</button>
        <button onclick="handleKey('L')">L</button>
        <br />
        <button onclick="handleKey('Z')">Z</button>
        <button onclick="handleKey('X')">X</button>
        <button onclick="handleKey('C')">C</button>
        <button onclick="handleKey('V')">V</button>
        <button onclick="handleKey('B')">B</button>
        <button onclick="handleKey('N')">N</button>
        <button onclick="handleKey('M')">M</button>
        <button onclick="checkWord()">Check</button>
    </div>
</div>

<script>
    const solution = "CODES"; // Replace with a random word generator if you want
    let guess = ["", "", "", "", ""];
    let currentTile = 0;
    let currentRow = 0;

    function handleKey(letter) {
        if (currentTile < (currentRow + 1) * 5) {
            guess[currentTile % 5] = letter;
            document.getElementById(`tile-${currentTile}`).textContent = letter;
            currentTile++;
        }
    }

    function checkWord() {
        if (currentTile % 5 === 0) { // Check after 5 letters in a row
            for (let i = 0; i < 5; i++) {
                const tileIndex = currentRow * 5 + i;
                const tile = document.getElementById(`tile-${tileIndex}`);
                if (guess[i] === solution[i]) {
                    tile.classList.add('correct'); // Correct letter in the correct place
                } else if (solution.includes(guess[i])) {
                    tile.classList.add('present'); // Correct letter in the wrong place
                } else {
                    tile.classList.add('absent'); // Incorrect letter
                }
            }
            guess = ["", "", "", "", ""]; // Reset guess for next row
            currentRow++; // Move to the next row
        }
    }
</script>