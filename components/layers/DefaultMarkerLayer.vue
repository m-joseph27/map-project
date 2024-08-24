<template>
  <div></div>
</template>

<script setup>
import { onMounted } from 'vue'

const props = defineProps(['map', 'data'])

onMounted(() => {
  props.data.features.forEach(feature => {
    if (feature.properties.name === 'Marker Default') {
      new maplibregl.Marker()
        .setLngLat(feature.geometry.coordinates)
        .addTo(props.map)
    }
  })
})
</script>