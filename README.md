

✅ ¿Qué incluye?
1. index.html
Interfaz principal con controles y visualización:

html
Copiar
Editar
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <title>Control de Temperatura Ambiental</title>
    <link rel="stylesheet" href="styles.css">
    <script src="https://code.jquery.com/jquery-3.6.0.min.js"></script>
</head>
<body>
    <div class="container">
        <h1>Control de Temperatura Ambiental</h1>
        <p>Temperatura actual: <span id="temperature">25</span>°C</p>
        <div class="slider-container">
            <input type="range" id="tempSlider" min="16" max="40" value="25">
        </div>
        <button id="coolBtn">Activar Enfriamiento</button>
        <div class="status">
            <p>Estado del sistema: <span id="status">En espera</span></p>
        </div>
        <div class="patents">
            <h2>Patentes Relacionadas</h2>
            <img src="patente1.jpg" alt="Patente 1">
            <img src="patente2.jpg" alt="Patente 2">
        </div>
    </div>
    <script src="script.js"></script>
</body>
</html>
2. styles.css
Diseño moderno y adaptativo:

css
Copiar
Editar
body {
    font-family: Arial, sans-serif;
    background: linear-gradient(to right, #2c3e50, #3498db);
    color: white;
    margin: 0;
    padding: 0;
}
.container {
    max-width: 600px;
    margin: 50px auto;
    background: rgba(0, 0, 0, 0.3);
    padding: 20px;
    border-radius: 15px;
    box-shadow: 0 0 10px #000;
}
h1, h2 {
    text-align: center;
}
.slider-container {
    margin: 20px 0;
    text-align: center;
}
input[type="range"] {
    width: 100%;
}
button {
    display: block;
    width: 100%;
    padding: 15px;
    font-size: 18px;
    background-color: #1abc9c;
    border: none;
    border-radius: 10px;
    color: white;
    cursor: pointer;
}
button:hover {
    background-color: #16a085;
}
.status {
    margin-top: 20px;
    text-align: center;
}
.patents {
    margin-top: 30px;
    text-align: center;
}
.patents img {
    width: 45%;
    margin: 5px;
    border: 2px solid white;
    border-radius: 10px;
}
3. script.js
Lógica de enfriamiento automática con jQuery:

javascript
Copiar
Editar
$(document).ready(function () {
    $('#tempSlider').on('input', function () {
        $('#temperature').text($(this).val());
        $('#status').text('En espera');
    });

    $('#coolBtn').click(function () {
        let temp = parseInt($('#temperature').text());
        if (temp > 22) {
            $('#status').text('Enfriando...');
            let interval = setInterval(() => {
                temp--;
                $('#temperature').text(temp);
                if (temp <= 22) {
                    $('#status').text('Temperatura óptima alcanzada');
                    clearInterval(interval);
                }
            }, 500);
        } else {
            $('#status').text('La temperatura ya es óptima');
        }
    });
});
