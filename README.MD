<!DOCTYPE html>
<html>
<head>
  <title>Bon de commande</title>
  <style>
    body {
      font-family: Arial, sans-serif;
    }
    
    .form-container {
      max-width: 500px;
      margin: 0 auto;
    }
    
    .form-row {
      margin-bottom: 20px;
    }
    
    .form-label {
      display: inline-block;
      width: 150px;
      font-weight: bold;
    }
    
    .form-input {
      width: 250px;
      padding: 5px;
    }
    
    .form-submit {
      margin-top: 20px;
    }
    
    .form-total {
      font-weight: bold;
    }
  </style>
  
  <script>
    function calculateTotal() {
      var patchPrice = 9;
      var patchCount = parseInt(document.getElementById('nombre-patch').value);
      var totalPrice = patchPrice * patchCount;
      
      document.getElementById('total-price').textContent = totalPrice + " €";
    }
  </script>
</head>
<body>
  <div class="form-container">
    <h2>Bon de commande</h2>
    
    <form onsubmit="event.preventDefault(); calculateTotal();">
      <div class="form-row">
        <label class="form-label" for="nom-commandant">Nom du commandant:</label>
        <input class="form-input" type="text" id="nom-commandant" name="nom-commandant" required>
      </div>
      
      <div class="form-row">
        <label class="form-label" for="nombre-patch">Nombre de patch:</label>
        <input class="form-input" type="number" id="nombre-patch" name="nombre-patch" required onchange="calculateTotal();">
      </div>
      
      <div class="form-row">
        <label class="form-label" for="adresse-postale">Adresse postale:</label>
        <textarea class="form-input" id="adresse-postale" name="adresse-postale" required></textarea>
      </div>
      
      <div class="form-row">
        <label class="form-label">Prix unitaire:</label>
        <span class="form-input">9 €</span>
      </div>
      
      <div class="form-row">
        <label class="form-label">Prix total:</label>
        <span class="form-input form-total" id="total-price">0 €</span>
      </div>
      
      <div class="form-submit">
        <p>Merci de faire un screen de la page et la poster en MP sur Discord. Merci :)</p>
      </div>
    </form>
  </div>
</body>
</html>
