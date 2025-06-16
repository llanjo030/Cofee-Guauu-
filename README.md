<!DOCTYPE html>

<html lang="es">
<head>
<meta charset="utf-8"/>
<meta content="width=device-width, initial-scale=1" name="viewport"/>
<meta content="Café pet-friendly en CDMX. Disfruta bebidas y comida con tu lomito en Café ¡Guauu!." name="description"/>
<title>Café ¡Guauu!</title>
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
      background-image: url('https://i.postimg.cc/4d85tq1t/cafe-s-de-gatos-cdmx.jpg');
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
  
  .slider {
    max-width: 800px;
    margin: 30px auto;
    overflow: hidden;
    border-radius: 12px;
    box-shadow: 0 4px 10px rgba(0,0,0,0.2);
  }
  .slides {
    display: flex;
    width: 300%;
    animation: slide 12s infinite;
  }
  .slides img {
    width: 100%;
    object-fit: cover;
  }
  @keyframes slide {
    0%   { transform: translateX(0%); }
    33%  { transform: translateX(-100%); }
    66%  { transform: translateX(-200%); }
    100% { transform: translateX(0%); }
  }


  body.dark-mode {
    background-color: #1e1e1e;
    color: #eee;
  }
  body.dark-mode header,
  body.dark-mode nav,
  body.dark-mode footer,
  body.dark-mode section {
    background-color: #2c2c2c !important;
    color: #eee !important;
  }
  body.dark-mode nav a:hover {
    color: #ffb74d;
  }
  .dark-toggle {
    position: fixed;
    top: 20px;
    right: 20px;
    background-color: #333;
    color: #fff;
    padding: 8px 12px;
    border: none;
    border-radius: 6px;
    cursor: pointer;
    z-index: 1001;
  }

</style>
</head>
<body>
<header>
<h1>🐶 Café ¡Guauu!</h1>
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
<p style="text-align:center;">En Café ¡Guauu! celebramos el amor por el café y por los animales. Nuestra cafetería pet-friendly te espera con un ambiente único, productos de calidad y espacio para que tu lomito disfrute contigo.</p>
</section>

