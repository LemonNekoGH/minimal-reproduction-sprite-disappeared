<script setup lang="ts">
import { Application } from 'vue3-pixi'

import { settings } from 'pixi.js'
import MinimalReproduction from './MinimalReproduction.vue'
import { ref } from 'vue'

settings.RESOLUTION = window.devicePixelRatio

const components = ref([{ id: 1 }, { id: 2 }, { id: 3 }, { id: 4 }])
</script>

<template>
  <div class="container">
    <application :width="480" :height="270">
      <MinimalReproduction v-for="c in components" :key="c.id" :x="(c.id - 1) * 100" />
    </application>
  </div>
</template>

<style scoped>
.container {
  width: 100%;
  height: 100vh;
  overflow: hidden;
}
</style>
