<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta name="robots" content="noindex, nofollow">
  <title>Una Sorpresa Especial</title>
  <style>
    * { box-sizing: border-box; margin: 0; padding: 0; }
    body {
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
      background-color: #1a1a2e;
      color: #ffffff;
      min-height: 100vh;
      display: flex;
      justify-content: center;
      align-items: center;
    }
    #lock-screen {
      position: fixed; top: 0; left: 0; width: 100%; height: 100%;
      background-color: #16213e; display: flex; justify-content: center;
      align-items: center; z-index: 100;
    }
    .card {
      background: #0f3460; padding: 2.5rem; border-radius: 16px;
      box-shadow: 0 8px 32px rgba(0, 0, 0, 0.4); text-align: center;
      max-width: 400px; width: 90%;
    }
    h2 { margin-bottom: 1rem; color: #e94560; }
    p { margin-bottom: 1.5rem; color: #cbd5e1; }
    input[type="password"] {
      width: 100%; padding: 12px; margin-bottom: 1rem;
      border: 2px solid #e94560; border-radius: 8px; background: #1a1a2e;
      color: #ffffff; font-size: 1rem; text-align: center; outline: none;
    }
    button {
      width: 100%; padding: 12px; background-color: #e94560; color: white;
      border: none; border-radius: 8px; font-size: 1rem; font-weight: bold;
      cursor: pointer; transition: background 0.2s;
    }
    button:hover { background-color: #ff6b81; }
    #error-msg { color: #ff4757; margin-top: 1rem; font-size: 0.9rem; display: none; }
    #content { display: none; width: 90%; max-width: 600px; margin: 2rem auto; text-align: center; }
    .content-card { background: #0f3460; padding: 2rem; border-radius: 16px; box-shadow: 0 8px 32px rgba(0,0,0,0.4); }
    
    /* Polaroid Style */
    .polaroid-container { display: flex; justify-content: center; gap: 15px; flex-wrap: wrap; margin-top: 20px; }
    .polaroid { background: white; padding: 10px 10px 20px 10px; box-shadow: 0 4px 10px rgba(0,0,0,0.3); transform: rotate(-3deg); max-width: 200px; color: #333; }
    .caption { font-family: sans-serif; margin-top: 10px; font-size: 0.9rem; }
  </style>
</head>
<body>

  <!-- LOCK SCREEN -->
  <div id="lock-screen">
    <div class="card">
      <h2>Acceso Secreto 🔒</h2>
      <p>Ingresa la contraseña secreta:</p>
      <input type="password" id="password-input" placeholder="Escribe aquí..." autofocus>
      <button onclick="checkPassword()">Desbloquear</button>
      <p id="error-msg">¡Código incorrecto, intenta de nuevo!</p>
    </div>
  </div>

  <!-- HIDDEN CONTENT -->
  <div id="content">
    <div class="content-card">
      <h1>¡Feliz Cumpleaños! 🎉💖</h1>
      <p style="margin-top: 10px;">¡Lograste entrar!</p>
      
      <div class="polaroid-container">
        <div class="polaroid">
          <p class="caption">Nuestra primera cita ☕</p>
        </div>
      </div>
    </div>
  </div>

  <script>
    // CHANGE YOUR PASSWORD HERE
    const SECRET_PASSWORD = "1234";

    function checkPassword() {
      const input = document.getElementById("password-input").value;
      const errorMsg = document.getElementById("error-msg");
      const lockScreen = document.getElementById("lock-screen");
      const content = document.getElementById("content");

      if (input === SECRET_PASSWORD) {
        lockScreen.style.display = "none";
        content.style.display = "block";
      } else {
        errorMsg.style.display = "block";
        document.getElementById("password-input").value = "";
      }
    }

    document.getElementById("password-input").addEventListener("keypress", function(event) {
      if (event.key === "Enter") {
        checkPassword();
      }
    });
  </script>
</body>
</html>
