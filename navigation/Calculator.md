---
layout: page
title: Calculator
permalink: /Calculator/
---

{% include nav/home.html %}

<style>
    body.light-theme {
        background-color: white;
        color: black;
    }

    body.dark-theme {
        background-color: #333;
        color: white;
    }

    body.blue-theme {
        background-color: #007acc;
        color: white;
    }

    body.red-theme {
        background-color: #ff4c4c;
        color: white;
    }

    body.green-theme {
        background-color: #28a745;
        color: white;
    }

    body.grey-theme {
        background-color: #aaa;
        color: white;
    }

    .theme-button {
        margin: 5px;
        padding: 10px;
        border-radius: 5px;
        cursor: pointer;
        border: none;
        font-size: 1em;
        transition: background-color 0.3s ease;
    }

    .theme-button:hover {
        opacity: 0.8;
    }

    .calculator {
        width: 400px;
        margin: 50px auto;
        padding: 20px;
        border: 2px solid #007acc;
        border-radius: 10px;
        background: linear-gradient(145deg, #e6e6e6, #ffffff);
        box-shadow: 6px 6px 12px #bebebe, -6px -6px 12px #ffffff;
    }

    .display {
        width: 100%;
        height: 50px;
        background-color: #f9f9f9;
        border: 1px solid #ddd;
        border-radius: 5px;
        margin-bottom: 15px;
        font-size: 1.7em;
        text-align: right;
        padding-right: 15px;
        line-height: 50px;
        box-shadow: inset 3px 3px 6px #cacaca, inset -3px -3px 6px #ffffff;
    }

    .button-container {
        display: grid;
        grid-template-columns: repeat(4, 1fr);
        grid-gap: 10px;
    }

    .button-container button {
        padding: 20px;
        background-color: #007acc;
        color: white;
        border: none;
        border-radius: 10px;
        font-size: 1.2em;
        cursor: pointer;
        transition: background-color 0.3s ease, transform 0.2s ease;
        box-shadow: 3px 3px 6px #aaa, -3px -3px 6px #fff;
    }

    .button-container button:hover {
        background-color: #005fa3;
        transform: translateY(-3px);
    }

    .wide-button {
        grid-column: span 2;
    }

    .scientific-button-container {
        margin-top: 15px;
        grid-gap: 10px;
    }

    .theme-selector {
        text-align: center;
        margin: 20px;
    }

</style>

<div class="theme-selector">
    <button class="theme-button" onclick="switchTheme('light-theme')">Light</button>
    <button class="theme-button" onclick="switchTheme('dark-theme')">Dark</button>
    <button class="theme-button" onclick="switchTheme('blue-theme')">Blue</button>
    <button class="theme-button" onclick="switchTheme('red-theme')">Red</button>
    <button class="theme-button" onclick="switchTheme('green-theme')">Green</button>
    <button class="theme-button" onclick="switchTheme('grey-theme')">Grey</button>
</div>

<div class="calculator">
    <div id="display" class="display">0</div>
    <div class="button-container">
        <button onclick="clearDisplay()">C</button>
        <button onclick="deleteLast()">DEL</button>
        <button onclick="insert('%')">%</button>
        <button onclick="insert('/')">/</button>

        <button onclick="insert('7')">7</button>
        <button onclick="insert('8')">8</button>
        <button onclick="insert('9')">9</button>
        <button onclick="insert('*')">*</button>

        <button onclick="insert('4')">4</button>
        <button onclick="insert('5')">5</button>
        <button onclick="insert('6')">6</button>
        <button onclick="insert('-')">-</button>

        <button onclick="insert('1')">1</button>
        <button onclick="insert('2')">2</button>
        <button onclick="insert('3')">3</button>
        <button onclick="insert('+')">+</button>

        <button onclick="insert('0')" class="wide-button">0</button>
        <button onclick="insert('.')">.</button>
        <button onclick="calculate()">=</button>
    </div>

    <div class="scientific-button-container button-container">
        <button onclick="insert('Math.PI')">π</button>
        <button onclick="insert('Math.E')">e</button>
        <button onclick="insert('Math.sqrt(')">√</button>
        <button onclick="insert('Math.log(')">log</button>

        <button onclick="insert('Math.sin(')">sin</button>
        <button onclick="insert('Math.cos(')">cos</button>
        <button onclick="insert('Math.tan(')">tan</button>
        <button onclick="insert('Math.pow(')">x^y</button>
    </div>
</div>

<script>
    let display = document.getElementById("display");

    // Clear the display
    function clearDisplay() {
        display.innerHTML = "0";
    }

    // Delete the last character
    function deleteLast() {
        if (display.innerHTML.length > 1) {
            display.innerHTML = display.innerHTML.slice(0, -1);
        } else {
            display.innerHTML = "0";
        }
    }

    // Insert value into the display
    function insert(value) {
        if (display.innerHTML === "0") {
            display.innerHTML = value;
        } else {
            display.innerHTML += value;
        }
    }

    // Calculate the result
    function calculate() {
        try {
            display.innerHTML = eval(display.innerHTML);
        } catch (e) {
            display.innerHTML = "Error";
        }
    }

    // Switch themes
    function switchTheme(theme) {
        document.body.className = theme;
    }
</script>
