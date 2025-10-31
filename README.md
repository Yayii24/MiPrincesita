<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Para mi princesita 💖</title>
<link href="https://fonts.googleapis.com/css2?family=Poppins:wght@400;600&display=swap" rel="stylesheet">
<style>
body {
  font-family: 'Poppins', sans-serif;
  background: url('fondo.jpg') no-repeat center center fixed;
  background-size: cover;
  margin: 0;
  display: flex;
  flex-direction: column;
  align-items: center;
}

.seccion {
  display: none;
  flex-direction: column;
  align-items: center;
  justify-content: flex-start;
  width: 100%;
  min-height: 100vh;
  padding: 20px;
  box-sizing: border-box;
}

.visible {
  display: flex;
}

.titulo-img { max-width: 900px; transform: scale(1.4); margin-top: -70px; }

.subtitulo-img { 
  max-width: 900px;       
  transform: scale(2.5);   
  margin-top: -100px;      
  margin-left: 10px;        
  margin-bottom: 20px;    
}

.portada { max-width: 450px; transform: scale(1.15); margin-top: -5px; margin-bottom: 25px; }

.menu-principal-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: flex-start;
  height: 100vh;
}

.menu-img { max-width: 500px; transform: scale(1.2); margin-top: -50px; margin-bottom: 20px; }

.botones-menu {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  gap: 5px;
  margin-top: -70px;
}

.btn, .botones-menu button {
  background-color: white;
  color: black;
  border: 2px solid #00000015;
  border-radius: 25px;
  padding: 12px 24px;
  font-size: 1em;
  font-weight: bold;
  cursor: pointer;
  margin: 10px;
  transition: all 0.3s ease;
}

.btn:hover, .botones-menu button:hover { background-color: #f0f0f0; transform: scale(1.05); }

/* === Sopa de letras === */
#sopa-wrapper {
  display: flex;
  flex-direction: column;
  align-items: center;
}

#sopa-container {
  display: grid;
  grid-template-columns: repeat(10, 1fr);
  gap: 5px;
  background-color: rgba(255,255,255,0.9);
  padding: 15px;
  border-radius: 15px;
  box-shadow: 0 4px 15px rgba(0,0,0,0.1);
  width: fit-content;
  margin-top: -20px;
  box-sizing: border-box;
  justify-content: center;
}

.celda {
  width: 20px;               
  height: 20px;
  display: flex;
  justify-content: center;
  align-items: center;
  background: white;
  border-radius: 8px;
  font-size: 1em;          
  font-weight: 600;
  cursor: pointer;
  transition: 0.2s;
  user-select: none;
  color: #333;
  box-sizing: border-box;
}

.celda:hover { background: #e6e6e6; transform: scale(1.1); }
.seleccionada { background: #c3d9ff; }
.acertada { background: #a1f0a1 !important; text-decoration: underline; color: #1a4d1a; }

#lista-palabras {
  margin-top: 25px;
  background: rgba(255,255,255,0.9);
  padding: 15px 25px;
  border-radius: 15px;
  box-shadow: 0 4px 10px rgba(0,0,0,0.1);
  text-align: center;
  max-width: 80vw;
}

#lista-palabras span {
  margin: 6px 10px;
  font-weight: 600;
  display: inline-block;
  color: #444;
}

.encontrada { color: #1a4d1a; text-decoration: line-through; }

/* === PREMIO (MODIFICADO) === */
#premio {
  display: none;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  width: 100%;
  max-width: 1400px;
  margin-top: -35px;
  box-sizing: border-box;
  padding: 10px;
  background: none !important;
  box-shadow: none !important;
  animation: fadeInUp 0.8s ease forwards;
}

#premio img {
  width: 100%;
  max-width: none;
  height: auto;
  object-fit: contain;
  display: block;
  border-radius: 0;
  box-shadow: none;
  background: transparent;
}

