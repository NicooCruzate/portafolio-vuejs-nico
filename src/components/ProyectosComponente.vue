<script setup>
import proyecto1 from '/src/assets/outlier.png';
import proyecto2 from '/src/assets/outlier2.png';
import proyecto3 from '/src/assets/bank.jpeg';
import { ref } from 'vue';
var misProyectos = ref([])   
misProyectos.value = ([
    {
    id:1,
    titulo: "Writing AI",
    descripcion: "Transcribir y modificar respuestas de IA.",
    src: proyecto1
    },
       {
    id:2,
    titulo: "AI Response Analysis",
    descripcion: "Analisis sobre las respuestas de IA y Supervisar el funcionamiento.",
    src: proyecto2
    },
    {
        id: 3,
        src: proyecto3,
        titulo: "Sistema Bancario",
        descripcion: "Realizamos un proyecto de sistema bancario con entidad grafica en java con compañeros en la T.U.P de la UTN",
        projectoLink: "https://www.google.com.ar",
        githubLink: "https://github.com/usuario/proyecto"
    },

]) 

</script>

<template>
    <!-- Aquí va el código HTML de la galería de proyectos -->
    <div class="galeria">
      <!-- Itera sobre cada proyecto en la lista de misProyectos -->
        <li class="proyecto" v-for="proyecto in misProyectos" :key="proyecto.id">
          <!-- Muestra la imagen del proyecto utilizando v-bind para el atributo src -->
          <img :src="proyecto.src" :alt="proyecto.titulo" />
          <div class="proyecto-info">
            <!-- Muestra el título y la descripción del proyecto utilizando la interpolación de Vue.js -->
            <h3>{{ proyecto.titulo }}</h3>
            <p>{{ proyecto.descripcion }}</p>
            <div class="proyecto-links">
              <a :href="proyecto.proyectoLink" class="btn-ver-mas" target="_blank" rel="noopener noreferrer">Ver Proyecto</a>
              <a :href="proyecto.githubLink" class="github-link" target="_blank" rel="noopener noreferrer">Ver código en GitHub</a>
            </div>
          </div>
        </li>
    </div>
  </template>

<style scoped>
.galeria {
    width: 100%;
    height: 100%;
    display: flex;
    flex-wrap: wrap;
    gap: 20px;
    padding: 20px;
    justify-content: center;
    background: linear-gradient(to bottom right, rgba(0, 0, 0, 0), rgba(70, 0, 0, 0.8));
    background-size: 400% 400%;
    animation: gradient 15s ease infinite;
}

/* Define una animacion llamada "gradient" para cambiar la posicion del fondo */
@keyframes gradient {
    /* Al inicio, el fondo esta posicionado en el 0% horizontal y 50% vertical */
    0% {
        background-position: 0% 50%;
    }

    50% {
        background-position: 100% 50%;
    }

    100% {
        background-position: 0% 50%;
    }
}

.proyecto {
    display: flex;
    flex-direction: column;
    border: 2px solid #660000;
    border-radius: 8px;
    overflow: hidden;
    background-color: #f9f9f9;
    max-width: 222px;
    flex: 1 1 300px;
}
.proyecto img {
    width: 100%;
    height: auto;
    display: block;
}
.proyecto-info {
    padding: 15px;
    text-align: center;
}
.proyecto-info h3 {
    margin: 10px 0;
    font-size: 1.3em;
    color: #333;
}

.proyecto-info p {
    margin: 10px 0;
    font-size: 1em;
    color: #666;
}

.proyecto-links {
    display: flex;
    flex-direction: column;
    gap: 10px;
    margin-top: 10px;
}

.proyecto-links .btn-ver-mas {
    background-color: #007BFF;
    color: #fff;
    padding: 10px 15px;
    border-radius: 5px;
    text-decoration: none;
    transition: background-color 0.3s;
}

.proyecto-links .btn-ver-mas:hover {
    background-color: #0056b3;
}

.proyecto-links .github-link {
    color: #333;
    text-decoration: none;
    font-size: 0.9em;
}

.proyecto-links .github-link:hover {
    text-decoration: underline;
}
</style>
