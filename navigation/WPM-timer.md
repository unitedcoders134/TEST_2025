---
layout: page
title: Typing Game with Timer
permalink: /WPM-Timer/
---

<style>
    body {
        font-family: Arial, sans-serif;
        background-color: #f4f4f4;
        color: #333;
        text-align: center;
        padding: 50px;
    }
    #game-container {
        background-color: #fff;
        padding: 20px;
        border-radius: 10px;
        box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        width: 80%;
        margin: auto;
    }
    #prompt {
        font-size: 1.2em;
        margin-bottom: 20px;
    }
    #input-area {
        width: 100%;
        padding: 10px;
        font-size: 1.2em;
        border: 2px solid #007acc;
        border-radius: 5px;
    }
    #start-btn, #reset-btn {
        background-color: #007acc;
        color: white;
        padding: 10px 20px;
        border: none;
        border-radius: 5px;
        cursor: pointer;
        font-size: 1em;
        margin: 10px;
    }
    #start-btn:hover, #reset-btn:hover {
        background-color: #005fa3;
    }
    #results {
        margin-top: 20px;
        font-size: 1.5em;
    }
    #timer {
        font-size: 1.5em;
        margin-top: 10px;
        color: #007acc;
    }
</style>

<div id="game-container">
    <h1>Test Your Typing Speed with Timer</h1>
    <p id="prompt">Click "Start" to begin typing!</p>
    <textarea id="input-area" rows="5" placeholder="Type here..." disabled></textarea>
    <div>
        <button id="start-btn">Start</button>
        <button id="reset-btn" disabled>Reset</button>
    </div>
    <div id="timer">Time left: 60 seconds</div>
    <div id="results"></div>
</div>

<script>
    const prompts = [
        "The quick brown fox jumps over the lazy dog.",
        "Typing fast is a skill that improves with practice.",
        "Consistency is key when trying to get better at something.",
        "A journey of a thousand miles begins with a single step.",
        "You can achieve anything if you put your mind to it."
    ];

    const inputArea = document.getElementById('input-area');
    const startBtn = document.getElementById('start-btn');
    const resetBtn = document.getElementById('reset-btn');
    const promptElement = document.getElementById('prompt');
    const resultsElement = document.getElementById('results');
    const timerElement = document.getElementById('timer');

    let startTime;
    let isPlaying = false;
    let selectedPrompt = '';
    let timerInterval;
    let timeLeft = 60; // Set the timer duration in seconds

    startBtn.addEventListener('click', startGame);
    inputArea.addEventListener('input', checkInput);
    resetBtn.addEventListener('click', resetGame);

    function startGame() {
        selectedPrompt = prompts[Math.floor(Math.random() * prompts.length)];
        promptElement.textContent = selectedPrompt;
        inputArea.value = '';
        inputArea.disabled = false;
        inputArea.focus();
        startTime = new Date().getTime();
        isPlaying = true;
        startBtn.disabled = true;
        resetBtn.disabled = false;
        resultsElement.textContent = '';
        timeLeft = 60;
        timerElement.textContent = `Time left: ${timeLeft} seconds`;

        // Start the timer countdown
        timerInterval = setInterval(updateTimer, 1000);
    }

    function updateTimer() {
        if (timeLeft > 0) {
            timeLeft--;
            timerElement.textContent = `Time left: ${timeLeft} seconds`;
        } else {
            // Timer has run out, stop the game
            clearInterval(timerInterval);
            inputArea.disabled = true;
            isPlaying = false;
            calculateWPM();
        }
    }

    function checkInput() {
        if (!isPlaying) return;
        const textEntered = inputArea.value;

        // If the entire prompt is typed before the time runs out
        if (textEntered === selectedPrompt) {
            clearInterval(timerInterval); // Stop the timer
            inputArea.disabled = true;
            isPlaying = false;
            calculateWPM();
        }
    }

    function calculateWPM() {
        const endTime = new Date().getTime();
        const timeTaken = (endTime - startTime) / 1000; // Time in seconds
        const wordsTyped = inputArea.value.split(' ').filter(word => word !== '').length;
        const wpm = (wordsTyped / timeTaken) * 60;
        displayResults(wpm);
    }

    function displayResults(wpm) {
        resultsElement.textContent = `Your WPM: ${Math.round(wpm)} words per minute!`;
    }

    function resetGame() {
        promptElement.textContent = 'Click "Start" to begin typing!';
        inputArea.value = '';
        inputArea.disabled = true;
        startBtn.disabled = false;
        resetBtn.disabled = true;
        resultsElement.textContent = '';
        timerElement.textContent = `Time left: 60 seconds`;
        clearInterval(timerInterval); // Clear the timer if it's still running
        isPlaying = false;
    }
</script>
