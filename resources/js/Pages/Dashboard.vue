<script setup>
import Sidebar from '@/components/Dashboard/Sidebar.vue'
import Header from '@/components/Dashboard/Header.vue'
import Dashboard from '@/components/Dashboard/Dashboard.vue'

</script>

<style scoped>
.app, #app {
  display: flex;
  min-height: 100vh;
}

.main-content {
  flex: 1;
  display: flex;
  flex-direction: column;
  background-color: #f8f9fa;
}
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: 'Inter', sans-serif;
  background-color: #f5f5f5;
  color: #333;
}

</style>

<template>
  <div class="app">
    <Sidebar />
    <main class="main-content">
      <Header />
      <Dashboard />
    </main>
  </div>
</template>
