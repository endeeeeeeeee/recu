

<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Recuerdo Especial</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <style>
        .imagen-interactiva {
            transition: transform 0.3s ease;
        }
        .imagen-interactiva:hover {
            transform: scale(1.1);
        }

        .reproductor-fijo {
            position: fixed;
            bottom: 20px;
            right: 20px;
            z-index: 1000;
            width: 300px;
            height: 80px;
        }

        .scrollbar-hide::-webkit-scrollbar {
            display: none;
        }
        .scrollbar-hide {
            -ms-overflow-style: none;
            scrollbar-width: none;
        }

        /* Estilos para el primer fondo (superior) */
        #video-fondo {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 50%;
            object-fit: cover;
            z-index: -2;
            display: none; /* Se oculta por defecto */
        }

        #audio-fondo {
            display: none; /* Ocultamos el audio inicialmente */
        }

        /* Estilos para el segundo fondo (inferior) */
        #video-corazon {
            position: fixed;
            bottom: 0;
            left: 0;
            width: 100%;
            height: 50%;
            object-fit: cover;
            z-index: -1;
            display: none; /* Se oculta por defecto */
        }

        #audio-corazon {
            display: none; /* Ocultamos el audio inicialmente */
        }

        /* Estilo para la sección de Tres Millones (más estético) */
        .tres-millones-area {
            background-color: rgba(255, 99, 71, 0.8);
            border-radius: 15px;
            padding: 50px;
            margin-top: 30px;
            text-align: center;
            font-size: 2rem;
            font-weight: bold;
            color: white;
            transition: transform 0.3s ease, background-color 0.3s ease;
            margin-bottom: 50px;
            box-shadow: 0 4px 15px rgba(0, 0, 0, 0.2); /* Sombra suave */
        }

        .tres-millones-area:hover {
            transform: scale(1.05);
            background-color: rgba(255, 99, 71, 1);
        }

        /* Estilo para los textos secundarios */
        .subtitulo {
            font-size: 1.2rem;
            color: rgba(255, 255, 255, 0.8);
        }
    </style>
</head>
<body class="bg-gray-100 flex items-center justify-center min-h-screen">
    <!-- Video de fondo para la parte superior -->
    <video id="video-fondo" autoplay loop muted>
        <source src="tu-video.mp4" type="video/mp4">
        Tu navegador no soporta el formato de video.
    </video>

    <!-- Audio de fondo para la parte superior -->
    <audio id="audio-fondo" autoplay loop>
        <source src="tu-audio.mp3" type="audio/mp3">
        Tu navegador no soporta el formato de audio.
    </audio>

    <!-- Contenedor principal -->
    <div class="bg-white p-6 shadow-lg rounded-lg max-w-xl w-full relative z-10">
        <!-- Encabezado -->
        <header class="text-center">
            <h1 
                class="text-3xl font-bold text-gray-800 animate-pulse" 
                onmouseenter="reproducirVideoAudio()" 
                onmouseleave="detenerVideoAudio()"> 
                "Lo que más amamos nunca nos abandona"
            </h1>
        </header>

        <!-- Contenido principal -->
        <main class="mt-4">
            <!-- Foto Principal -->
            <section class="foto-principal text-center">
                <img src="foto-mascota.jpg" alt="Foto de la mascota" class="w-full rounded-lg shadow-md imagen-interactiva" 
                    onmouseenter="reproducirVideoAudio()" 
                    onmouseleave="detenerVideoAudio()">
                <p class="mt-2 text-xl font-semibold text-gray-600" 
                   onmouseenter="reproducirVideoAudio()" 
                   onmouseleave="detenerVideoAudio()"></p>
            </section>

            <!-- Nueva Sección: El ojo jamás olvida lo que ha visto el corazón -->
            <section class="seccion-corazon bg-gray-800 text-white py-16" id="seccion-corazon">
                <div class="text-center">
                    <h2 class="text-4xl font-bold animate-pulse"
                        onmouseenter="reproducirCorazon()" 
                        onmouseleave="detenerCorazon()">El ojo jamás olvida lo que ha visto el corazón ❤️</h2>
                </div>
                <!-- Video de fondo para la sección inferior -->
                <video id="video-corazon" autoplay loop muted class="absolute top-0 left-0 w-full h-full object-cover z-[-1] opacity-60">
                    <source src="video-corazon.mp4" type="video/mp4">
                    Tu navegador no soporta el formato de video.
                </video>

                <!-- Audio de fondo para la sección inferior -->
                <audio id="audio-corazon" autoplay loop>
                    <source src="audio-corazon.mp3" type="audio/mp3">
                    Tu navegador no soporta el formato de audio.
                </audio>
            </section>

          

            <!-- Galería de Recuerdos -->
            <section class="imagenes mt-6">
                <h2 class="text-xl font-semibold text-gray-800 mb-4">Galería de Recuerdos</h2>
                <div class="flex overflow-x-auto space-x-4 scrollbar-hide">
                    <div class="overflow-hidden w-40 h-40 rounded-lg shadow-md flex-shrink-0">
                        <img src="foto1.jpg" alt="Recuerdo 1" class="w-full h-full object-cover imagen-interactiva">
                        <p class="mt-2 text-center text-sm text-gray-500">Un gran momento </p>
                    </div>
                    <div class="overflow-hidden w-40 h-40 rounded-lg shadow-md flex-shrink-0">
                        <img src="foto2.jpg" alt="Recuerdo 2" class="w-full h-full object-cover imagen-interactiva">
                        <p class="mt-2 text-center text-sm text-gray-500">El día </p>
                    </div>
                    <div class="overflow-hidden w-40 h-40 rounded-lg shadow-md flex-shrink-0">
                        <img src="foto3.jpg" alt="-" class="w-full h-full object-cover imagen-interactiva">
                        <p class="mt-2 text-center text-sm text-gray-500">Su momento</p>
                    </div>
                </div>
            </section>

        <!-- Galería de Recuerdos -->
