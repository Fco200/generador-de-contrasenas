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
body {
    font-family: Arial, sans-serif;
    text-align: center;
    margin-top: 50px;
}

label, input, select {
    margin: 10px 0;
}

button {
    margin-top: 20px;
    padding: 10px 20px;
    background-color: #4CAF50;
    color: white;
    border: none;
    cursor: pointer;
}

button:hover {
    background-color: #45a049;
}
function generatePassword() {
    const length = document.getElementById("length").value;
    const structure = document.getElementById("structure").value;

    let characters = "";
    switch (parseInt(structure)) {
        case 1:
            characters = "abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ";
            break;
        case 2:
            characters = "abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ0123456789";
            break;
        case 3:
            characters = "abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ0123456789!@#$%^&*()-_=+[]{}|;:'\",.<>?/`~";
            break;
        default:
            alert("Opción no válida.");
            return;
    }

    let password = "";
    for (let i = 0; i < length; i++) {
        const index = Math.floor(Math.random() * characters.length);
        password += characters.charAt(index);
    }

    document.getElementById("password").textContent = "Contraseña generada: " + password;
}

    
