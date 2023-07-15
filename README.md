# appV4
j'ai ajouter un carousel dans mon app 

  <title>APP</title>
    <link href="https://fonts.googleapis.com/css2?family=Roboto:wght@400;500&display=swap" rel="stylesheet">
    <link href="https://fonts.googleapis.com/icon?family=Material+Icons" rel="stylesheet">
</head>
<body>
    
    <nav>
        <ul>
            <li><a href="#"><span class="material-icons">home</span> Accueil</a></li>
            <li><a href="asitepresentation.html"><span class="material-icons">school</span> Exercice</a></li>
        </ul>
    </nav>
    
    <h1> <u>Les App</u></h1>
  
    <div class="container">
        <div class="carousel">
            <div class="game game-perspective">
                <span class="material-icons">filter_1</span>
                <h2>Trouve le Numéro</h2>
            </div>

            <div class="game game-perspective">
                <span class="material-icons">transform</span>
                <h2>Quizz</h2>
            </div>

            <div class="game game-perspective">
                <span class="material-icons">local_offer</span>
                <h2>Réduction %</h2>
            </div>

            <div class="game game-perspective">
                <span class="material-icons">transform</span>
                <h2>Génerateur de MDP</h2>
            </div>

            <div class="game game-perspective">
                <span class="material-icons">shuffle</span>
                <h2>Aléatoire</h2>
            </div>
        </div>

        <div class="other-games">
            <div class="game game-perspective" onclick="window.location.href = 'chifoumie.html';">
                <span class="material-icons">gesture</span>
                <h2>Chifoumi</h2>
            </div>

            <div class="game game-perspective" onclick="window.location.href = 'nombrepremier.html';">
                <span class="material-icons">filter_none</span>
                <h2>Nombre Premier</h2>
            </div>

            <div class="game game-perspective" onclick="window.location.href = 'loto.html';">
                <span class="material-icons">casino</span>
                <h2>Loto</h2>
            </div>

            <div class="game game-perspective" onclick="window.location.href='convertiseur.html';">
                <span class="material-icons">transform</span>
                <h2>Convertisseur</h2>
            </div>

            <div class="game game-perspective" onclick="window.location.href='conv.html';">
                <span class="material-icons">access_time</span>
                <h2>Temps</h2>
            </div>

            <div class="game game-perspective" onclick="window.location.href='citation.html';">
                <span class="material-icons">transform</span>
                <h2>Citations &amp; Blagues</h2>
            </div>

            <div class="game game-perspective" onclick="window.location.href='conn.html';">
                <span class="material-icons">transform</span>
                <h2>Secret</h2>
            </div>
        </div>
    </div>

    <script>
        window.addEventListener('DOMContentLoaded', function() {
            var carousel = document.querySelector('.carousel');
            var carouselItems = document.querySelectorAll('.carousel .game-perspective');
        
            var currentIndex = 0;
        
            function navigateCarousel(index) {
                currentIndex = index;
                carousel.style.transform = `translateX(-${currentIndex * 100}%)`;
            }
        
            carouselItems.forEach(function(item, index) {
                item.addEventListener('click', function() {
                    navigateCarousel(index);
                });
            });
        });
    </script>
</body>
</html>

<style>
    body {
        font-family: 'Roboto', sans-serif;
        background-color: #292f3f;
        color: #fff;
        margin: 0;
        padding: 0;
    }

    nav {
        background: linear-gradient(to right, #292f3f, #007bff);
        padding: 20px 0;
        position: sticky;
        top: 0;
        z-index: 10;
    }

    nav ul {
        list-style-type: none;
        margin: 0;
        padding: 0;
        display: flex;
        justify-content: space-around;
        max-width: 960px;
        margin: 0 auto;
    }

    nav li a {
        color: #fff;
        text-decoration: none;
        font-size: 18px;
        transition: color 0.3s ease;
    }

    nav li a:hover {
        color: #292f3f;
    }

    .container {
        max-width: 960px;
        margin: 50px auto;
        padding: 0 20px;
    }

    h1 {
        text-align: center;
        font-size: 36px;
        margin-top: 40px;
    }

    .carousel {
        display: flex;
        overflow-x: scroll;
        scroll-snap-type: x mandatory;
        margin-bottom: 30px;
    }

    .carousel::-webkit-scrollbar {
        display: none;
    }
    .game {
        flex-shrink: 0;
        width: calc(50% - 20px); /* Adjust width for mobile */
        max-width: 400px; /* Adjust maximum width for web */
        background-color: #007bff;
        border-radius: 10px;
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        height: 250px; /* Adjust height for mobile and web */
        margin-right: 20px; /* Added margin-right */
        margin-bottom: 30px;
        cursor: pointer;
        box-shadow: 0px 5px 15px rgba(0, 0, 0, 0.1);
        animation: game-perspective-animation 2s infinite alternate;
        transform-style: preserve-3d;
    }
    .game-perspective-active {
        animation: none;
    }

    .other-games {
        display: flex;
        flex-wrap: wrap;
        justify-content: space-between;
        margin-top: 30px;
    }

    .game {
        margin-bottom: 30px;
    }

    h2 {
        font-size: 24px;
        text-align: center;
    }

    .material-icons {
        font-size: 48px;
        margin-bottom: 10px;
    }

    @keyframes game-perspective-animation {
        0% {
            transform: perspective(1000px) rotateX(0deg) scale(1);
        }

        100% {
            transform: perspective(1000px) rotateX(10deg) scale(1.05);
        }
    }
    @media (max-width: 600px) {
        .carousel {
            flex-wrap: nowrap;
            overflow-x: auto;
            margin-bottom: 0;
            scroll-snap-type: none; /* Disable scroll snap on mobile */
        }

      
    
        .game {
            width: calc(90% - 20px); /* Adjust width to fill the full width on mobile */
        }

        .other-games {
            flex-direction: column;
            align-items: center;
            margin-top: 30px; /* Add margin-top to create spacing */
        }
    }
</style>
