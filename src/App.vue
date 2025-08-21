<script setup>
import { ref } from 'vue'

const appName = ref('我的 Vue 應用')
</script>

<template>
  <div id="app" class="min-h-screen bg-gradient-to-br from-gray-50 to-blue-100">
    <header class="bg-white shadow-lg sticky top-0 z-50">
      <nav class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="flex justify-between items-center h-16">
          <div class="flex-shrink-0">
            <h1 class="text-2xl font-bold text-gray-900">{{ appName }}</h1>
          </div>
          <div class="flex space-x-8">
            <RouterLink to="/" 
                        class="text-gray-700 hover:text-blue-600 px-3 py-2 rounded-md text-sm font-medium 
                               transition-colors duration-200 border-b-2 border-transparent 
                               hover:border-blue-600 router-link-active:text-blue-600 router-link-active:border-blue-600">
              首頁
            </RouterLink>
            <RouterLink to="/about" 
                        class="text-gray-700 hover:text-blue-600 px-3 py-2 rounded-md text-sm font-medium 
                               transition-colors duration-200 border-b-2 border-transparent 
                               hover:border-blue-600 router-link-active:text-blue-600 router-link-active:border-blue-600">
              關於
            </RouterLink>
          </div>
        </div>
      </nav>
    </header>

    <main class="max-w-7xl mx-auto py-8 px-4 sm:px-6 lg:px-8">
      <RouterView />
    </main>

    <footer class="bg-gray-800 text-white text-center py-6 mt-auto">
      <p>&copy; 2024 我的 Vue 學習專案</p>
    </footer>
  </div>
</template>
