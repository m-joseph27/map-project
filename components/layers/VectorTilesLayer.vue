<template>
  <div></div>
</template>

<script setup>
import { onMounted } from 'vue'

const props = defineProps(['map'])

onMounted(() => {
  props.map.addSource('vector-tiles-source', {
    type: 'vector',
    url: 'mapbox://mapbox.mapbox-streets-v8'
  })

  props.map.addLayer({
    id: 'vector-tiles-layer',
    type: 'fill',
    source: 'vector-tiles-source',
    'source-layer': 'building',
    paint: {
      'fill-color': '#888888',
      'fill-opacity': 0.5
    }
  })
})
</script>