<template>
  <div></div>
</template>

<script setup>
import { onMounted } from 'vue'

const props = defineProps(['map', 'data'])

onMounted(() => {
  props.data.features.forEach(feature => {
    if (feature.properties.name === 'Custom Image Marker') {
      const el = document.createElement('div')
      el.className = 'custom-marker'
      el.style.backgroundImage = 'url(/path/to/circlegeo-logo.png)'
      el.style.width = '30px'
      el.style.height = '30px'
      el.style.backgroundSize = '100%'

      new maplibre.Marker(el)
        .setLngLat(feature.geometry.coordinates)
        .addTo(props.map)
    }
  })
})
</script>

<style scoped>
.custom-marker {
  background-size: contain;
  border-radius: 50%;
}
</style>