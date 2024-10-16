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



<!DOCTYPE html>
<html lang="en">

<!DOCTYPE html>
<html lang="en-US">
  <head>
    <meta charset="UTF-8">

<!-- Begin Jekyll SEO tag v2.8.0 -->
<title>Team Teach Home | Nighthawk Pages</title>
<meta name="generator" content="Jekyll v3.10.0" />
<meta property="og:title" content="Team Teach Home" />
<meta property="og:locale" content="en_US" />
<meta name="description" content="Class of 2025" />
<meta property="og:description" content="Class of 2025" />
<link rel="canonical" href="https://beijanm.github.io/beijan25/teamteachhome" />
<meta property="og:url" content="https://beijanm.github.io/beijan25/teamteachhome" />
<meta property="og:site_name" content="Nighthawk Pages" />
<meta property="og:type" content="article" />
<meta property="article:published_time" content="2024-10-08T00:00:00+00:00" />
<meta name="twitter:card" content="summary" />
<meta property="twitter:title" content="Team Teach Home" />
<script type="application/ld+json">
{"@context":"https://schema.org","@type":"BlogPosting","dateModified":"2024-10-08T00:00:00+00:00","datePublished":"2024-10-08T00:00:00+00:00","description":"Class of 2025","headline":"Team Teach Home","mainEntityOfPage":{"@type":"WebPage","@id":"https://beijanm.github.io/beijan25/teamteachhome"},"url":"https://beijanm.github.io/beijan25/teamteachhome"}</script>
<!-- End Jekyll SEO tag -->

    <link rel="preconnect" href="https://fonts.gstatic.com">
    <link rel="preload" href="https://fonts.googleapis.com/css?family=Open+Sans:400,700&display=swap" as="style" type="text/css" crossorigin>
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <meta name="theme-color" content="#157878">
    <meta name="apple-mobile-web-app-status-bar-style" content="black-translucent">
    <link rel="stylesheet" href="/beijan25/assets/css/style.css?v=13365e5072ad8bb0edf013c81a00cdc04ffd4fc2">
    <!-- start custom head snippets, customize with your own _includes/head-custom.html file -->

<!-- Setup Google Analytics -->



<!-- You can set your favicon here -->
<!-- link rel="shortcut icon" type="image/x-icon" href="/beijan25/favicon.ico" -->

<!-- end custom head snippets -->

  </head>
  <body>
    <a id="skip-to-content" href="#content">Skip to the content.</a>

    <header class="page-header" role="banner">
      <h1 class="project-name">Team Teach Home</h1>
      <h2 class="project-tagline">Class of 2025</h2>
      <a href="/beijan25/" class="btn">Nighthawk Pages</a><a href="/beijan25/blogs/" class="btn">Blogs</a><a href="/beijan25/search/" class="btn">Search</a><a href="/beijan25/about/" class="btn">About</a><a href="/beijan25/README4YML.html" class="btn">Readme</a>
        <a href="https://github.com/beijanm/beijan25" class="btn">View on GitHub</a>
      
    </header>

    <main id="content" class="main-content" role="main">
      <article class="post h-entry" itemscope itemtype="http://schema.org/BlogPosting">

  <header class="post-header"><h1 class="post-title p-name" itemprop="name headline">Team Teach Home</h1><p class="post-meta post-meta-title"><time class="dt-published" datetime="2024-10-08T00:00:00+00:00" itemprop="datePublished">
        Oct 8, 2024
      </time>• <span class="read-time" title="Estimated read time">
    
    
      2 min read
    
</span>
    </p>

    

    </header>

  <div class="post-content e-content" itemprop="articleBody"><style>
  body {
    font-family: 'Arial', sans-serif;
    background-color: #1a1a1a;
    color: #f4f4f4;
    margin: 0;
    padding: 20px;
    display: flex;
    flex-direction: column;
    align-items: center;
  }

  .container {
    max-width: 800px;
    width: 100%;
    background-color: #2c2c2c;
    padding: 40px;
    border-radius: 10px;
    box-shadow: 0 5px 15px rgba(0, 0, 0, 0.5);
    text-align: center;
  }

  h1 {
    font-size: 36px;
    margin-bottom: 40px;
    color: #ffffff;
  }

  .main-link {
    display: inline-block;
    font-size: 22px;
    background-color: #3498db;
    color: white;
    padding: 15px 30px;
    border-radius: 5px;
    text-decoration: none;
    margin-bottom: 30px;
    transition: background-color 0.3s ease;
  }

  .main-link:hover {
    background-color: #2980b9;
  }

  .links {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;
  }

  .link-container {
    width: 48%;
    margin-bottom: 20px;
  }

  .dropdown {
    background-color: #3c3c3c;
    color: #f4f4f4;
    padding: 15px;
    border-radius: 5px;
    text-decoration: none;
    position: relative;
    display: block;
    cursor: pointer;
    transition: background-color 0.3s ease;
  }

  .dropdown:hover {
    background-color: #555555;
  }

  .dropdown-content {
    display: none;
    position: absolute;
    background-color: #555555;
    min-width: 200px;
    box-shadow: 0px 8px 16px 0px rgba(0, 0, 0, 0.2);
    z-index: 1;
    border-radius: 5px;
    padding: 10px;
    top: 40px;
  }

  .dropdown:hover .dropdown-content {
    display: block;
  }

  ul {
    text-align: left;
    padding-left: 20px;
  }
</style>

