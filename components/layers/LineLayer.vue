<template>
  <div></div>
</template>

<script setup>
import { defineProps, onMounted } from 'vue'

const props = defineProps({
  map: Object,
  data: Object
})

const { map, data } = props


onMounted(() => {
  console.log('maps', map)
  console.log('data', data)
  if (!map) {
    console.error('Map instance is not available')
    return
  }

  if (!map.getSource('line-source')) {
    map.addSource('line-source', {
      type: 'geojson',
      data: data
    })
  } else {
    map.getSource('line-source').setData(data)
  }

  if (!map.getLayer('line-layer')) {
    map.addLayer({
      id: 'line-layer',
      type: 'line',
      source: 'line-source',
      paint: {
        'line-color': '#FF0000',
        'line-width': 2
      }
    })
  } else {
    console.warn('Line layer already exists')
  }
})
</script>