#premio p {
  margin-top: -40px; /* SUBIDO más cerca del cupón */
  background: rgba(255,255,255,0.9);
  padding: 8px 16px;
  border-radius: 10px;
  font-weight: 600;
  color: #333;
}

@keyframes fadeInUp {
  from { opacity: 0; transform: translateY(30px); }
  to { opacity: 1; transform: translateY(0); }
}

/* === Quiz de amor === */
#quiz-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  background: rgba(255,255,255,0.9);
  padding: 25px;
  border-radius: 15px;
  box-shadow: 0 4px 10px rgba(0,0,0,0.1);
  max-width: 700px;
  width: 90%;
  margin-top: -20px;
}

#quiz-container h3 {
  margin-bottom: 20px;
  text-align: center;
}

#quiz-container button {
  margin: 10px;
}

/* Adaptación móvil */
@media (max-width: 600px) {
  .titulo-img { width: 95%; transform: scale(1.1); }
  
  .subtitulo-img { 
    width: 95%; 
    transform: scale(1.3); /* aquí le subes el tamaño en móviles */
    margin-top: -80px; 
  }

  .portada, .menu-img { width: 95%; transform: scale(1.1); }
}

  .btn, .botones-menu button { font-size: 0.9em; padding: 10px 16px; }
  .celda { width: 8.5vw; height: 8.5vw; font-size: 1em; }
  #premio img { width: 90vw; max-width: 320px; }
    /* === Quiz de amor en móvil === */
    #quiz-container {
    padding: 15px;
    width: 95%;
      /* === Quiz de amor en móvil === */
  #quiz-container {
    padding: 15px;
    width: 95%;
  }

  #quiz-container button {
    font-size: 0.9em;
    padding: 8px 12px;
  }

  #quiz-container h3 {
    font-size: 1em;
  }

  #quiz-container p {
    font-size: 0.95em;
  }

  }

  #quiz-container button {
    font-size: 0.9em;
    padding: 8px 12px;
  }

  #quiz-container h3 {
    font-size: 1em;
  }

  #quiz-container p {
    font-size: 0.95em;
  }

  
}

/* === Optimización móvil para quiz.png === */
#quiz img {
  max-width: 90%;   /* no supera el ancho de la pantalla */
  height: auto;     /* mantiene proporción */
  margin-bottom: 15px; /* espacio debajo de la imagen */
}

/* === Optimización cupón quiz-premio === */
#quiz-premio img {
  max-width: 90%;   /* ancho máximo para celular */
  height: auto;     /* mantiene proporción */
  display: block;   /* centra la imagen */
  margin: 0 auto 10px; /* espacio debajo */
}

.lista-deseos {
  display: flex;
  flex-direction: column;
  gap: 10px;
  width: 90%;
  margin: 0 auto;
}

.tarjeta-deseo {
  display: flex;
  align-items: center;
  padding: 12px;
  border-radius: 10px;
  background: white;
  box-shadow: 0 2px 8px rgba(0,0,0,0.08);
  font-size: 0.95em;
  color: black;
  gap: 10px;
}

.tarjeta-deseo-ella {
  display: flex;
  align-items: center;
  padding: 12px;
  border-radius: 10px;
  background: #ffe4e1; /* Rosita pastel */
  box-shadow: 0 2px 8px rgba(0,0,0,0.08);
  font-size: 0.95em;
  color: #333;
  gap: 10px;
}

