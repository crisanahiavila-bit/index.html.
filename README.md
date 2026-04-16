<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<title>CONALEP 109</title>

<style>
    body {
        font-family: 'Segoe UI', sans-serif;
        background: linear-gradient(135deg, #a8edea, #fed6e3);
        display: flex;
        justify-content: center;
        align-items: center;
        height: 100vh;
        margin: 0;
    }

    .box {
        background: white;
        padding: 30px;
        border-radius: 20px;
        width: 320px;
        text-align: center;
        box-shadow: 0 10px 30px rgba(0,0,0,0.2);
    }

    h2 {
        margin-bottom: 5px;
    }

    p {
        color: #666;
        margin-bottom: 20px;
    }

    input {
        width: 90%;
        padding: 10px;
        margin: 8px 0;
        border-radius: 10px;
        border: 1px solid #ccc;
        outline: none;
        font-size: 14px;
    }

    input:focus {
        border-color: #a8edea;
    }

    button {
        width: 95%;
        padding: 12px;
        border: none;
        border-radius: 25px;
        background: linear-gradient(135deg, #667eea, #764ba2);
        color: white;
        font-size: 16px;
        font-weight: bold;
        cursor: pointer;
        margin-top: 10px;
        transition: 0.3s;
    }

    button:hover {
        transform: scale(1.05);
    }

    #resultado {
        margin-top: 20px;
        font-weight: bold;
        color: #333;
    }
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
