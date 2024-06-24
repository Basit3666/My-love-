<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My Love Story</title>
    <style>
        body {
            font-family: 'Georgia', serif;
            margin: 0;
            padding: 0;
            background: linear-gradient(to bottom, #ffcccc, #ffe6e6);
            color: #333;
            text-align: center;
            overflow-x: hidden;
        }
        header {
            background-color: #ff99cc;
            color: white;
            padding: 20px;
            font-size: 2.5em;
            border-bottom: 2px solid #ff6699;
        }
        .carousel {
            display: flex;
            overflow: hidden;
            width: 80%;
            margin: 20px auto;
            border-radius: 10px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        }
        .carousel img {
            max-width: 100%;
            transition: transform 0.5s ease-in-out;
        }
        .buttons {
            margin: 20px;
        }
        .buttons button {
            background-color: #ff99cc;
            color: white;
            border: none;
            padding: 10px 20px;
            cursor: pointer;
            font-size: 1em;
            margin: 0 10px;
            border-radius: 5px;
        }
        .buttons button:hover {
            background-color: #ff6699;
        }
        .message {
            font-size: 1.5em;
            color: #990033;
            margin: 20px 0;
        }
        .hidden-message {
            display: none;
            font-size: 1.2em;
            color: #ff6699;
            margin: 20px 0;
        }
        footer {
            background-color: #ff99cc;
            color: white;
            padding: 10px 0;
            position: fixed;
            bottom: 0;
            width: 100%;
        }
        @keyframes beat {
            0%, 100% {
                transform: scale(1);
            }
            50% {
                transform: scale(1.1);
            }
        }
    </style>
</head>
<body>
    <header>
       Madam Jee Narazgii Khatam Kayoo na...
    </header>
    <section>
        <div class="carousel" id="carousel">
            <img src="https://i.pinimg.com/564x/03/68/0a/03680aba4f151b9244e15603b464e7fa.jpg" alt="Moment 1">
            <img src="https://i.pinimg.com/564x/66/49/81/66498147a26006e130cb4a19e9511e9e.jpg" alt="Moment 2">
            <img src="https://i.pinimg.com/564x/2e/72/53/2e725373feb269176e720fb6a013bd56.jpg" alt="Moment 3">
        </div>
        <div class="buttons">
            <button onclick="prevSlide()">&#10094; Previous</button>
            <button onclick="nextSlide()">Next &#10095;</button>
        </div>
        <div class="message">
            <p>My dearest [Madam],</p>
            <p>Munji Pyarii Madam We'll gonna acheive everything together <3.</p>
        </div>
        <div class="buttons">
            <button onclick="revealMessage()">Click for a Special Message</button>
        </div>
        <div class="hidden-message" id="hiddenMessage">
            <p>You are my everything, Munjii Pyarii Madam  💖</p>
        </div>
    </section>
    <footer>
        <p>&copy; 2024 [Esco~]. All my love forever.</p>
    </footer>
    <script>
        let currentSlide = 0;

        function showSlide(index) {
            const slides = document.querySelectorAll('.carousel img');
            if (index >= slides.length) {
                currentSlide = 0;
            } else if (index < 0) {
                currentSlide = slides.length - 1;
            } else {
                currentSlide = index;
            }
            const offset = -currentSlide * 100;
            slides.forEach(slide => {
                slide.style.transform = `translateX(${offset}%)`;
            });
        }

        function nextSlide() {
            showSlide(currentSlide + 1);
        }

        function prevSlide() {
            showSlide(currentSlide - 1);
        }

        function revealMessage() {
            const message = document.getElementById('hiddenMessage');
            if (message.style.display === "none" || message.style.display === "") {
                message.style.display = "block";
            } else {
                message.style.display = "none";
            }
        }

        document.addEventListener('DOMContentLoaded', () => {
            showSlide(currentSlide);
        });
    </script>
</body>
</html>
