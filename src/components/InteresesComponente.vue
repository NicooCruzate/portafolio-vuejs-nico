<script setup>
import { ref } from 'vue';
// Este es un arreglo con ref para que se pueda reactivar el cambio de los intereses
const intereses = ref([
    'Desarrollo de Software y Programación: Comencé a estudiar programación en 2024 en la UTN San Rafael. Me apasiona la programación y me esfuerzo por aprender y mejorar mis habilidades en este campo.',
    'Tecnología e Innovación: Me interesa explorar nuevas tendencias tecnológicas que amplíen mis conocimientos, especialmente en áreas relacionadas con la programación y el desarrollo de aplicaciones',
    'Me encanta el desarrollo frontend porque me permite combinar creatividad y tecnología para crear interfaces atractivas y funcionales. Disfruto diseñar experiencias de usuario intuitivas y visualmente agradables.',
    'Tengo un interés particular en los videojuegos desde pequeño, y siempre me interesó algún día poder crear un videojuego.'
]);
</script>

<template>
    <div class="intereses-contenedor">
        <FondoLava />
        <ul class="contenedor-lista">
            <li class="item" v-for="interes in intereses" :key="interes">
                {{ interes }}
            </li>
        </ul>
    </div>
</template>

<style scoped>
.intereses-contenedor {
    display: flex;
    flex-direction: column; /* Para que los elementos se apilen verticalmente */
    align-items: center; /* Centra la lista horizontalmente */
    position: relative;
    margin: 0 auto;
    max-width: 85%;
    padding: 2rem; /* Espaciado interior más amplio */
    background: linear-gradient(to bottom right, rgba(0, 0, 0, 0), rgba(70, 0, 0, 0.8)); /* Fondo transparente con color blanco */
    border-radius: 12px; /* Bordes redondeados */
    box-shadow: 0 4px 15px rgba(0, 0, 0, 0.1); /* Sombra suave */
}

.contenedor-lista {
    list-style-type: none;
    padding: 0; /* Elimina el padding de la lista */
    margin: 0; /* Elimina el margen de la lista */
    color: #D9E0E8; /* Color de texto oscuro */
    font-size: 1.2rem; /* Tamaño de fuente más pequeño y elegante */
}

.item {
    margin-bottom: 1rem;
    padding: 1rem; /* Espaciado alrededor de cada ítem */
    background: rgba(106, 199, 227, 0.2); /* Fondo celeste semi-transparente */
    border: 1px solid #e1e1e1; /* Borde sutil alrededor de cada ítem */
    border-radius: 8px; /* Bordes redondeados para cada ítem */
    transition: none; /* Sin efecto de hover */
}
</style>
