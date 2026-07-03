<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <title>MiBiblioteca</title>
    <link rel="stylesheet" href="css/style.css">
</head>

<body>

<header>
    <h1>📚 MiBiblioteca</h1>
    <p>Organizá tus libros favoritos</p>
</header>

<main>

<form onsubmit="return guardarLibro()">

    <input
        type="text"
        id="titulo"
        placeholder="Título del libro">

    <input
        type="text"
        id="autor"
        placeholder="Autor">

    <select id="genero">
        <option>Novela</option>
        <option>Historia</option>
        <option>Ciencia ficción</option>
    </select>

    <input
        type="submit"
        value="Guardar libro">

</form>

<button onclick="mostrarLibros()">
    Ver recomendaciones
</button>

<div id="mensaje"></div>

<div id="libros"></div>

<footer>
    MiBiblioteca 2026
</footer>

</main>

<script src="js/script.js"></script>

</body>
</html>







































let titulo;
let libros = [];
let contenido = "";

function guardarLibro(){

    titulo = document.getElementById("titulo").value.trim();

    if(titulo == ""){
        document.getElementById("mensaje").innerHTML = "Debe ingresar el título.";
        return false;
    }

    libros.push(titulo);

    document.getElementById("mensaje").innerHTML =
    "Libro registrado correctamente.";

    return false;
}

function mostrarLibros(){

    libros = [];

    libros.push("📘 El Principito");
    libros.push("📗 Don Quijote");
    libros.push("📙 Cien años de soledad");

    contenido = "";

    for(let i = 0; i < libros.length; i++){

        contenido += "<div class='card'>";
        contenido += "<h3>";
        contenido += libros[i];
        contenido += "</h3>";
        contenido += "</div>";
    }

    contenido += "<p><strong>Cantidad de libros: "
              + libros.length +
              "</strong></p>";

    document.getElementById("libros").innerHTML = contenido;
}