/* Cuadro para marcar */
.cuadro {
  width: 20px;
  height: 20px;
  border: 2px solid #333;
  border-radius: 4px;
  cursor: pointer;
  display: flex;
  align-items: center;
  justify-content: center;
  font-weight: bold;
  color: green;
  user-select: none;
}
/* === Ajuste del premio en quiz solo para móviles === */
@media (max-width: 600px) {
  #quiz-premio {
    align-items: flex-start; /* mover contenido a la izquierda */
    margin-top: -50px;       /* subir bloque */
    margin-left: 10px;       /* separar un poco del borde */
  }

  #quiz-premio img {
    max-width: 85vw; /* ancho más adecuado para móvil */
    height: auto;
    margin: 0 0 5px 0; /* solo margen debajo */
  }

  #quiz-premio p {
    margin-top: -30px; /* acercar al cupón */
    margin-bottom: 8px;
    padding: 6px 12px;
  }

  #quiz-premio button {
    font-size: 0.9em;
    padding: 8px 12px;
  }
}

/* ----- GALERÍA DE FOTOS (tipo historias IG) ----- */
#galeria {
  text-align: center;
  padding: 20px 0;
}

.titulo-seccion {
  display: block;      /* se comporta como bloque */
  width: auto;         /* deja que la imagen use su tamaño natural */
  max-width: none;     /* sin límite */
  height: auto;        /* mantiene proporción */
  margin-top: -60px;   /* sube la imagen */
  margin-bottom: 20px;
}

/* Contenedor exterior: controla el ancho máximo total del carrusel */
.carrusel-container {
  max-width: 1000px;         /* controla el ancho total del carrusel */
  margin: -90px;
  overflow: hidden;
}

.carrusel {
  display: flex;
  overflow-x: auto;
  scroll-snap-type: x mandatory;
  gap: 0px;                  /* espacio entre fotos */
  justify-content: center;
  padding: 1px 0;
}

.carrusel img {
  width: 500px;               /* 👈 aquí ajustas el tamaño de las fotos */
  height: auto;
  border-radius: 20px;
  scroll-snap-align: center;
  transition: transform 0.3s;
  flex-shrink: 0;             /* evita que las fotos se hagan pequeñas */
}


/* Indicadores (puntos abajo del carrusel) */
.puntos {
  display: flex;
  justify-content: center;
  margin-top: 10px;
}

.punto {
  height: 10px;
  width: 10px;
  background-color: #bbb;
  border-radius: 50%;
  margin: 0 5px;
  transition: background-color 0.3s;
}

.punto.activo {
  background-color: #ff7eb9;
}

@media (max-width: 768px) {
  .titulo-seccion {
    max-width: 180px;
  }
  .carrusel-container {
    width: 95%;
  }

  .carrusel {
    gap: 0px;  /* aquí ajustas el espacio entre fotos */
  }
}

@media (max-width: 768px) {
  .carrusel img {
    width: 90vw;       /* cada foto ocupa 90% del ancho del móvil */
    max-width: 300px;  /* opcional: evita que sea gigante en tablets */
    height: auto;
    flex-shrink: 0;    /* que no se encojan */
    border-radius: 20px;
  }

  .carrusel {
    gap: 10px;         /* pequeño espacio entre fotos */
    padding: 0 10px;   /* margen lateral */
    justify-content: flex-start; /* importante: empezar desde la primera foto */
  }
}

/* Ajuste solo para móviles */
@media (max-width: 600px) {
  .titulo-seccion {
    width: 90vw;      /* 90% del ancho de la pantalla del móvil */
    height: auto;     /* mantiene proporción */
    margin-top: -60px;
    margin-bottom: 20px;
  }
}
/* === Fotos.png más grande en móvil === */
@media (max-width: 600px) {
  .titulo-seccion {
    width: 120vw !important;   /* casi todo el ancho de la pantalla */
    max-width: none !important; /* ignora cualquier límite */
    height: auto !important;    /* mantiene proporción */
    margin-top: -120px;          /* ajusta hacia arriba si quieres */
    margin-bottom: 20px;
    display: block;
  }
}

</style>
</head>
<body>

<!-- INICIO -->
<section id="inicio" class="seccion visible">
  <img src="titulo1.png" alt="Hola mi niña" class="titulo-img">
  <img src="subtitulo1.png" alt="Subtítulo" class="subtitulo-img">
  <img src="portada1.png" alt="Portada" class="portada">
  <button class="btn" onclick="mostrarMenuPrincipal()">Ir al menú principal</button>
