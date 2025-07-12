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
