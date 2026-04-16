<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<title>Cálculo CONALEP</title>
<style>
    body { font-family: Arial; text-align: center; background: #f4f4f4; }
    .box { background: white; padding: 20px; margin: auto; width: 300px; border-radius: 10px; }
    input, button { margin: 10px; padding: 10px; width: 80%; }
</style>
</head>
<body>

<div class="box">
    <h2>CONALEP 109</h2>
    <p>Cálculo de alumnos</p>

    <input type="number" id="inscritos" placeholder="Total inscritos">
    <input type="number" id="reprobados" placeholder="Reprobados">

    <button onclick="calcular()">Calcular</button>

    <p id="resultado"></p>
</div>

<script>
function calcular() {
    let inscritos = parseInt(document.getElementById("inscritos").value);
    let reprobados = parseInt(document.getElementById("reprobados").value);

    if (inscritos <= 0 || reprobados < 0 || reprobados > inscritos) {
        document.getElementById("resultado").innerText = "Datos inválidos";
        return;
    }

    let indice = (reprobados / inscritos) * 100;

    document.getElementById("resultado").innerText =
        "Total: " + inscritos + 
        " | Índice de reprobación: " + indice.toFixed(2) + "%";
}
</script>

</body>
</html>
        