</section>

<!-- MENÚ PRINCIPAL -->
<section id="menu-principal" class="seccion">
  <div class="menu-principal-container">
    <img src="menu.png" alt="Menú principal" class="menu-img">
    <div class="botones-menu">
      <button onclick="irASeccion('carta')">💗 Bienvenida mi cielo 💗</button>
      <button onclick="irASeccion('juego')">🔠 Sopita de letras 🔠</button>
      <button onclick="irASeccion('quiz')">✅ Examen de tu Yayi ✅</button>
      <button onclick="irASeccion('deseos')">✨ Lista de deseos ✨</button>
      <button onclick="irASeccion('mensajes')">💬 Mensajes para Yayi 💬</button>
      <button onclick="irASeccion('galeria')">📸 Galeria de recuerdos 📸</button>
    </div>
    <button class="btn" onclick="irASeccion('inicio')">Volver al inicio</button>
  </div>
</section>

<section id="carta" class="seccion">
  <!-- Título arriba -->
  <img src="cartalogo.png" alt="Carta para ti" class="titulo-seccion" style="margin-top:-60px; margin-bottom:20px; width:120vw; max-width:none; display:block;">

  <!-- Contenedor de la carta -->
  <div class="carta-container" style="display:flex; flex-direction:column; align-items:center; justify-content:center; max-width:1000px; margin:-40px auto;">

    <div class="carta" style="display:flex; justify-content:center; align-items:center; overflow:hidden; width:100%; max-width:600px; position:relative;">
      <!-- Imágenes de la carta -->
      <img src="carta1.png" alt="Carta 1" class="carta-img" style="width:100%; height:auto; flex-shrink:0;">
      <img src="carta2.png" alt="Carta 2" class="carta-img" style="width:100%; height:auto; flex-shrink:0; display:none;">
      <img src="carta3.png" alt="Carta 3" class="carta-img" style="width:100%; height:auto; flex-shrink:0; display:none;">
      <img src="carta4.png" alt="Carta 4" class="carta-img" style="width:100%; height:auto; flex-shrink:0; display:none;">
    </div>

    <!-- Botones de navegación -->
    <div style="margin-top:15px; display:flex; gap:20px;">
      <button class="btn" id="carta-prev">Anterior</button>
      <button class="btn" id="carta-next">Siguiente ➡️</button>
    </div>

  </div>

  <button class="btn" onclick="irASeccion('menu-principal')" style="margin-top:20px;">Volver al menú</button>
</section>


<!-- 🔤 SOPA DE LETRAS -->
<section id="juego" class="seccion">
  <img src="sopa.png" alt="Sopa de letras del amor" class="menu-img" style="max-width:420px; margin-top:-50px; margin-left:-5px;">
  <div id="sopa-wrapper">
    <div id="sopa-container"></div>
    <div id="lista-palabras"></div>
    <div id="premio">
      <img src="cupon1.png" alt="Cupón de premio">
      <p>Felicidades, acabas de ganar un ticket valido por 999 usos</p>
      <button class="btn" onclick="irASeccion('inicio')">Volver al inicio</button>
    </div>
  </div>
  <button class="btn" onclick="irASeccion('menu-principal')" style="margin-top:20px;">Volver al menú</button>
</section>

<!-- QUIZ DE AMOR -->
<section id="quiz" class="seccion">
  <img src="quiz.png" alt="Quiz de amor" style="max-width:300px; height:auto; margin-top:-90px; margin-bottom:20px;">
  <div id="quiz-container"></div>

  <!-- Premio al terminar -->
  <div id="quiz-premio" style="display:none; flex-direction: column; align-items:flex-start; margin-top:-60px; margin-left:20px;">
    <img src="cupon2.png" alt="Cupón de premio" style="max-width:300px; height:auto;">
    <button class="btn" onclick="irASeccion('inicio')">Volver al inicio</button>
    <button class="btn" onclick="irASeccion('menu-principal')">Volver al menú principal</button>
  </div>
