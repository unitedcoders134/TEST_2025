---
layout: page
title: About
permalink: /about/
comments: true
---

<style>
    /* Gradient background styling */
    html {
        margin: 0;
        font-family: Arial, sans-serif;
        background: linear-gradient(to bottom right, #b3b3b3, #4d4d4d);
        color: white;
    }

    /* Styling for the flag container */
    .flag-container {
        display: flex;
        align-items: center;
        justify-content: center;
        margin-top: 50px;
    }

    .flag {
        text-align: center;
        margin-right: 20px;
    }

    .flag img {
        width: 200px;
    }

    /* Centering and text styling */
    h1 {
        text-align: center;
        margin-top: 30px;
    }

    ul {
        list-style: none;
        padding: 0;
        text-align: center;
        line-height: 1.8;
    }
</style>

<ul>
    <li>👋 Hi, I'm <strong>Mihir Thaha</strong>!</li>
    <li>🇮🇳 <strong>Nationality:</strong> Indian</li>
    <li>🎂 <strong>Age:</strong> 15 years old</li>
    <li>🎓 <strong>Education:</strong> Sophomore at Del Norte High School</li>
    <li>🌍 <strong>Location:</strong> California, USA</li>
</ul>

# About Me

👋 Hi, I'm Mihir Thaha!

I’m currently a sophomore at Del Norte High School in California, USA. I love learning about diverse cultures and languages, which has shaped how I approach life and learning.

### My Interests
I'm passionate about technology, especially in areas like coding, web development, and engineering. I’ve been learning Python and JavaScript, working on small projects that help me build my skills and understanding of how software works.

### Hobbies
I love playing badminton and basketball, as well as going to the gym. I also like reading and watching YouTube in my freetime. I also am a big fan of music, and it is as part of my life. 

### Future Goals
In this course, I expect to build a functional website and expand my knowledge on computer science. I also want to have fun while coding.

### Connect With Me
Feel free to check out my [GitHub](https://github.com/mihirthaha) for my latest projects, or contact me at [mihirthaha@gmail.com](mailto:mihirthaha@gmail.com).


<script>
  // Function to toggle the theme
  function toggleTheme() {
    let body = document.body;
    let currentTheme = body.dataset.theme;
    
    if (currentTheme === "dark") {
      body.dataset.theme = "light";
      localStorage.setItem("theme", "light");
    } else {
      body.dataset.theme = "dark";
      localStorage.setItem("theme", "dark");
    }
    applyTheme();
  }

  // Apply the saved theme from localStorage
  function applyTheme() {
    let savedTheme = localStorage.getItem("theme") || "light";
    document.body.dataset.theme = savedTheme;
  }

  // Run theme initialization on page load
  document.addEventListener("DOMContentLoaded", applyTheme);
</script>

<style>
  body[data-theme='dark'] {
    background-color: #2e2e2e;
    color: #ffffff;
  }
  body[data-theme='light'] {
    background-color: #ffffff;
    color: #000000;
  }
    body[data-theme='blue'] {
    background-color: #AEC6CF;
    color: white;
  }
</style>

<!-- Flag Container -->
<div class="flag-container">
    <div class="flag">
        <p>California</p>
        <img src="https://upload.wikimedia.org/wikipedia/commons/0/01/Flag_of_California.svg" alt="California Flag">
    </div>
    <div class="flag">
        <p>India</p>
        <img src="https://upload.wikimedia.org/wikipedia/en/4/41/Flag_of_India.svg" alt="Indian Flag">
    </div>
</div>



<script src="https://utteranc.es/client.js"
        repo="[ENTER REPO HERE]"
        issue-term="pathname"
        theme="icy-dark"
        crossorigin="anonymous"
        async>
</script>


