<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>Coffe ¡Guauu!</title>
  <style>
    @import url('https://fonts.googleapis.com/css2?family=Fredoka:wght@500&display=swap');

    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      font-family: 'Fredoka', sans-serif;
      background-color: #fffaf4;
      color: #333;
      scroll-behavior: smooth;
      animation: fadeIn 1s ease;
    }

    @keyframes fadeIn {
      from { opacity: 0; }
      to { opacity: 1; }
    }

    header {
      background-image: url('https://i.imgur.com/vDkFpJ1.jpg');
      background-size: cover;
      background-position: center;
      color: white;
      text-align: center;
      padding: 100px 20px;
    }

    header h1 {
      font-size: 3em;
      text-shadow: 2px 2px 4px rgba(0,0,0,0.5);
    }

    nav {
      background-color: #ffb74d;
      display: flex;
      justify-content: center;
      padding: 10px;
      position: sticky;
      top: 0;
      z-index: 100;
    }

    nav a {
      margin: 0 15px;
      color: white;
      text-decoration: none;
      font-weight: bold;
      transition: color 0.3s;
    }

    nav a:hover {
      color: #5d4037;
    }

    section {
      padding: 60px 20px;
      max-width: 1100px;
      margin: auto;
    }

    h2 {
      color: #5d4037;
      margin-bottom: 20px;
      text-align: center;
    }

    .menu-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
      gap: 25px;
      margin-top: 30px;
    }

    .menu-item {
      background: #fff8e1;
      border-radius: 15px;
      overflow: hidden;
      box-shadow: 0 4px 8px rgba(0,0,0,0.1);
      transition: transform 0.3s;
      animation: fadeIn 1.2s ease;
    }

    .menu-item:hover {
      transform: translateY(-5px);
    }

    .menu-item img {
      width: 100%;
      height: 170px;
      object-fit: cover;
    }

    .menu-item div {
      padding: 15px;
    }

    footer {
      background-color: #6d4c41;
      color: white;
      text-align: center;
      padding: 20px;
      margin-top: 50px;
    }

    .nosotros, .contacto {
      text-align: center;
    }

    .contacto p {
      margin: 10px 0;
    }
  </style>
</head>
<body>

  <header>
    <h1>🐶 Coffe ¡Guauu!</h1>
    <p>Donde el café y las mascotas se encuentran</p>
  </header>

  <nav>
    <a href="#bienvenida">Inicio</a>
    <a href="#menu">Menú</a>
    <a href="#nosotros">Nosotros</a>
    <a href="#contacto">Contacto</a>
  </nav>

  <section id="bienvenida">
    <h2>Bienvenidos</h2>
    <p style="text-align:center;">En Coffe ¡Guauu! celebramos el amor por el café y por los animales. Nuestra cafetería pet-friendly te espera con un ambiente único, productos de calidad y espacio para que tu lomito disfrute contigo.</p>
  </section>

  <section id="menu">
    <h2>☕ Menú Destacado</h2>
    <div class="menu-grid">
      <div class="menu-item">
        <img src="https://i.imgur.com/34vYwba.jpg" alt="Latte de Avellana">
        <div>
          <h3>Latte de Avellana</h3>
          <p>$55 MXN</p>
        </div>
      </div>
      <div class="menu-item">
        <img src="https://i.imgur.com/I4tz1jb.jpg" alt="Sándwich Capresse">
        <div>
          <h3>Sándwich Capresse</h3>
          <p>$75 MXN</p>
        </div>
      </div>
      <div class="menu-item">
        <img src="https://i.imgur.com/3VxTxTh.jpg" alt="Galleta para Perros">
        <div>
          <h3>Galletas para Perros</h3>
          <p>$20 MXN</p>
        </div>
      </div>
      <div class="menu-item">
        <img src="https://i.imgur.com/Bf8nEZc.jpg" alt="Frappé Mocha">
        <div>
          <h3>Frappé Mocha</h3>
          <p>$65 MXN</p>
        </div>
      </div>
    </div>
  </section>

  <section id="nosotros" class="nosotros">
    <h2>🐾 Sobre Nosotros</h2>
    <p>Somos amantes del café y de los peluditos. Nuestra misión es crear un espacio donde humanos y mascotas convivan mientras disfrutan de bebidas artesanales, comida deliciosa y productos especializados. Estamos ubicados en una de las zonas más activas de la CDMX, cerca del IPN.</p>
  </section>

  <section id="contacto" class="contacto">
    <h2>📍 Contáctanos</h2>
    <p>📌 Av. Instituto Politécnico Nacional, CDMX</p>
    <p>📞 Tel: 55 5493 6361</p>
    <p>📞 Tel: 55 3233 1624</p>
    <p>📧 Correo: llanjo030@gmail,com</p>
    <p>📸 Instagram: <strong>@coffeeguauu</strong></p>
  </section>

  <footer>
    <p>&copy; 2025 Coffe ¡Guauu! - Todos los derechos reservados</p>
  </footer>

</body>
</html>
