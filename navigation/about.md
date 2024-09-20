---
layout: page
title: About Manas
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

<!-- Chatbot Container -->
<div class="chatbot-container">
    <div id="chatbot-box" style="background-color: #333; color: white; padding: 20px; border-radius: 8px; max-width: 400px; margin: 20px auto;">
        <div id="chatbot-messages" style="height: 200px; overflow-y: auto; margin-bottom: 10px; border: 1px solid #555; padding: 10px; border-radius: 5px;">
            <div>Chatbot: Hi! I'm your virtual assistant. How can I help you today?</div>
        </div>
        <input type="text" id="chatbot-input" placeholder="Ask me anything..." style="width: 75%; padding: 10px; border-radius: 5px; border: 1px solid #555;">
        <button id="chatbot-send" style="padding: 10px; background-color: #007acc; color: white; border: none; border-radius: 5px;">Send</button>
    </div>
</div>

<script>
    const chatbotMessages = document.getElementById('chatbot-messages');
    const chatbotInput = document.getElementById('chatbot-input');
    const chatbotSend = document.getElementById('chatbot-send');

    chatbotSend.addEventListener('click', function() {
        const userMessage = chatbotInput.value;
        if (!userMessage) return;

        // Display user message
        const userMsgElement = document.createElement('div');
        userMsgElement.textContent = "You: " + userMessage;
        chatbotMessages.appendChild(userMsgElement);
        chatbotMessages.scrollTop = chatbotMessages.scrollHeight;

        // Clear input
        chatbotInput.value = '';

        // Response logic
        let botResponse = "I'm not sure I understand that.";

        const lowerCaseMsg = userMessage.toLowerCase();

        // Adding a variety of responses for different keywords
        if (lowerCaseMsg.includes("hello") || lowerCaseMsg.includes("hi")) {
            botResponse = "Hello! How's your day going?";
        } else if (lowerCaseMsg.includes("bike")) {
            botResponse = "You seem to love bikes! What's your favorite route to ride on?";
        } else if (lowerCaseMsg.includes("computer")) {
            botResponse = "Computers are fascinating! Do you prefer coding or building them?";
        } else if (lowerCaseMsg.includes("family")) {
            botResponse = "Family is everything. How do you like spending time with yours?";
        } else if (lowerCaseMsg.includes("coding") || lowerCaseMsg.includes("programming")) {
            botResponse = "Coding is like solving puzzles! What's your favorite language to code in?";
        } else if (lowerCaseMsg.includes("python")) {
            botResponse = "Python is a great choice for automation, data science, and more. Do you enjoy working with it?";
        } else if (lowerCaseMsg.includes("javascript")) {
            botResponse = "JavaScript makes the web come alive! Any favorite projects you’ve worked on?";
        } else if (lowerCaseMsg.includes("biking")) {
            botResponse = "Biking keeps you fit and clears your mind! What's your best biking memory?";
        } else if (lowerCaseMsg.includes("california")) {
            botResponse = "California is so diverse, from beaches to mountains! What's your favorite spot?";
        } else if (lowerCaseMsg.includes("india")) {
            botResponse = "India has such a rich history and culture. Do you miss Bangalore?";
        } else if (lowerCaseMsg.includes("school") || lowerCaseMsg.includes("study")) {
            botResponse = "School can be challenging, but rewarding! What's your favorite subject?";
        } else if (lowerCaseMsg.includes("hobby")) {
            botResponse = "Hobbies are a great way to unwind. What's one hobby you can't live without?";
        } else if (lowerCaseMsg.includes("music")) {
            botResponse = "Music makes everything better! Who’s your favorite artist or band?";
        } else if (lowerCaseMsg.includes("movie")) {
            botResponse = "Movies can transport us to another world. What’s your favorite genre?";
        } else if (lowerCaseMsg.includes("travel")) {
            botResponse = "Traveling expands your horizons! Is there a dream destination on your list?";
        } else if (lowerCaseMsg.includes("sports")) {
            botResponse = "Sports are fun! Which one do you like playing or watching?";
        } else if (lowerCaseMsg.includes("football")) {
            botResponse = "Football is exciting! Do you play or just enjoy watching it?";
        } else if (lowerCaseMsg.includes("coding project")) {
            botResponse = "I'd love to hear more about your coding projects. What are you working on?";
        } else if (lowerCaseMsg.includes("workout") || lowerCaseMsg.includes("gym")) {
            botResponse = "Staying fit is so important! What’s your workout routine like?";
        } else if (lowerCaseMsg.includes("exercise")) {
            botResponse = "Exercise keeps the mind and body sharp! Do you have a favorite exercise?";
        } else if (lowerCaseMsg.includes("food")) {
            botResponse = "Food is love! What's your favorite dish to eat or cook?";
        } else if (lowerCaseMsg.includes("book")) {
            botResponse = "Books are a portal to different worlds! Do you have a favorite author or book?";
        } else if (lowerCaseMsg.includes("game")) {
            botResponse = "Games are a great way to unwind! What games are you into right now?";
        } else if (lowerCaseMsg.includes("fun fact")) {
            botResponse = "Did you know honey never spoils? What's your favorite random fact?";
        } else if (lowerCaseMsg.includes("weather")) {
            botResponse = "The weather can really set the mood! What's it like outside today?";
        } else if (lowerCaseMsg.includes("advice")) {
            botResponse = "I'm happy to help! What do you need advice on?";
        } else if (lowerCaseMsg.includes("thanks") || lowerCaseMsg.includes("thank you")) {
            botResponse = "You're welcome! Happy to help.";
        } else if (lowerCaseMsg.includes("bye")) {
            botResponse = "Goodbye! Chat with me anytime you like!";
        } else if (lowerCaseMsg.includes("joke")) {
            botResponse = "Why don't scientists trust atoms? Because they make up everything!";
        } else if (lowerCaseMsg.includes("time")) {
            botResponse = `It's ${new Date().toLocaleTimeString()} right now!`;
        } else if (lowerCaseMsg.includes("day")) {
            botResponse = `It's ${new Date().toLocaleDateString()} today!`;
        }

        // Display bot response
        const botMsgElement = document.createElement('div');
        botMsgElement.textContent = "Chatbot: " + botResponse;
        chatbotMessages.appendChild(botMsgElement);
        chatbotMessages.scrollTop = chatbotMessages.scrollHeight;
    });
</script>


