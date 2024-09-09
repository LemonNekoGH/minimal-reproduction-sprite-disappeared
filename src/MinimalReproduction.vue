<script setup lang="ts">
import texture from '@/assets/texture.png'
import { ref } from 'vue'

const exist = ref(true)
</script>

<template>
  <container>
    <sprite :texture="texture" v-if="exist"></sprite>
    <text v-if="exist" :y="50" :style="{ fill: 'white' }">
      Hello
    </text>
    <text :y="100" :style="{ fill: 'white' }" @click="exist = !exist">
      {{ exist ? 'remove' : 'add' }}
    </text>
  </container>
</template>
