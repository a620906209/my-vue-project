<script setup>
import { ref } from 'vue'
import Counter from '../components/Counter.vue'

const message = ref('歡迎來到我的 Vue 應用！')
</script>

<template>
  <div class="text-center">
    <h1 class="text-4xl font-bold text-gray-900 mb-4">{{ message }}</h1>
    <p class="text-xl text-gray-600 mb-8">這是使用 Vue 3 + Tailwind CSS 建立的現代化應用</p>
    <Counter />
  </div>
</template>
