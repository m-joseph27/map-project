<template>
  <div></div>
</template>

<script setup>
import { onMounted } from 'vue'

const props = defineProps(['map', 'data'])

onMounted(() => {
  props.map.addSource('circle-source', {
    type: 'geojson',
    data: props.data
  })

  props.map.addLayer({
    id: 'circle-layer',
    type: 'circle',
    source: 'circle-source',
    filter: ['==', '$type', 'Point'],
    paint: {
      'circle-radius': ['get', 'radius'],
      'circle-color': '#FF0000'
    }
  })
})
</script>