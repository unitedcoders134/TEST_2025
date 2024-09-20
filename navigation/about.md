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
        margin: 20px;
        line-height: 1.6;
    }
    .container {
        max-width: 800px;
        margin: 0 auto;
        padding: 20px;
        background-color: #000;
        border-radius: 8px;
        box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
    }
    h1 {
        text-align: center;
        color: #007acc;
    }
    .flags {
        text-align: center;
        margin-top: 20px;
    }
    .flags img {
        width: 100px;
        margin: 10px;
    }
    .bike-emoji {
        font-size: 2em;
    }
    .fun-facts {
        background-color: #007acc;
        color: white;
        padding: 10px;
        border-radius: 5px;
        margin-top: 20px;
        font-style: italic;
    }
    .family-section {
        background-color: #FFFFFF;
        color: #000000; /* Changed text color to black */
        padding: 20px;
        border-radius: 8px;
        margin-top: 20px;
        border: 1px solid #007acc;
    }
    .family-section h2 {
        color: #007acc;
    }
    .family-section img {
        width: 150px;
        border-radius: 50%;
        margin: 10px 0;
    }
    ul {
        list-style-type: disc;
        margin-left: 20px;
    }
     /* Styling for gallery and buttons */
    .image-gallery img {
        max-width: 100%;
        height: 300px; /* Ensures uniform image height */
        object-fit: cover; /* Ensures the image fits within the container */
        display: block;
        margin: 0 auto;
    }
    .button-container {
        text-align: center;
        margin-top: 20px;
    }
    button {
        background-color: #007acc;
        color: white;
        padding: 10px 20px;
        border: none;
        border-radius: 5px;
        cursor: pointer;
    }
    button:hover {
        background-color: #005fa3;
    }
    /* Remove dead space above the family section */
    .family-section {
        margin-top: 0;
        padding-top: 40px; /* Keep some padding for visual separation */
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
        // Function to toggle between light and dark theme
        const themeSwitcher = document.getElementById('theme-switcher');
        let isDarkTheme = true;

        themeSwitcher.addEventListener('click', function() {
            if (isDarkTheme) {
                document.body.style.backgroundColor = "#f0f0f0";  // Light theme background
                document.body.style.color = "#000000";  // Light theme text color
                document.querySelector('.container').style.backgroundColor = "#ffffff";  // Light theme container
                isDarkTheme = false;
            } else {
                document.body.style.backgroundColor = "#000000";  // Dark theme background
                document.body.style.color = "#ffffff";  // Dark theme text color
                document.querySelector('.container').style.backgroundColor = "#000000";  // Dark theme container
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
    // Array of image sources
    const images = [
        "{{site.baseurl}}/images/bike.jpg",
        "{{site.baseurl}}/images/familyphoto.jpg",
        "{{site.baseurl}}/images/cologne.jpg",
        "{{site.baseurl}}/images/fam.jpg",
        "{{site.baseurl}}/images/universal.jpg",
        "{{site.baseurl}}/images/fat.jpg",
    ];

    let currentIndex = 0;

    const nextBtn = document.getElementById('next-btn');
    const prevBtn = document.getElementById('prev-btn');
    const galleryImage = document.getElementById('gallery-image');

    // Function to display the next image
    nextBtn.addEventListener('click', function() {
        currentIndex = (currentIndex + 1) % images.length;  // Increment index and loop back to start
        galleryImage.src = images[currentIndex];  // Change the image source
    });

    // Function to display the previous image
    prevBtn.addEventListener('click', function() {
        currentIndex = (currentIndex - 1 + images.length) % images.length;  // Decrement index and loop back to end if necessary
        galleryImage.src = images[currentIndex];  // Change the image source
    });
</script>

<script src="https://utteranc.es/client.js"
        repo="manas12709/manas_2025"
        issue-term="pathname"
        theme="github-light"
        crossorigin="anonymous"
        async>
</script>