</section>


<!-- OTRAS SECCIONES -->
<!-- LISTA DE DESEOS -->
<section id="deseos" class="seccion" style="margin-top:-160px;">
  <img src="deseo.png" alt="Lista de deseos" style="max-width:450px; height:auto; margin-bottom:10px;">
  <p style="max-width:90%; text-align:center; margin-top:-115px; margin-bottom:20px;">
    Este es el apartado de la lista de deseos, aqui debes marcar los que ya hemos hecho y tambien si quieres puedes agregar tus propios deseos mi bebé 💗
  </p>

  <!-- Lista de tus deseos -->
  <div id="lista-mios" class="lista-deseos"></div>

  <!-- Lista de deseos de ella -->
  <div id="lista-ella" class="lista-deseos" style="margin-top:10px;"></div>

  <!-- Input para que ella agregue deseos -->
  <div style="display:flex; justify-content:center; margin-top:20px; gap:10px; width:90%;">
    <input type="text" id="nuevo-deseo" placeholder="Escribe tu deseo..." style="flex:1; border-radius:8px; padding:8px; border:1px solid #ccc;">
    <button class="btn" onclick="agregarDeseo()">Agregar</button>
  </div>

  <button class="btn" onclick="irASeccion('menu-principal')" style="margin-top:20px;">Volver al menú</button>
</section>

<section id="mensajes" class="seccion"><h2>❤️‍🩹 Mensajitoshhh ❤️‍🩹</h2><textarea id="mensaje" rows="5" style="width:80%;border-radius:10px;padding:10px;"></textarea><br><button class="btn" onclick="enviarMensaje()">Enviar</button><button class="btn" onclick="irASeccion('menu-principal')">Volver</button></section>

<!-- SECCIÓN GALERÍA DE FOTOS -->
<section id="galeria" class="seccion">
  <img src="fotos.png" alt="Galería de fotos" class="titulo-seccion">
  
  <div class="carrusel-container">
    <div class="carrusel">
      <img src="ig1.png" alt="Foto 1">
      <img src="ig2.png" alt="Foto 2">
      <img src="ig3.png" alt="Foto 3">
      <img src="ig4.png" alt="Foto 4">
      <img src="ig5.png" alt="Foto 5">
      <img src="ig6.png" alt="Foto 6">
      <img src="ig7.png" alt="Foto 7">
      <img src="ig8.png" alt="Foto 8">
      <img src="ig9.png" alt="Foto 9">
      <img src="ig10.png" alt="Foto 10">
      <img src="ig11.png" alt="Foto 11">
    </div>
    <button class="btn" onclick="irASeccion('menu-principal')" style="margin-top:20px;">⬅️ Volver al menú</button>
  </div>
</section>


<script>
function irASeccion(id) {
  document.querySelectorAll('.seccion').forEach(sec => sec.classList.remove('visible'));
  const seccion = document.getElementById(id);
  seccion.classList.add('visible');
  window.scrollTo({ top: 0, behavior: 'smooth' });

  if(id === "galeria") { 
  // Reiniciar índice
  indice = 0; 
  carrusel.scrollLeft = 0;
}


  // === GENERAR EL QUIZ AUTOMÁTICAMENTE ===
  if(id === "quiz"){
    document.getElementById("quiz-premio").style.display = "none"; // Oculta el premio
    generarQuiz(); // Crea las preguntas
  }
}

// ---- CARRUSEL AUTOMÁTICO ----
const carrusel = document.querySelector(".carrusel");
const imagenes = document.querySelectorAll(".carrusel img");
let indice = 0;

