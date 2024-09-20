---
layout: page
title: About
permalink: /about/
---

<style>
    body {
        font-family: Arial, sans-serif;
        background-color: #FFFFFF;
        color: #FFFFFF;
        margin: 0;
        padding: 0;
        line-height: 1.6;
        transition: background-color 0.5s, color 0.5s;
        scroll-behavior: smooth; /* For smooth scrolling */
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

    /* Typing animation for header */
    h1 {
        text-align: center;
        color: #007acc;
        margin-top: 0;
        margin-bottom: 10px;
        font-size: 2.5em;
        border-right: 2px solid #007acc;
        white-space: nowrap;
        overflow: hidden;
        animation: typing 3s steps(22) 1s 1 normal both, blink-caret 0.75s step-end infinite;
    }

    @keyframes typing {
        from { width: 0; }
        to { width: 100%; }
    }

    @keyframes blink-caret {
        from, to { border-color: transparent; }
        50% { border-color: #007acc; }
    }

    .flags {
        text-align: center;
        margin: 10px 0;
    }

    .flags img {
        width: 100px;
        margin: 5px;
        transition: transform 0.3s ease-in-out;
    }

    .flags img:hover {
        transform: scale(1.1) rotate(10deg);
    }

    .bike-emoji {
        font-size: 2em;
    }

    .fun-facts {
        background-color: #007acc;
        color: white;
        padding: 10px;
        border-radius: 5px;
        margin-top: 10px;
        font-style: italic;
        position: relative;
        overflow: hidden;
        transition: background-color 0.5s ease;
    }

    .fun-facts::before {
        content: '';
        position: absolute;
        top: 0;
        left: -100%;
        width: 100%;
        height: 100%;
        background: rgba(255, 255, 255, 0.3);
        transform: skewX(-45deg);
        transition: left 0.5s;
    }

    .fun-facts:hover::before {
        left: 100%;
    }

    .family-section {
        background-color: #FFFFFF;
        color: #000000;
        padding: 10px;
        border-radius: 8px;
        margin-top: 10px;
        border: 1px solid #007acc;
        animation: slideInUp 1s;
    }

    .family-section h2 {
        color: #007acc;
        margin-top: 0;
        transition: color 0.3s ease;
    }

    .family-section h2:hover {
        color: #005fa3;
    }

    .image-gallery {
        margin-top: 20px;
        animation: zoomIn 1s;
        perspective: 1000px; /* Add depth for 3D effect */
    }

    .image-gallery img {
        max-width: 100%;
        height: 300px;
        object-fit: cover;
        display: block;
        margin: 0 auto;
        border-radius: 10px;
        transition: transform 0.3s ease-in-out;
        transform-style: preserve-3d;
    }

    .image-gallery img:hover {
        transform: scale(1.05) rotateY(10deg);
    }

    .button-container {
        text-align: center;
        margin-top: 10px;
    }

    button {
        background-color: #007acc;
        color: white;
        padding: 10px 20px;
        border: none;
        border-radius: 5px;
        cursor: pointer;
        transition: background-color 0.3s, transform 0.3s, box-shadow 0.3s;
        box-shadow: 0 0 10px rgba(0, 122, 204, 0.5);
    }

    button:hover {
        background-color: #005fa3;
        transform: scale(1.1);
        box-shadow: 0 0 15px rgba(0, 122, 204, 0.8);
    }

    @keyframes slideInUp {
        from {
            opacity: 0;
            transform: translateY(20px);
        }
        to {
            opacity: 1;
            transform: translateY(0);
        }
    }

    @keyframes zoomIn {
        from {
            opacity: 0;
            transform: scale(0.8);
        }
        to {
            opacity: 1;
            transform: scale(1);
        }
    }

    /* Parallax effect for the body background */
    body {
        background-image: url('https://www.transparenttextures.com/patterns/asfalt-dark.png');
        background-attachment: fixed;
        background-position: center;
        background-repeat: no-repeat;
        background-size: cover;
    }
</style>

<div class="container">
    <h1>Manas</h1>

    <ul>
        <li><strong>Computer Science + Biking = Me!</strong> I’m a sophomore at Del Norte High with a passion for coding and a love for street riding <span class="bike-emoji">🚴‍♂️</span>.</li>
        <li><strong>From Bangalore to California</strong>—I moved here last year and have been balancing both tech hubs ever since.</li>
    </ul>

    <div class="flags">
        <img src="https://upload.wikimedia.org/wikipedia/en/4/41/Flag_of_India.svg" alt="Indian Flag">
        <img src="https://upload.wikimedia.org/wikipedia/commons/0/01/Flag_of_California.svg" alt="California Flag">
    </div>

    <div class="fun-facts">
        Fun Fact: Bangalore is India’s Silicon Valley! Seems like I was destined to end up in tech.
    </div>

    <div class="family-section">
        <h2>Meet My Family</h2>
        <ul>
            <li>My dad has been working in the tech industry for over 20 years and has been with Qualcomm for the past 13 years.</li>
            <li>My mom has been in the pharma domain for over 20 years.</li>
            <li>My sister is a business major at UCSD. (That was the reason we moved).</li>
        </ul>
    </div>

    <!-- Theme switcher button -->
    <div class="button-container">
        <p>You can change the theme to your liking! If you like dark mode or light mode, you pick!!</p>
        <button id="theme-switcher">Switch Theme</button>
    </div>

    <script>
        const themeSwitcher = document.getElementById('theme-switcher');
        let isDarkTheme = true;

        themeSwitcher.addEventListener('click', function() {
            if (isDarkTheme) {
                document.body.style.backgroundColor = "#f0f0f0";
                document.body.style.color = "#000000";
                document.querySelector('.container').style.backgroundColor = "#ffffff";
                isDarkTheme = false;
            } else {
                document.body.style.backgroundColor = "#000000";
                document.body.style.color = "#ffffff";
                document.querySelector('.container').style.backgroundColor = "#000000";
                isDarkTheme = true;
            }
        });
    </script>

    <!-- Image gallery -->
    <h2>Here's a sneak peek into my life!!!</h2>
    <div class="image-gallery">
        <img id="gallery-image" src="{{site.baseurl}}/images/gallery.jpg" alt="Main Image">
    </div>

    <div class="button-container">
        <button id="prev-btn">Previous</button>
        <button id="next-btn">Next</button>
    </div>

    <script>
        const images = [
            "{{site.baseurl}}/images/bike.jpg",
            "{{site.baseurl}}/images/familyphoto.jpg",
            "{{site.baseurl}}/images/cologne.jpg",
            "{{site.baseurl}}/images/fam.jpg",
            "{{site.baseurl}}/images/universal.jpg",
            "{{site.baseurl}}/images/fat.jpg",
            "{{site.baseurl}}/images/wheelie.jpg",
            "{{site.baseurl}}/images/wheelie2.jpg",
        ];

        let currentIndex = 0;

        const nextBtn = document.getElementById('next-btn');
        const prevBtn = document.getElementById('prev-btn');
        const galleryImage = document.getElementById('gallery-image');

        nextBtn.addEventListener('click', function() {
            currentIndex = (currentIndex + 1) % images.length;
            galleryImage.src = images[currentIndex];
        });

        prevBtn.addEventListener('click', function() {
            currentIndex = (currentIndex - 1 + images.length) % images.length;
            galleryImage.src = images[currentIndex];
        });
    </script>

    <script src="https://utteranc.es/client.js"
        repo="manas12709/manas_2025"
        issue-term="pathname"
        theme="github-light"
        crossorigin="anonymous"
        async>
    </script>
</div>