<div class="container">
  <h1>Programming Topics</h1>

  <div class="links">
    <!-- Dropdown for Unit 1 -->
        <div class="link-container">
      <div class="dropdown" onclick="window.location.href='/beijan25/U1';">Unit 1 — Variables and Assignments
        <div class="dropdown-content">
          <ul>
            <li>Naming: SnakeCase, Pascal Case, CamelCase</li>
            <li>Types of Variables: Intigers, Strings, Boolean, Floats, Lists, Dictionaries</li>
            <li>Operators</li>
            <li>Arrays and Objects in Javascript: Arrays, Objects</li>
          </ul>
        </div>
      </div>
    </div>
    <!-- Dropdown for Unit 2 -->
    <div class="link-container">
      <div class="dropdown" onclick="window.location.href='/beijan25/U2';">Unit 2 — Data Abstraction
        <div class="dropdown-content">
          <ul>
            <li>Learned how various data types can use abstraction for efficiency</li>
            <li>Created dictionaries to encapse variables</li>
            <li>Learned about number functions to create a simple javascript and python calculator</li>
            <li>Learned about looping through strings to print outputs in python</li>
            <li>Functions that compare different strings with eachother, and returning true or false outputs.</li>
          </ul>
        </div>
      </div>
    </div>
    <!-- Dropdown for Unit 3 -->
    <div class="link-container">
      <div class="dropdown" onclick="window.location.href='/beijan25/U3';">Unit 3 — Mathematical Expressions
        <div class="dropdown-content">
          <ul>
            <li>Using arithmetic operators (+,-,*,/) to perform calculatoins</li>
            <li>Also learned the code for factorials involving variable creation as well as multiplication and subtraction. Can also use division and addition based on personal preference.</li>
            <li>Learned about fibonacci sequence and how to calculate the "n"th digit of fibonacci sequence</li>
          </ul>
        </div>
      </div>
    </div>
    <!-- Dropdown for Unit 4 -->
    <div class="link-container">
      <div class="dropdown" onclick="window.location.href='/beijan25/U4';">Unit 4 — Strings and String Operations
        <div class="dropdown-content">
          <ul>
            <li>Go over string functions in both javascript and python as follows:</li>
            <li>Concatenation, Interpolation, Indexing (substrings), escape characters (javascript)</li>
            <li>Using looping to create a palindrome checker and reverse order hack (python)</li>
          </ul>
        </div>
      </div>
    </div>
    <!-- Dropdown for Unit 5 -->
    <div class="link-container">
      <div class="dropdown" onclick="window.location.href='/beijan25/U5';">Unit 5 — Boolean Expressions
        <div class="dropdown-content">
          <ul>
            <li>Learned how boolean expressions involve using loops and conditions to make decisions.</li>
            <li>Rational Operators, Logical Operators </li>
            <li>Creating Logic Gate Similator in boty Python and Java</li>
            <li>Contrapositive Law in Python and Java</li>
          </ul>
        </div>
      </div>
    </div>
    <!-- Dropdown for Unit 6 -->
    <div class="link-container">
      <div class="dropdown" onclick="window.location.href='/beijan25/U6';">Unit 6 — Conditionals
        <div class="dropdown-content">
          <ul>
            <li>Go over If Statements, Else Statements, Javascript and Python Examples. </li>
            <li>Use these conditionals in our popcorn hacks</li>
          </ul>
        </div>
      </div>
    </div>
    <!-- Dropdown for Unit 7 -->
    <div class="link-container">
      <div class="dropdown" onclick="window.location.href='/beijan25/U7';">Unit 7 — Nested Conditionals
        <div class="dropdown-content">
          <ul>
            <li>If statements, Else Statements, Nested Conditions, and Examples in both languages we're learning.</li>
            <li>Conditionals using variables and operations to pair with if and else statements to create programs.</li>
          </ul>
        </div>
      </div>
    </div>
    <!-- Dropdown for Unit 8 -->
    <div class="link-container">
      <div class="dropdown" onclick="window.location.href='/beijan25/U8';">Unit 8 — Iterations
        <div class="dropdown-content">
          <ul>
            <li>Going over Looping: For Loops, While Loops / Do-While Loops, Index Loops</li>
            <li>Learning how to continue and break loops</li>
            <li>Endless/Infinite loop. When Condition is not met then loop continues infintetly</li>
            <li>Common operations: iterating over rows and columns.</li>
            <li>Using exceptions with loops</li>
          </ul>
        </div>
      </div>
    </div>
    <!-- Dropdown for Unit 9 -->
    <div class="link-container">
      <div class="dropdown" onclick="window.location.href='/beijan25/U';">Unit 10 — Lists
        <div class="dropdown-content">
          <ul>
            <li>Learning how storage and maniplation of data is performed using indexing and lists.</li>
            <li>Learned how to: Add values to lists, insert elements to list, append elements to end of lists, remove elements from list, and calculate the length of a list.</li>
            <li>Learned about Pseudocode:</li>
            <li>Variables in sudocode, number lists, modulus operator (remainder) and control structures.</li>
            <li>Practiced using iterations in functions.</li>
          </ul>
        </div>
      </div>
    </div>
    <!-- The Link for the issue -->
    <a href="/beijan25/revtic-TT" class="main-link">Go to My Issue</a>
  </div>
</div>


  </div><!-- from https://github.com/utterance/utterances -->
<script src="https://utteranc.es/client.js"
        repo="beijanm/beijan25"
        issue-term="title"
        label="blogpost-comment"
        theme="github-light"
        crossorigin="anonymous"
        async>
</script><a class="u-url" href="/beijan25/teamteachhome" hidden></a>
</article>


      <footer class="site-footer">
        
          <span class="site-footer-owner"><a href="https://github.com/beijanm/beijan25">beijan25</a> is maintained by <a href="https://github.com/beijanm">beijanm</a>.</span>
        
        <span class="site-footer-credits">This page was generated by <a href="https://pages.github.com">GitHub Pages</a>.</span>
      </footer>
    </main>
  </body>
</html>
</html>
