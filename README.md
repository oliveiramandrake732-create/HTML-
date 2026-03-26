# HTML-
Palmeira-robusta?
DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <title>Calculadora de Troco</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: #f4f4f4;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
    }
    .calculadora {
      background: #fff;
      padding: 20px;
      border-radius: 10px;
      box-shadow: 0 0 10px rgba(0,0,0,0.2);
      width: 300px;
    }
    input, button {
      width: 100%;
      padding: 10px;
      margin: 5px 0;
      font-size: 16px;
    }
    button {
      background: #007BFF;
      color: #fff;
      border: none;
      cursor: pointer;
      border-radius: 5px;
    }
    button:hover {
      background: #0056b3;
    }
    .resultado {
      margin-top: 10px;
      font-weight: bold;
      color: #333;
    }
  </style>
</head>
<body>
  <div class="calculadora">
    <h2>Calculadora de Troco</h2>
    <input type="number" id="valorCompra" placeholder="Valor da compra (R$)">
    <input type="number" id="valorPago" placeholder="Valor pago (R$)">
    <button onclick="calcularTroco()">Calcular Troco</button>
    
    <div class="resultado" id="resultado"></div>
  </div>

  <script>
    function calcularTroco() {
      let compra = parseFloat(document.getElementById("valorCompra").value);
      let pago = parseFloat(document.getElementById("valorPago").value);

      if (isNaN(compra) || isNaN(pago)) {
        document.getElementById("resultado").innerText = "Por favor, insira valores válidos.";
        return;
      }

      if (pago < compra) {
        document.getElementById("resultado").innerText = "Valor pago insuficiente! Falta R$ " + (compra - pago).toFixed(2);
      } else if (pago === compra) {
        document.getElementById("resultado").innerText = "Pagamento exato, não há troco.";
      } else {
        let troco = pago - compra;
        document.getElementById("resultado").innerText = "Troco: R$ " + troco.toFixed(2);
      }
    }
  </script>
</body>
</html>
