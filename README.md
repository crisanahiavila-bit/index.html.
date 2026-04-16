<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<title>CONALEP 109</title>

<style>
body {
    margin: 0;
    font-family: 'Segoe UI', sans-serif;
    background: linear-gradient(135deg, #667eea, #764ba2);
    height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
}

/* Caja tipo glass */
.box {
    backdrop-filter: blur(15px);
    background: rgba(255, 255, 255, 0.15);
    padding: 30px;
    border-radius: 25px;
    width: 320px;
    text-align: center;
    color: white;
    box-shadow: 0 10px 30px rgba(0,0,0,0.3);
}

h2 {
    margin-bottom: 5px;
    font-size: 24px;
}

p {
    margin-bottom: 20px;
    opacity: 0.8;
}

input {
    width: 90%;
    padding: 12px;
    margin: 8px 0;
    border-radius: 12px;
    border: none;
    outline: none;
    font-size: 14px;
}

/* Botón */
button {
    width: 95%;
    padding: 12px;
    border: none;
    border-radius: 30px;
    background: linear-gradient(135deg, #00c6ff, #0072ff);
    color: white;
    font-size: 16px;
    font-weight: bold;
    cursor: pointer;
    margin-top: 10px;
    transition: 0.3s;
}

button:hover {
    transform: scale(1.07);
}

/* Resultado */
#resultado {
    margin-top: 20px;
    font-weight: bold;
    font-size: 15px;
}
</style>
</head>

<body>

<div class="box">
    <h2>🎓 CONALEP 109</h2>
    <p>Cálculo de alumnos</p>

    <input type="number" id="inscritos" placeholder="Total inscritos">
    <input type="number" id="reprobados" placeholder="Reprobados">

    <button onclick="calcular()">Calcular</button>

    <div id="resultado"></div>
</div>

<script>
function calcular() {
    let inscritos = parseInt(document.getElementById("inscritos").value);
    let reprobados = parseInt(document.getElementById("reprobados").value);

    if (inscritos <= 0 || reprobados < 0 || reprobados > inscritos) {
        document.getElementById("resultado").innerText = "⚠️ Datos inválidos";
        return;
    }

    let indice = (reprobados / inscritos) * 100;

    document.getElementById("resultado").innerText =
        "📊 Total: " + inscritos +
        " | Reprobación: " + indice.toFixed(2) + "%";
}
</script>

</body>
</html>
