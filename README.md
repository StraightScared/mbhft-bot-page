<form id="orderForm">
    <label>Symbol: <input name="symbol" id="symbol" /></label><br>
    <label>Amount: <input type="number" step="any" name="qty" id="qty" /></label><br>
    <button type="submit">Send Order</button>
  </form>
  
  <script src="https://telegram.org/js/telegram-web-app.js"></script>
  <script>
    const webApp = Telegram.WebApp;
    webApp.ready();
  
    document.getElementById('orderForm').addEventListener('submit', e => {
      e.preventDefault();
      webApp.sendData(JSON.stringify({
        symbol: document.getElementById('symbol').value,
        qty:    parseFloat(document.getElementById('qty').value),
      }));
    });
  </script>
  
