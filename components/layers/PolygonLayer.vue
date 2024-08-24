<template>
  <div></div>
</template>

<script setup>
import { onMounted } from 'vue'

const props = defineProps(['map', 'data'])

onMounted(() => {
  props.map.addSource('polygon-source', {
    type: 'geojson',
    data: props.data
  })

  props.map.addLayer({
    id: 'polygon-fill-layer',
    type: 'fill',
    source: 'polygon-source',
    filter: ['==', '$type', 'Polygon'],
    paint: {
      'fill-color': ['get', 'fillColor'],
      'fill-opacity': 0.5
    }
  });

  console.log('Polygon fill layer added:', props.map.getLayer('polygon-fill-layer'));

  props.map.addLayer({
    id: 'polygon-line-layer',
    type: 'line',
    source: 'polygon-source',
    filter: ['==', '$type', 'Polygon'],
    paint: {
      'line-color': ['get', 'lineColor'],
      'line-width': 2
    }
  });
})

</script>