<section class="imagenes mt-6">
    <h2 class="text-xl font-semibold text-gray-800 mb-4">Mufasa we</h2>
    <div class="flex overflow-x-auto space-x-4 scrollbar-hide">
        <!-- Primer video -->
        <div class="video-item flex-shrink-0 w-80">
            <iframe src="https://www.tiktok.com/embed/7443655613986508087" 
                    class="w-full h-[600px]" frameborder="0" 
                    allow="autoplay; clipboard-write; encrypted-media; picture-in-picture" 
                    allowfullscreen>
            </iframe>
        </div>

        <!-- Segundo video -->
        <div class="video-item flex-shrink-0 w-80">
            <iframe src="https://www.tiktok.com/embed/7134010754054786309" 
                    class="w-full h-[600px]" frameborder="0" 
                    allow="autoplay; clipboard-write; encrypted-media; picture-in-picture" 
                    allowfullscreen>
            </iframe>
        </div>

        <!-- Tercer video -->
        <div class="video-item flex-shrink-0 w-80">
            <iframe src="https://www.tiktok.com/embed/7399641874367089925" 
                    class="w-full h-[600px]" frameborder="0" 
                    allow="autoplay; clipboard-write; encrypted-media; picture-in-picture" 
                    allowfullscreen>
            </iframe>
        </div>
    </div>
</section>
  <!-- Sección de Tres Millones (más estética y ajustada) -->
  <section class="tres-millones-area"
  onmouseenter="reproducirAudioTresMillones()" 
  onmouseleave="detenerAudioTresMillones()">
  Tres millones
  
</section>

        </main>

        <!-- Pie de Página -->
        <footer class="mt-8 text-center text-gray-500 text-sm">
            <p>&copy; Santa Cruz core</p>
        </footer>
    </div>

    <!-- Reproductor de Música Fijo de Spotify -->
    <div class="reproductor-fijo">
        <iframe src="https://open.spotify.com/embed/playlist/4ODpq1dJzT84vOO0TZh25l" 
                width="100%" height="80" frameborder="0" 
                allow="autoplay; clipboard-write; encrypted-media; picture-in-picture"></iframe>
    </div>

    <script>
        var audioTresMillones = null; // Variable global para el audio

        // Función para reproducir el audio "tres millones"
function reproducirAudioTresMillones() {
    // Verifica si el audio ya está reproduciéndose, si no, lo reproduce
    if (audioTresMillones === null || audioTresMillones.paused) {
        audioTresMillones = new Audio('audio-tres-millones.mp3'); // Ruta del audio
        audioTresMillones.play();
    }
}

// Función para detener el audio "tres millones"
function detenerAudioTresMillones() {
    if (audioTresMillones !== null) {
        audioTresMillones.pause();
        audioTresMillones.currentTime = 0; // Resetea el tiempo para que comience desde el principio la próxima vez
    }
}


        function reproducirVideoAudio() {
            // Reproducir el primer video y audio cuando el cursor esté sobre el título
            document.getElementById('video-fondo').style.display = 'block';
            document.getElementById('audio-fondo').play();
        }

        function detenerVideoAudio() {
            // Detener el primer video y audio cuando el cursor salga del título
            document.getElementById('video-fondo').style.display = 'none';
            document.getElementById('audio-fondo').pause();
        }

        function reproducirCorazon() {
            // Reproducir el segundo video y audio cuando el cursor esté sobre el título de "El ojo jamás olvida lo que ha visto el corazón"
            document.getElementById('video-corazon').style.display = 'block';
            document.getElementById('audio-corazon').play();
        }

        function detenerCorazon() {
            // Detener el segundo video y audio cuando el cursor salga del título de "El ojo jamás olvida lo que ha visto el corazón"
            document.getElementById('video-corazon').style.display = 'none';
            document.getElementById('audio-corazon').pause();
        }
    </script>
</body>
</html>