<div style="text-align:center; margin-bottom: 40px;">
<label for="filtro-menu" style="font-weight:bold; font-size: 1.2em;">Filtrar por categoría:</label>
<select id="filtro-menu" onchange="filtrarMenu()" style="padding: 8px 12px; margin-left: 10px; font-size: 1em; border-radius: 6px;">
<option value="todo">Mostrar todo</option>
<option value="Café">Café</option>
<option value="Bebidas">Bebidas</option>
<option value="Postres">Postres</option>
<option value="Meriendas">Meriendas</option>
<option value="Snacks para mascotas">Snacks para mascotas</option>
<option value="Combos">Combos</option>
</select>
</div>
<script>
function filtrarMenu() {
  const seleccion = document.getElementById("filtro-menu").value;
  const secciones = document.querySelectorAll("#menu h3");
  secciones.forEach(sec => {
    const contenedor = sec.nextElementSibling;
    if (!contenedor || !contenedor.classList.contains("menu-grid")) return;
    const titulo = sec.textContent.replace("🍽 ", "").trim();
    if (seleccion === "todo" || seleccion === titulo) {
      sec.style.display = "block";
      contenedor.style.display = "grid";
    } else {
      sec.style.display = "none";
      contenedor.style.display = "none";
    }
  });
}
</script>
<section id="menu">
<h2>☕ Menú Destacado</h2>
<div class="menu-grid">
<div class="menu-item">
<img alt="Taza de Latte de Avellana" loading="lazy" src="https://i.postimg.cc/6qJQH5zN/cafe-latte-con-avellana.jpg"/>
<div>
<h3>Latte de Avellana</h3>
<p>$55 MXN</p>
</div>
</div>
<div class="menu-item">
<img alt="Sándwich Capresse con pan artesanal" loading="lazy" src="https://i.postimg.cc/zXNBKvVC/d30e03105253-sandwich-caprese-adob-t.jpg"/>
<div>
<h3>Sándwich Capresse</h3>
<p>$75 MXN</p>
</div>
</div>
<div class="menu-item">
<img alt="Galletas especiales para perros" loading="lazy" src="https://i.postimg.cc/fWmyVmTW/galletas-caseras-para-perros-800x1067.jpg"/>
<div>
<h3>Galletas para Perros</h3>
<p>$20 MXN</p>
</div>
</div>
<div class="menu-item">
<img alt="Frappé Mocha frío servido en vaso alto" loading="lazy" src="https://i.postimg.cc/rFyTqrDP/55-MOCHA-FRAPPE-3-4-03-Retouch.png"/>
<div>
<h3>Frappé Mocha</h3>
<p>$65 MXN</p>
</div>
</div>
</div>
<h3 style="text-align:center; margin-top:50px; color:#5d4037;">🍽 Café</h3><div class="menu-grid">
<div class="menu-item">
<div>
<h3>Espresso sencillo</h3>
<p>Intenso, para puristas</p>
<p><strong>Mediano: $35 Grande: $45 Jumbo: $55</strong></p>
</div>
</div>
<div class="menu-item">
<div>
<h3>Americano</h3>
<p>Ligero, el clásico diario</p>
<p><strong>Mediano: $38 Grande: $48 Jumbo: $58</strong></p>
</div>
</div>
<div class="menu-item">
<div>
<h3>Latte clásico</h3>
<p>Suave y equilibrado</p>
<p><strong>Mediano: $45 Grande: $55 Jumbo: $65</strong></p>
</div>
</div>
<div class="menu-item">
<div>
<h3>Cappuccino</h3>
<p>Espuma rica y textura cremosa</p>
<p><strong>Mediano: $48 Grande: $58 Jumbo: $68</strong></p>
</div>
</div>
<div class="menu-item">
<div>
<h3>Mocha Guauu</h3>
<p>Café + chocolate, perfecto para dulceros</p>
<p><strong>Mediano: $55 Grande: $65 Jumbo: $75</strong></p>
</div>
</div>
<div class="menu-item">
<div>
<h3>Caramel Macchiato</h3>
<p>Vainilla, leche vaporizada y caramelo</p>
<p><strong>Mediano: $58 Grande: $68 Jumbo: $78</strong></p>
</div>
</div>
<div class="menu-item">
<div>
<h3>Latte de temporada</h3>
<p>Sabores especiales: calabaza, vainilla, maple</p>
<p><strong>Mediano: $65 Grande: $75 Jumbo: $85</strong></p>
</div>
</div>
<div class="menu-item">
<div>
<h3>Cold Brew premium</h3>
<p>Café filtrado en frío por 12h</p>
<p><strong>Mediano: $70 Grande: $80 Jumbo: $90</strong></p>
</div>
</div>
<div class="menu-item">
<div>
<h3>Affogato (café con helado)</h3>
<p>Espresso sobre bola de helado</p>
<p><strong>Mediano: $70 Grande: $80 Jumbo: $90</strong></p>
</div>
</div>
<div class="menu-item">
<div>
<h3>Flat White</h3>
<p>Espresso doble con microespuma de leche</p>
<p><strong>Mediano: $50 Grande: $60 Jumbo: $70</strong></p>
</div>
</div>
<div class="menu-item">
<div>
<h3>Latte con leche vegetal</h3>
<p>Almendra, avena o coco (elige una)</p>
<p><strong>Mediano: $60 Grande: $70 Jumbo: $80</strong></p>
</div>
</div>
<div class="menu-item">
<div>
<h3>Espresso doble</h3>
<p>Dosis fuerte de energía</p>
<p><strong>Mediano: $40 Grande: $50 Jumbo: $60</strong></p>
</div>
</div>
<div class="menu-item">
<div>
<h3>Vienés</h3>
<p>Café con crema batida y canela</p>
<p><strong>Mediano: $60 Grande: $70 Jumbo: $80</strong></p>
</div>
</div>
<div class="menu-item">
<div>
<h3>Cortado</h3>
<p>Espresso con un toque de leche</p>
<p><strong>Mediano: $38 Grande: $48 Jumbo: $58</strong></p>
</div>
</div>
<div class="menu-item">
<div>
<h3>Latte con miel y canela</h3>
<p>Aromático y reconfortante</p>
<p><strong>Mediano: $52 Grande: $62 Jumbo: $72</strong></p>
</div>
</div>
<div class="menu-item">
<div>
<h3>Café de olla</h3>
<p>Tradicional, con canela y piloncillo</p>
<p><strong>Mediano: $45 Grande: $55 Jumbo: $65</strong></p>
</div>
</div>
<div class="menu-item">
<div>
<h3>Chocolate caliente mexicano</h3>
<p>Hecho con cacao real y especias</p>
<p><strong>Mediano: $50 Grande: $60 Jumbo: $70</strong></p>
</div>
</div>
<div class="menu-item">
<div>
<h3>Moka blanco</h3>
<p>Espresso, leche y chocolate blanco</p>
<p><strong>Mediano: $60 Grande: $70 Jumbo: $80</strong></p>
</div>
</div>
</div><h3 style="text-align:center; margin-top:50px; color:#5d4037;">🍽 Bebidas</h3><div class="menu-grid">
<div class="menu-item">
<div>
<h3>Té helado del día</h3>
<p>Natural, con fruta real</p>
<p><strong>Mediano: $35 Grande: $45 Jumbo: $55</strong></p>
</div>
</div>
<div class="menu-item">
<div>
<h3>Limonada con menta</h3>
<p>Refrescante y sin azúcar añadida</p>
<p><strong>Mediano: $38 Grande: $48 Jumbo: $58</strong></p>
</div>
</div>
<div class="menu-item">
<div>
<h3>Chai latte</h3>
<p>Especiado, suave</p>
<p><strong>Mediano: $55 Grande: $65 Jumbo: $75</strong></p>
</div>
</div>
<div class="menu-item">
<div>
<h3>Chocolate caliente/frío</h3>
<p>Cacao mexicano, espeso</p>
<p><strong>Mediano: $50 Grande: $60 Jumbo: $70</strong></p>
</div>
</div>
<div class="menu-item">
<div>
<h3>Matcha latte</h3>
<p>Té verde japonés, con leche vegetal</p>
<p><strong>Mediano: $60 Grande: $70 Jumbo: $80</strong></p>
</div>
</div>
<div class="menu-item">
<div>
<h3>Smoothie natural</h3>
<p>Fruta 100%, sin jarabes</p>
<p><strong>Mediano: $65 Grande: $75 Jumbo: $85</strong></p>
</div>
</div>
<div class="menu-item">
<div>
<h3>Bebida especial de temporada</h3>
<p>Horchata con espresso, mango con jamaica</p>
<p><strong>Mediano: $65 Grande: $75 Jumbo: $85</strong></p>
</div>
</div>
<div class="menu-item">
<div>
<h3>Frappe clásico</h3>
<p>Café, hielo, crema batida</p>
<p><strong>Mediano: $58 Grande: $68 Jumbo: $78</strong></p>
</div>
</div>
<div class="menu-item">
<div>
<h3>Frappe sabor (chocolate, caramelo, vainilla)</h3>
<p>Personalízalo</p>
<p><strong>Mediano: $65 Grande: $75 Jumbo: $85</strong></p>
</div>
</div>
<div class="menu-item">
<div>
<h3>Limonada rosa con jamaica</h3>
<p>Natural y colorida</p>
<p><strong>Mediano: $45 Grande: $55 Jumbo: $65</strong></p>
</div>
</div>
<div class="menu-item">
<div>
<h3>Té frío con miel y limón</h3>
<p>Refrescante y saludable</p>
<p><strong>Mediano: $38 Grande: $48 Jumbo: $58</strong></p>
</div>
</div>
<div class="menu-item">
<div>
<h3>Smoothie de frutos rojos</h3>
<p>100% fruta natural</p>
<p><strong>Mediano: $65 Grande: $75 Jumbo: $85</strong></p>
</div>
</div>
<div class="menu-item">
<div>
<h3>Cold brew con leche</h3>
<p>Suave, refrescante</p>
<p><strong>Mediano: $55 Grande: $65 Jumbo: $75</strong></p>
</div>
</div>
<div class="menu-item">
<div>
<h3>Frappuccino Oreo</h3>
<p>Frappe con galletas Oreo</p>
<p><strong>Mediano: $70 Grande: $80 Jumbo: $90</strong></p>
</div>
</div>
<div class="menu-item">
<div>
<h3>Té verde frío</h3>
<p>Refrescante, ligero</p>
<p><strong>Mediano: $38 Grande: $48 Jumbo: $58</strong></p>
</div>
</div>
<div class="menu-item">
<div>
<h3>Smoothie tropical</h3>
<p>Mango, piña y coco</p>
<p><strong>Mediano: $65 Grande: $75 Jumbo: $85</strong></p>
</div>
</div>
<div class="menu-item">
<div>
<h3>Limonada con pepino y menta</h3>
<p>Muy fresca y natural</p>
<p><strong>Mediano: $40 Grande: $50 Jumbo: $60</strong></p>
</div>
</div>
</div><h3 style="text-align:center; margin-top:50px; color:#5d4037;">🍽 Postres</h3><div class="menu-grid">
<div class="menu-item">
<div>
<h3>Galletas artesanales</h3>
<p>Chispas de chocolate, avena o manzana</p>
<p><strong>Medio: $25</strong></p>
</div>
</div>
<div class="menu-item">
<div>
<h3>Muffin casero</h3>
<p>Frutos rojos, plátano o chocolate</p>
<p><strong>Medio: $38</strong></p>
</div>
</div>
<div class="menu-item">
<div>
<h3>Panqué de plátano</h3>
<p>Suave y casero, con nuez</p>
<p><strong>Medio: $40</strong></p>
</div>
</div>
<div class="menu-item">
<div>
<h3>Brownie intenso</h3>
<p>Con nuez, denso y chocolatoso</p>
<p><strong>Medio: $45</strong></p>
</div>
</div>
<div class="menu-item">
<div>
<h3>Cheesecake clásico</h3>
<p>Con coulis natural de frutos rojos</p>
<p><strong>Medio: $60</strong></p>
</div>
</div>
<div class="menu-item">
<div>
<h3>Roll de canela especial</h3>
<p>Extra glaseado, con relleno de nuez o manzana</p>
<p><strong>Medio: $55</strong></p>
</div>
</div>
<div class="menu-item">
<div>
<h3>Pastel del día (rebanada)</h3>
<p>Red velvet, zanahoria, tres leches, etc.</p>
<p><strong>Medio: $60</strong></p>
</div>
</div>
<div class="menu-item">
<div>
<h3>Postre premium: Tiramisú</h3>
<p>Hecho en casa, receta italiana</p>
<p><strong>Medio: $75</strong></p>
</div>
</div>
<div class="menu-item">
<div>
<h3>Donas artesanales (pieza)</h3>
<p>Glaseadas, chocolate o azúcar</p>
<p><strong>Medio: $35</strong></p>
</div>
</div>
<div class="menu-item">
<div>
<h3>Cupcake decorado</h3>
<p>Vainilla o chocolate, con topping colorido</p>
<p><strong>Medio: $45</strong></p>
</div>
</div>
<div class="menu-item">
<div>
<h3>Galleta rellena XL</h3>
<p>Galleta grande con centro líquido</p>
<p><strong>Medio: $50</strong></p>
</div>
</div>
<div class="menu-item">
<div>
<h3>Tarta de frutas</h3>
<p>Masa crujiente, crema pastelera y fruta fresca</p>
<p><strong>Medio: $70</strong></p>
</div>
</div>
<div class="menu-item">
<div>
<h3>Pastel de chocolate intenso</h3>
<p>Porción generosa, con cobertura extra</p>
<p><strong>Medio: $70</strong></p>
</div>
</div>
<div class="menu-item">
<div>
<h3>Panqué de limón</h3>
<p>Suave y esponjoso</p>
<p><strong>Medio: $45</strong></p>
</div>
</div>
<div class="menu-item">
<div>
<h3>Croissant de mantequilla</h3>
<p>Recién horneado</p>
<p><strong>Medio: $55</strong></p>
</div>
</div>
<div class="menu-item">
<div>
<h3>Rollito de canela</h3>
<p>Con glaseado de vainilla</p>
<p><strong>Medio: $55</strong></p>
</div>
</div>
<div class="menu-item">
<div>
<h3>Cheesecake mini</h3>
<p>Fresa o frutos rojos</p>
<p><strong>Medio: $60</strong></p>
</div>
</div>
<div class="menu-item">
<div>
<h3>Brownie con nuez</h3>
<p>Intenso y chocolatoso</p>
<p><strong>Medio: $60</strong></p>
</div>
</div>
<div class="menu-item">
<div>
<h3>Pan de muerto (de temporada)</h3>
<p>Tradicional mexicano</p>
<p><strong>Medio: $44</strong></p>
</div>
</div>
<div class="menu-item">
<div>
<h3>Muffin salado de tocino y queso</h3>
<p>Ideal para brunch</p>
<p><strong>Medio: $55</strong></p>
</div>
</div>
</div><h3 style="text-align:center; margin-top:50px; color:#5d4037;">🍽 Meriendas</h3><div class="menu-grid">
<div class="menu-item">
<div>
<h3>Sándwich mixto</h3>
<p>Pavo y queso en pan de caja artesanal</p>
<p><strong>Precio: $42</strong></p>
</div>
</div>
<div class="menu-item">
<div>
<h3>Tostada de aguacate</h3>
<p>Pan rústico, aguacate, semillas</p>
<p><strong>Precio: $48</strong></p>
</div>
</div>
<div class="menu-item">
<div>
<h3>Panini caprese</h3>
<p>Queso, jitomate, albahaca, pesto casero</p>
<p><strong>Precio: $58</strong></p>
</div>
</div>
<div class="menu-item">
<div>
<h3>Molletes clásicos</h3>
<p>Frijol, queso, pico de gallo</p>
<p><strong>Precio: $45</strong></p>
</div>
</div>
<div class="menu-item">
<div>
<h3>Wrap de pollo al chipotle</h3>
<p>Fresco, con vegetales y aderezo</p>
<p><strong>Precio: $60</strong></p>
</div>
</div>
<div class="menu-item">
<div>
<h3>Croissant relleno</h3>
<p>Jamón, queso, espinaca o versión dulce</p>
<p><strong>Precio: $55</strong></p>
</div>
</div>
<div class="menu-item">
<div>
<h3>Ensalada gourmet con nuez</h3>
<p>Con manzana, espinaca y aderezo casero</p>
<p><strong>Precio: $65</strong></p>
</div>
</div>
<div class="menu-item">
<div>
<h3>Waffles salados con pollo y miel</h3>
<p>Inspiración sureña con toque mexicano</p>
<p><strong>Precio: $70</strong></p>
</div>
</div>
<div class="menu-item">
<div>
<h3>Quiche individual</h3>
<p>Espinaca con queso o jamón con cebolla caramelizada</p>
<p><strong>Precio: $60</strong></p>
</div>
</div>
<div class="menu-item">
<div>
<h3>Empanada rellena</h3>
<p>Queso con elote o champiñón con epazote</p>
<p><strong>Precio: $40</strong></p>
</div>
</div>
<div class="menu-item">
<div>
<h3>Burrito pequeño</h3>
<p>Pollo, frijoles, arroz</p>
<p><strong>Precio: $45</strong></p>
</div>
</div>
<div class="menu-item">
<div>
<h3>Tostada de hummus</h3>
<p>Pan artesanal con hummus, jitomate y pepino</p>
<p><strong>Precio: $42</strong></p>
</div>
</div>
<div class="menu-item">
<div>
<h3>Sandwich de jamón artesanal</h3>
<p>Con queso, mostaza y pan rústico</p>
<p><strong>Precio: $55</strong></p>
</div>
</div>
<div class="menu-item">
<div>
<h3>Ensalada de pasta fría</h3>
<p>Ideal para días calurosos</p>
<p><strong>Precio: $50</strong></p>
</div>
</div>
<div class="menu-item">
<div>
<h3>Tostadas de aguacate</h3>
<p>Pan integral, aguacate, limón</p>
<p><strong>Precio: $48</strong></p>
</div>
</div>
<div class="menu-item">
<div>
<h3>Bagel con queso crema</h3>
<p>Simple pero delicioso</p>
<p><strong>Precio: $42</strong></p>
</div>
</div>
<div class="menu-item">
<div>
<h3>Molletes mini</h3>
<p>Pan, frijoles, queso y pico de gallo</p>
<p><strong>Precio: $45</strong></p>
</div>
</div>
<div class="menu-item">
<div>
<h3>Chilaquiles en vasito</h3>
<p>Porción individual, salsa verde o roja</p>
<p><strong>Precio: $50</strong></p>
</div>
</div>
</div><h3 style="text-align:center; margin-top:50px; color:#5d4037;">🍽 Snacks para mascotas</h3><div class="menu-grid">
<div class="menu-item">
<div>
<h3>Galletitas caseras (4 piezas)</h3>
<p>Manzana, avena, zanahoria</p>
<p><strong>Precio: $20</strong></p>
</div>
</div>
<div class="menu-item">
<div>
<h3>Pupcake perruno</h3>
<p>Pastelito sin azúcar, con mantequilla de maní</p>
<p><strong>Precio: $28</strong></p>
</div>
</div>
<div class="menu-item">
<div>
<h3>Paleta perruna</h3>
<p>Fruta congelada en forma de hueso</p>
<p><strong>Precio: $20</strong></p>
</div>
</div>
<div class="menu-item">
<div>
<h3>Helado para perro</h3>
<p>Yogur sin lactosa, plátano y miel</p>
<p><strong>Precio: $35</strong></p>
</div>
</div>
<div class="menu-item">
<div>
<h3>Tira de pollo deshidratado</h3>
<p>100% natural, sin sal</p>
<p><strong>Precio: $40</strong></p>
</div>
</div>
<div class="menu-item">
<div>
<h3>Snack gourmet (salmón o res)</h3>
<p>Alta proteína, presentación especial</p>
<p><strong>Precio: $50</strong></p>
</div>
</div>
<div class="menu-item">
<div>
<h3>Panecillo de avena y plátano</h3>
<p>Mini muffin suave sin azúcar</p>
<p><strong>Precio: $22</strong></p>
</div>
</div>
<div class="menu-item">
<div>
<h3>Huesitos de pollo al horno</h3>
<p>Bocadillos horneados, sin condimentos</p>
<p><strong>Precio: $28</strong></p>
</div>
</div>
<div class="menu-item">
<div>
<h3>Yogur con trozos de manzana</h3>
<p>Postre natural en vasito</p>
<p><strong>Precio: $30</strong></p>
</div>
</div>
<div class="menu-item">
<div>
<h3>Kit especial cumpleaños</h3>
<p>Pupcake + gorro + galletas decoradas</p>
<p><strong>Precio: $95</strong></p>
</div>
</div>
<div class="menu-item">
<div>
<h3>Pupcake sabor tocino</h3>
<p>Cupcake sin azúcar con saborizante natural</p>
<p><strong>Precio: $30</strong></p>
</div>
</div>
<div class="menu-item">
<div>
<h3>Galletas en forma de huesito</h3>
<p>Sabor pollo o zanahoria</p>
<p><strong>Precio: $25</strong></p>
</div>
</div>
<div class="menu-item">
<div>
<h3>Paleta helada para perro</h3>
<p>Yogur y fruta congelada</p>
<p><strong>Precio: $28</strong></p>
</div>
</div>
<div class="menu-item">
<div>
<h3>Bolitas de avena y mantequilla maní</h3>
<p>Sin azúcar ni sal</p>
<p><strong>Precio: $30</strong></p>
</div>
</div>
<div class="menu-item">
<div>
<h3>Galletas calmantes (lavanda y manzanilla)</h3>
<p>Para perros nerviosos</p>
<p><strong>Precio: $35</strong></p>
</div>
</div>
<div class="menu-item">
<div>
<h3>Canelita para gato (snack horneado)</h3>
<p>Hecho con atún y avena</p>
<p><strong>Precio: $28</strong></p>
</div>
</div>
<div class="menu-item">
<div>
<h3>Pouch de cumpleaños especial</h3>
<p>Incluye galleta, bandana y foto polaroid</p>
<p><strong>Precio: $120</strong></p>
</div>
</div>
<div class="menu-item">
<div>
<h3>Agua</h3>
<p>Botella de agua con eletrolitos para perros</p>
<p><strong>Precio: $25</strong></p>
</div>
</div>
</div><h3 style="text-align:center; margin-top:50px; color:#5d4037;">🍽 Combos</h3><div class="menu-grid">
<div class="menu-item">
<div>
<h3>Mini Guauu</h3>
<p>Café (Americano o Espresso) + Galleta artesanal (a elección: vainilla, chispas o avena) + Snack para tu lomito (galleta en forma de huesito)</p>
<p><strong>Precio: $65</strong></p>
</div>
</div>
<div class="menu-item">
<div>
<h3>Desayuno Pet-Friendly</h3>
<p>Panini (de jamón con queso o espinaca con queso) o wrap vegetariano + Café a elección (Americano, Latte o Café de olla) + Agua del día (frutas naturales o infusionada) + Pupcake para tu mascota (zanahoria o tocino)</p>
<p><strong>Precio: $100</strong></p>
</div>
</div>
<div class="menu-item">
<div>
<h3>Combo Pareja con Peludo</h3>
<p>2 cafés (cualquier bebida caliente del menú básico) + 1 pastelito a compartir (Brownie, Cheesecake o Tarta de frutas) + 2 snacks perrunos (galletas o bolitas de avena)</p>
<p><strong>Precio: $150</strong></p>
</div>
</div>
<div class="menu-item">
<div>
<h3>Tarde Dulce</h3>
<p>Chocolate caliente mexicano o Moka blanco + Muffin o rollito de canela + Galleta perruna con forma temática (huella o huesito)</p>
<p><strong>Precio: $80</strong></p>
</div>
</div>
<div class="menu-item">
<div>
<h3>Combo Premium "Guauu VIP"</h3>
<p>Café especial (Caramel Macchiato, Matcha Latte o Cold Brew Premium) + Postre gourmet (Cheesecake, Affogato o Croissant con almendras) + Snack premium para tu lomito (galleta de salmón o pastelito artesanal)</p>
<p><strong>Precio: $120</strong></p>
</div>
</div>
<div class="menu-item">
<div>
<h3>Combo Despertar Guauu</h3>
<p>Cafe Latte clasico o americano  + Donut artesanal o muffin pequeño + snack para  mascota (galletitas o pupcake pequeño)</p>
<p><strong>Precio: $80</strong></p>
</div>
</div>
<div class="menu-item">
<div>
<h3>Combo Refrescante y Snack</h3>
<p>Té frío con miel y limón o limonada rosa con jamaica + sandwich de jamón artesanal o tostada de hummus + huesitos de pollo al horno para mascota</p>
<p><strong>Precio: $95</strong></p>
</div>
</div>
<div class="menu-item">
<div>
<h3>Combo Dulce Tentación</h3>
<p>Mocha Guauu o Caramel Macchiato + brownie con nuez o cupcake decorado + yogur con trozos de manzana para mascota</p>
<p><strong>Precio: $110</strong></p>
</div>
</div>
<div class="menu-item">
<div>
<h3>Combo Anfitrión Pet Friendly</h3>
<p>Cold Brew premium o Frappe sabor (chocolate/caramelo/vainilla) + Quiche individual o empanada rellena + Kit especial cumpleaños para mascota (pupcake + galletas + gorro)</p>
<p><strong>Precio: $145</strong></p>
</div>
</div>
<div class="menu-item">
<div>
<h3>Combo Brunch Guauu</h3>
<p>Latte con miel y canela o café de olla + Molletes mini o chilaquiles en vasito + Bolitas de avena y mantequilla de maní para mascota</p>
<p><strong>Precio: $105</strong></p>
</div>
</div>
<div class="menu-item">
<div>
<h3>Combo Relax y Mimos</h3>
<p>Chocolate caliente mexicano o Matcha Latte + Croissant de mantequilla o rollito de canela + Galletas calmantes para perro (lavanda/manzanilla)</p>
<p><strong>Precio: $115</strong></p>
</div>
</div>
<div class="menu-item">
<div>
<h3>Combo Saludable y Fresco</h3>
<p>Smoothie de frutos rojos o smoothie tropical + Ensalada de pasta fría o tostadas de aguacate + Paleta helada para perro</p>
<p><strong>Precio: $110</strong></p>
</div>
</div>
</div></section>
<section class="nosotros" id="nosotros">
<h2>🐾 Sobre Nosotros</h2>
<p>Somos amantes del café y de los peluditos. Nuestra misión es crear un espacio donde humanos y mascotas convivan mientras disfrutan de bebidas artesanales, comida deliciosa y productos especializados. Estamos ubicados en una de las zonas más activas de la CDMX, cerca del IPN.</p>
</section>
<section class="contacto" id="contacto">
<h2>📍 Contáctanos</h2>
<p>📌 Av. Instituto Politécnico Nacional, CDMX</p>
<p>📞 Tel: 55 5493 6361</p>
<p>📞 Tel: 55 3233 1624</p>
<p>📧 Correo: coffeguau20412@gmail.com</p>
<p>📸 Instagram: <strong>@coffeguau</strong></p>
</section>
<footer>
<p>© 2025 Café ¡Guauu! - Todos los derechos reservados</p>
<section id="testimonios" style="background-color: #fff3e0; padding: 40px 20px;">
<h2 style="color: #5d4037; text-align: center; margin-bottom: 30px;">🗣 Opiniones</h2>
<div style="max-width: 800px; margin: auto; text-align: center;">
<blockquote style="font-style: italic; margin-bottom: 20px;">"¡Excelente atención! Mi perrita fue muy bien recibida, el café delicioso y el ambiente muy cálido."</blockquote>
<p><strong>- Andrea L.</strong></p>
<blockquote style="font-style: italic; margin: 30px 0 20px;">"Mi perro amó las galletas especiales. Muy recomendable para amantes de los animales."</blockquote>
<p><strong>- Roberto G.</strong></p>
<blockquote style="font-style: italic; margin: 30px 0 20px;">"Lugar acogedor, buena música y excelente trato para los peluditos. Volveré sin duda."</blockquote>
<p><strong>- Karina M.</strong></p>
</div>
</section>
</footer>
<a href="https://wa.me/525554936361" style="
    position: fixed;
    bottom: 20px;
    right: 20px;
    background-color: #25D366;
    color: white;
    font-size: 24px;
    padding: 12px 16px;
    border-radius: 50%;
    text-align: center;
    text-decoration: none;
    box-shadow: 0 4px 8px rgba(0,0,0,0.3);
    z-index: 1000;
  " target="_blank">💬</a>
<script>
    const toggle = document.createElement('button');
    toggle.innerText = '🌙 Modo Oscuro';
    toggle.className = 'dark-toggle';
    toggle.onclick = () => document.body.classList.toggle('dark-mode');
    document.body.appendChild(toggle);
  </script>
</body>
</html>
