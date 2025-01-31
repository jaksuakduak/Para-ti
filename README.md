# Para-ti
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>¿Quieres ser mi San Valentín?</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <div class="container">
        <h1>¿Quieres ser mi San Valentín? ❤️</h1>
        <div class="buttons">
            <button id="yes">Sí</button>
            <button id="no">No</button>
        </div>
        <p id="message"></p>
    </div>
    <script src="script.js"></script>
</body>
</html>
body {
    font-family: Arial, sans-serif;
    text-align: center;
    background: url('https://source.unsplash.com/1600x900/?love,romantic') no-repeat center center fixed;
    background-size: cover;
    color: white;
}

.container {
    margin-top: 20%;
    background: rgba(0, 0, 0, 0.6);
    padding: 20px;
    border-radius: 15px;
    display: inline-block;
}

h1 {
    font-size: 2em;
}

.buttons {
    margin-top: 20px;
}

button {
    font-size: 1.5em;
    padding: 10px 20px;
    margin: 10px;
    border: none;
    border-radius: 10px;
    cursor: pointer;
    transition: 0.3s;
}

#yes {
    background-color: #ff4d79;
    color: white;
}

#no {
    background-color: #333;
    color: white;
    position: absolute;
}

#message {
    font-size: 1.5em;
    margin-top: 20px;
    display: none;
}

.heart {
    position: absolute;
    font-size: 2em;
    color: red;
    animation: float 2s linear infinite;
}

@keyframes float {
    0% { transform: translateY(0); opacity: 1; }
    100% { transform: translateY(-100px); opacity: 0; }
}
document.addEventListener("DOMContentLoaded", function () {
    const noButton = document.getElementById("no");
    const yesButton = document.getElementById("yes");
    const message = document.getElementById("message");

    // Mueve el botón "No" cuando se pasa el mouse por encima
    noButton.addEventListener("mouseover", function () {
        const x = Math.random() * (window.innerWidth - 100);
        const y = Math.random() * (window.innerHeight - 50);
        noButton.style.left = `${x}px`;
        noButton.style.top = `${y}px`;
    });

    // Mensaje al hacer clic en "Sí"
    yesButton.addEventListener("click", function () {
        message.innerHTML = "¡Sabía que dirías que sí! ❤️💖";
        message.style.display = "block";

        // Crear corazones flotantes
        for (let i = 0; i < 20; i++) {
            createHeart();
        }
    });

    // Función para crear corazones flotantes
    function createHeart() {
        const heart = document.createElement("div");
        heart.innerHTML = "❤️";
        heart.classList.add("heart");
        document.body.appendChild(heart);

        heart.style.left = `${Math.random() * window.innerWidth}px`;
        heart.style.top = `${window.innerHeight}px`;

        setTimeout(() => {
            heart.remove();
        }, 2000);
    }
});