function moverCarrusel() {
  indice = (indice + 1) % imagenes.length;
  carrusel.style.transform = `translateX(-${indice * 100}%)`;
}

function mostrarMenuPrincipal() { irASeccion('menu-principal'); }
function enviarMensaje() {
  const texto = document.getElementById('mensaje').value.trim();
  if (!texto) return alert("Escribe algo antes de enviar ❤️");
  window.open(`https://wa.me/528131068497?text=${encodeURIComponent(texto)}`, "_blank");
}

/* === Sopa de Letras === */
const palabras = ["NANI","YAYI","PRINCESA","AMOR","HERMOSA","BESOS","ZURDA","CORAZON","DIOS","JIJI"];
const gridSize = 10;
const letras = "ABCDEFGHIJKLMNOPQRSTUVWXYZ";
const sopaContainer = document.getElementById("sopa-container");
const listaPalabrasDiv = document.getElementById("lista-palabras");
let seleccionadas = [], acertadas = [];

function generarSopa() {
  let grid = Array(gridSize).fill(null).map(()=>Array(gridSize).fill(''));
  palabras.forEach(palabra=>{
    let fila, col;
    do { fila=Math.floor(Math.random()*gridSize); col=Math.floor(Math.random()*(gridSize-palabra.length)); }
    while (!puedeColocar(grid,palabra,fila,col));
    for (let i=0;i<palabra.length;i++) grid[fila][col+i]=palabra[i];
  });
  for (let i=0;i<gridSize;i++) for (let j=0;j<gridSize;j++) if(grid[i][j]==='') grid[i][j]=letras[Math.floor(Math.random()*letras.length)];

  sopaContainer.innerHTML=""; listaPalabrasDiv.innerHTML=""; seleccionadas=[]; acertadas=[];
  for (let i=0;i<gridSize;i++) for (let j=0;j<gridSize;j++){
    const celda=document.createElement("div");
    celda.textContent=grid[i][j];
    celda.className="celda";
    celda.dataset.fila=i; celda.dataset.col=j;
    celda.addEventListener("click",()=>seleccionarCelda(celda));
    sopaContainer.appendChild(celda);
  }
  palabras.forEach(p=>{
    const span=document.createElement("span");
    span.textContent=p;
    span.id="pal_"+p;
    listaPalabrasDiv.appendChild(span);
  });
}
function puedeColocar(grid,palabra,fila,col){for(let i=0;i<palabra.length;i++) if(grid[fila][col+i]!=='') return false; return true;}

function seleccionarCelda(celda){
  if(celda.classList.contains("acertada"))return;
  celda.classList.toggle("seleccionada");
  seleccionadas=[...document.querySelectorAll(".seleccionada")];
  const texto=seleccionadas.map(c=>c.textContent).join('');
  const inverso=texto.split('').reverse().join('');
  const palabraEncontrada=palabras.find(p=>p===texto||p===inverso);
   if(palabraEncontrada){
    seleccionadas.forEach(c => c.classList.add("acertada"));
    document.getElementById("pal_" + palabraEncontrada).classList.add("encontrada");
    acertadas.push(palabraEncontrada);
    seleccionadas = [];
    document.querySelectorAll(".seleccionada").forEach(c => c.classList.remove("seleccionada"));
    if(acertadas.length === palabras.length){
      document.getElementById("premio").style.display = "flex";
    }
  }
}

/* Generar la sopa al cargar la página */
window.addEventListener("load", generarSopa);

