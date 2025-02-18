# generador-de-contrasenas
genera contraseñas aleatorias
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Generador de Contraseñas</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <h1>Generador de Contraseñas</h1>
    <label for="length">Longitud de la contraseña:</label>
    <input type="number" id="length" name="length" min="1" required>
    <br>
    <label for="structure">Estructura de la contraseña:</label>
    <select id="structure" name="structure">
        <option value="1">Solo letras</option>
        <option value="2">Letras y números</option>
        <option value="3">Letras, números y caracteres especiales</option>
    </select>
    <br>
    <button onclick="generatePassword()">Generar Contraseña</button>
    <p id="password"></p>
    <script src="script.js"></script>
</body>
</html>
    
