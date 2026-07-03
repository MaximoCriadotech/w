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
