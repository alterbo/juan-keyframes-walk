<template>
  <g :transform="computedTransform">
    <slot />
    <circle :cx="anchor.x" :cy="anchor.y" r="5" fill="blue" />
  </g>
</template>

<script setup lang="ts">
import { computed } from 'vue'

interface Props {
  part: string
  anchor: { x: number; y: number }
  rotation: number
}

const props = defineProps<Props>()

const computedTransform = computed(() => {
  return `rotate(${props.rotation}, ${props.anchor.x}, ${props.anchor.y})`
})
</script>
