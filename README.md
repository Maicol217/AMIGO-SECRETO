# AMIGO-SECRETO

<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Amigo Secreto</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <div class="container">
        <h1>Juego de Amigo Secreto</h1>
        <button onclick="seleccionarAmigo()">Seleccionar Amigo Secreto</button>
        <p id="mensaje"></p>
        <h3>Lista de Participantes:</h3>
        <ul id="listaNombres"></ul>
    </div>
    <script src="script.js"></script>
</body>
</html>
body {
    font-family: Arial, sans-serif;
    text-align: center;
    background-color: #f8f9fa;
}

.container {
    margin-top: 50px;
    padding: 20px;
    background: white;
    border-radius: 10px;
    box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.1);
    display: inline-block;
}

button {
    padding: 10px 15px;
    margin: 10px;
    cursor: pointer;
    background-color: #007bff;
    color: white;
    border: none;
    border-radius: 5px;
}

button:hover {
    background-color: #0056b3;
}

p {
    font-size: 18px;
    font-weight: bold;
    color: red;
}

ul {
    list-style: none;
    padding: 0;
}

li {
    font-size: 18px;
    margin: 5px 0;
}
// Lista predefinida de participantes
let nombres = ["Michael", "Nicole", "Margarita", "Michelle", "Patricia", "José", "Andrea", "Alfredo"];

// Mostrar los nombres en la lista al cargar la página
document.addEventListener("DOMContentLoaded", actualizarLista);

function seleccionarAmigo() {
    if (nombres.length === 0) {
        document.getElementById("mensaje").innerText = "No hay participantes.";
        return;
    }
    
    let indiceAleatorio = Math.floor(Math.random() * nombres.length);
    let amigoSecreto = nombres[indiceAleatorio];

    document.getElementById("mensaje").innerText = "🎉 El amigo secreto es: " + amigoSecreto + " 🎉";
}

function actualizarLista() {
    let lista = document.getElementById("listaNombres");
    lista.innerHTML = "";
    nombres.forEach(nombre => {
        let item = document.createElement("li");
        item.innerText = nombre;
        lista.appendChild(item);
    });
}