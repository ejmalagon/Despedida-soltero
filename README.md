<html lang="es">
<head>
  <meta charset="UTF-8">
  <title>Despedida de soltero 🎉</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0">

  <style>
<script type="module">
  // Importar Firebase
  import { initializeApp } from "https://www.gstatic.com/firebasejs/10.7.1/firebase-app.js";
  import { getFirestore, collection, getDocs, doc, updateDoc } from "https://www.gstatic.com/firebasejs/10.7.1/firebase-firestore.js";

  // CONFIGURACIÓN (PEGA AQUÍ LA TUYA)
      apiKey: "AIzaSyBBJwB7goplMb2WJpBvJU5rsvoueD84glg",
  authDomain: "despedida-ba71a.firebaseapp.com",
  databaseURL: "https://despedida-ba71a-default-rtdb.firebaseio.com",
  projectId: "despedida-ba71a",
  storageBucket: "despedida-ba71a.firebasestorage.app",
  messagingSenderId: "30414791076",
  appId: "1:30414791076:web:08d0d7494477ca5f912131",
  measurementId: "G-GY9J0H7BW8"
  };

  const app = initializeApp(firebaseConfig);
  const db = getFirestore(app);
</script>


    
    
    
    body {
      font-family: Arial, sans-serif;
      background-color: #f5f5f5;
      margin: 0;
      padding: 0;
      text-align: center;
    }

    header {
      background-color: #222;
      color: white;
      padding: 20px;
    }

    header h1 {
      margin: 0;
    }

    .container {
      max-width: 800px;
      margin: auto;
      padding: 20px;
    }

    .foto {
      margin: 20px 0;
    }

    .foto img {
      max-width: 100%;
      border-radius: 10px;
    }

    .regalos {
      list-style: none;
      padding: 0;
    }

    .regalo {
      background-color: white;
      margin: 10px 0;
      padding: 15px;
      border-radius: 8px;
      display: flex;
      justify-content: space-between;
      align-items: center;
    }

    .regalo.reservado {
      background-color: #ddd;
    }

    button {
      padding: 8px 12px;
      border: none;
      border-radius: 5px;
      cursor: pointer;
      background-color: #007bff;
      color: white;
    }

    button:disabled {
      background-color: #999;
      cursor: not-allowed;
    }

    footer {
      margin-top: 40px;
      color: #777;
      font-size: 0.9em;
    }
  </style>
</head>

<body>

  <header>
    <h1>Despedida de soltero 🎉</h1>
    <p>¡Ayúdanos a organizar los regalos!</p>
  </header>

  <div class="container">

    <div class="foto">
      <!-- Cambia la ruta de la imagen -->
      <img src="foto-amigos.png" alt="Los futuros esposos">
    </div>

    <p>
      Selecciona un regalo de la lista para evitar que se repita.
      Una vez elegido, quedará marcado con tu nombre.
    </p>

    <ul class="regalos" id="listaRegalos">

      <li class="regalo" data-id="1">
        <span>🥃 Botella de whisky</span>
        <button onclick="reservar(this)">Elegir</button>
      </li>

      <li class="regalo" data-id="2">
        <span>🍷 Set de copas</span>
        <button onclick="reservar(this)">Elegir</button>
      </li>

      <li class="regalo" data-id="3">
        <span>🎮 Videojuego</span>
        <button onclick="reservar(this)">Elegir</button>
      </li>

      <li class="regalo" data-id="4">
        <span>🕶️ Gafas de sol</span>
        <button onclick="reservar(this)">Elegir</button>
      </li>

    </ul>

  </div>

  <footer>
    Hecho con cariño para la despedida 🍻
  </footer>

  <script>
    function reservar(boton) {
      const nombre = prompt("¿Cuál es tu nombre?");
      if (!nombre) return;

      const regalo = boton.parentElement;
      regalo.classList.add("reservado");

      boton.disabled = true;
      boton.textContent = "Reservado";

      const texto = regalo.querySelector("span");
      texto.textContent += " — 🎁 " + nombre;
    }
  </script>

</body>
</html>

