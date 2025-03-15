<!DOCTYPE html> 
<html lang="es"> 
<head> 
    <meta charset="UTF-8"> 
    <meta name="viewport" content="width=device-width, initial-scale=1.0"> 
    <title>Agregar Vuelo</title> 
    <script> 
        function validarFormulario() { 
            let origen = document.getElementById("origen").value; 
            let destino = document.getElementById("destino").value; 
            let fecha = document.getElementById("fecha").value; 
            let plazas = document.getElementById("plazas").value; 
            let precio = document.getElementById("precio").value; 
  
            if (origen === "" || destino === "" || fecha === "" || plazas === "" || precio === "") { 
                alert("Todos los campos son obligatorios"); 
                return false; 
            } 
  
            if (parseInt(plazas) <= 0) { 
                alert("Las plazas disponibles deben ser mayores a 0"); 
                return false; 
            } 
  
            if (parseFloat(precio) <= 0) { 
                alert("El precio debe ser mayor a 0"); 
                return false; 
            } 
  
            return true; 
        } 
    </script> 
</head> 
<body> 
    <h2>Registrar Vuelo</h2> 
    <form action="procesar_vuelo.php" method="POST" onsubmit="return validarFormulario();"> 
        <label>Origen:</label> 
        <input type="text" id="origen" name="origen" required><br><br> 
  
        <label>Destino:</label> 
        <input type="text" id="destino" name="destino" required><br><br> 
  
        <label>Fecha:</label> 
        <input type="date" id="fecha" name="fecha" required><br><br> 
  
        <label>Plazas disponibles:</label> 
        <input type="number" id="plazas" name="plazas" min="1" required><br><br> 
  
        <label>Precio:</label> 
        <input type="number" id="precio" name="precio" step="0.01" min="0.01" required><br><br> 
  
        <button type="submit">Registrar Vuelo</button> 
    </form> 
</body> 
</html> 
