<script setup>
import { ref } from 'vue'

const title = ref('關於我們')
const technologies = ref([
  { name: 'Vue 3', desc: 'Composition API' },
  { name: 'Vue Router 4', desc: '路由管理' },
  { name: 'Pinia', desc: '狀態管理' },
  { name: 'Vite', desc: '建構工具' },
  { name: 'Tailwind CSS', desc: 'CSS 框架' }
])
</script>

<template>
  <div class="max-w-4xl mx-auto">
    <h1 class="text-4xl font-bold text-gray-900 mb-6">{{ title }}</h1>
    <p class="text-lg text-gray-600 mb-8">
      這是一個使用 Vue 3 + Tailwind CSS 建立的現代化 Web 應用程式。
    </p>
    
    <div class="bg-white rounded-xl shadow-lg p-8">
      <h2 class="text-2xl font-semibold mb-6 text-gray-800">使用的技術：</h2>
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-4">
        <div v-for="tech in technologies" :key="tech.name" 
             class="bg-gradient-to-r from-blue-50 to-indigo-50 p-4 rounded-lg border border-blue-200">
          <h3 class="font-semibold text-blue-900">{{ tech.name }}</h3>
          <p class="text-blue-700 text-sm">{{ tech.desc }}</p>
        </div>
      </div>
    </div>
  </div>
</template>
