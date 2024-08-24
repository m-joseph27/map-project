<template>
  <div>
    <h1>Tech Test MapLibre Circlegeo</h1>
    <Map />
  </div>
</template>

<script setup>
import Map from '@/components/Map.vue'
</script>

<style scoped>
  h1 {
    text-align: center;
    font-weight: bold;
    letter-spacing: 5px;
    color: rgba(12, 104, 233, 0.759);
  }
</style>

<!-- style: `https://api.maptiler.com/maps/streets-v2/style.json?key=${apiKey}`, -->
<!-- const apiKey = 'TC8vZBDQweh7PquodwxM' -->