const quizPreguntas = [
  {
    pregunta: "La primera vez que fui a tu casa ¿qué comida me invitó a comer tu familia?",
    opciones: ["Enchiladas suizas", "Fajitas de pollo con macarrón", "Mole con arroz"],
    correcta: "Fajitas de pollo con macarrón"
  },
  {
    pregunta: "Dónde nos tomamos nuestra primer foto?",
    opciones: ["En la iglesia", "En Parque fundidora", "En la boda de tu mamá"],
    correcta: "En la boda de tu mamá"
  },
  {
    pregunta: "Cuál es mi color favorito?",
    opciones: ["Rosa", "Negro", "Blanco"],
    correcta: "Rosa"
  },
  {
    pregunta: "¿Qué es lo primero que piensas cuando me ves después de tiempo sin vernos?",
    opciones: ["Sonrío automáticamente", "Quiero abrazarte", "Me pongo nerviosa"],
    correcta: ["Sonrío automáticamente","Quiero abrazarte","Me pongo nerviosa"]
  },
  {
    pregunta: "¿Cuál fue el primer regalo que te di?",
    opciones: ["Una cajita con Peluches y una carta", "Tu nombre en cursiva", "Un bob esponja nemo"],
    correcta: "Un bob esponja nemo"
  },
  {
    pregunta: "Quién se baña menos veces a la semana?",
    opciones: ["Nani", "Yayi", "Los dos por igual"],
    correcta: "Nani",
    mensajesEspeciales: {
      "Yayi": "AMOR ERES TU, NO TE HAGAS",
      "Los dos por igual": "NO MIENTAS AMOR, ERES TU"
    }
  },
  {
    pregunta: "Cuál es el libro favorito de Yayi?",
    opciones: ["La naranja mecánica", "It", "Crónicas de una muerte anunciada"],
    correcta: "La naranja mecánica"
  },
  {
    pregunta: "Cuál es uno de los apodos favoritos de Yayi?",
    opciones: ["Amor", "Corazon", "Precioso"],
    correcta: "Precioso"
  },
  {
    pregunta: "Cuántos deportes practica Yayi a día de hoy?",
    opciones: ["1", "2", "3"],
    correcta: "2"
  },
  {
    pregunta: "Qué prefiere Yayi?",
    opciones: ["UCM (universo cinematográfico de marvel)", "DC COMICS", "ambas"],
    correcta: "DC COMICS"
  }
];

function generarQuiz(){
  const cont = document.getElementById("quiz-container");
  cont.innerHTML = "";
  quizPreguntas.forEach((q, idx)=>{
    const divPregunta = document.createElement("div");
    divPregunta.style.background = "rgba(255,255,255,0.9)";
    divPregunta.style.padding = "15px";
    divPregunta.style.margin = "10px 0";
    divPregunta.style.borderRadius = "10px";
    divPregunta.style.boxShadow = "0 3px 8px rgba(0,0,0,0.1)";

    const h3 = document.createElement("h3");
    h3.textContent = (idx+1)+". "+q.pregunta;
    divPregunta.appendChild(h3);

    const resultado = document.createElement("p");
    resultado.style.fontWeight = "bold";
    resultado.style.marginTop = "10px";
    divPregunta.appendChild(resultado);

    q.opciones.forEach(op=>{
      const btn = document.createElement("button");
      btn.textContent = op;
      btn.className = "btn";
      btn.addEventListener("click", ()=>{
        if(q.mensajesEspeciales && q.mensajesEspeciales[op]){
          resultado.textContent = q.mensajesEspeciales[op];
          resultado.style.color = "orange";
        } else if(Array.isArray(q.correcta) && q.correcta.includes(op)){
          resultado.textContent = "Correcto ✅";
          resultado.style.color = "green";
        } else if(op === q.correcta){
          resultado.textContent = "Correcto ✅";
          resultado.style.color = "green";
        } else {
          resultado.textContent = "Incorrecto ❌";
          resultado.style.color = "red";
        }

        // Si todas las preguntas ya tienen respuesta, mostrar premio
        const todosResueltos = Array.from(document.querySelectorAll("#quiz-container p")).every(p=>p.textContent!=="");
        if(todosResueltos){
          document.getElementById("quiz-premio").style.display = "flex";
        }
      });
      divPregunta.appendChild(btn);
    });

    cont.appendChild(divPregunta);
  });
}
// MIS DESEOS
const deseosMios = [
  "Ver el amanecer en la playa juntos",
  "Dormir y amanecer juntos",
  "Viajar a otra ciudad o estado juntos",
  "Probar un deporte extremo juntos",
  "Correr una carrera o maraton juntos",
  "Cocinar juntos",
  "Jugar al xbox juntos",
  "Hacernos youtubers",
  "Plantar un arbolito",
  "Armar una capsula del tiempo",
  "Hacer un proyecto solidario juntos",
  "Casarnos"
];

