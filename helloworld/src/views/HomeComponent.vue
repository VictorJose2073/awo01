<!--Estructura SFC (3 partes: HTML, JS Y CSS)-->
<script setup>
//1.importaciones: otros componentes, servicios, composables

import {ref, computed, onMouted} from 'vue'
import {useWeatherStore} from '@/stores/weatherStore'

//2. Estados locales - solo datos que este componente necesita

const extra = ref(false);
//3. Estado global- desde el store de piña

const store = useWeatherStore()

//4. Valores computados - derivados del estado de datos en nuestro store

const iconClima = computed(()=>store.temperatura > 25? '-' : '-')

//5. ciclo de vida
onMounted(() => console.log('Componente listo'))
</script>


<template>
<div class="weather-card">
    <span>{{ iconClima }}</span>
    <p>{{ store.temperatura }}</p>

</div>

</template>