const listaMiosDiv = document.getElementById("lista-mios");
const listaEllaDiv = document.getElementById("lista-ella");

// Función para crear una tarjeta de deseo
function crearTarjeta(texto, esElla=false){
  const div = document.createElement("div");
  div.className = esElla ? "tarjeta-deseo-ella" : "tarjeta-deseo";

  const cuadro = document.createElement("div");
  cuadro.className = "cuadro";
  cuadro.addEventListener("click", ()=> {
    if(cuadro.textContent === "✔") cuadro.textContent = "";
    else cuadro.textContent = "✔";
  });

  const span = document.createElement("span");
  span.textContent = texto;

  div.appendChild(cuadro);
  div.appendChild(span);

  if(esElla) listaEllaDiv.appendChild(div);
  else listaMiosDiv.appendChild(div);
}

// Cargar los deseos míos al abrir la sección
function cargarDeseosMios(){
  listaMiosDiv.innerHTML = "";
  deseosMios.forEach(d=> crearTarjeta(d));
}

// Función para agregar deseo de ella
function agregarDeseo(){
  const input = document.getElementById("nuevo-deseo");
  const texto = input.value.trim();
  if(!texto) return;
  crearTarjeta(texto,true);
  input.value = "";
}

// Cargar deseos cuando se abre la sección
function abrirDeseos(){
  cargarDeseosMios();
}

// Llama a abrirDeseos cada vez que entras a la sección
document.querySelector('button[onclick*="irASeccion(\'deseos\')"]').addEventListener("click", abrirDeseos);

// === CONTROL DE CARTA ===
let cartaIndice = 0;
let cartas; // definimos variable global

function mostrarCarta(indice){
  cartas.forEach((img, i) => {
    img.style.display = i === indice ? "block" : "none";
  });
}

// Función para inicializar la carta cada vez que entras a la sección
function initCarta(){
  cartas = document.querySelectorAll(".carta-img");
  cartaIndice = 0;
  mostrarCarta(cartaIndice);

  document.getElementById("carta-next").onclick = ()=>{
    cartaIndice = (cartaIndice + 1) % cartas.length;
    mostrarCarta(cartaIndice);
  }

  document.getElementById("carta-prev").onclick = ()=>{
    cartaIndice = (cartaIndice - 1 + cartas.length) % cartas.length;
    mostrarCarta(cartaIndice);
  }
}

// Llamamos a initCarta cada vez que entras a la sección
function irASeccion(id) {
  document.querySelectorAll('.seccion').forEach(sec => sec.classList.remove('visible'));
  const seccion = document.getElementById(id);
  seccion.classList.add('visible');
  window.scrollTo({ top: 0, behavior: 'smooth' });

  if(id === "carta") initCarta(); // aquí inicializamos la carta
  if(id === "galeria") { 
    // Reiniciar la galería para que siempre empiece desde la primera foto
    carrusel.scrollLeft = 0;
}


  // === GENERAR EL QUIZ AUTOMÁTICAMENTE ===
  if(id === "quiz"){
    document.getElementById("quiz-premio").style.display = "none"; // Oculta el premio
    generarQuiz(); // Crea las preguntas
  }
}
// Botón de carta
document.querySelector('button[onclick*="irASeccion(\'carta\')"]').addEventListener("click", ()=>{
  irASeccion('carta');
});

</script>
</body>
</html>
